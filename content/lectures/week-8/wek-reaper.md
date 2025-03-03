---
title: "Wekinator to Reaper"
---


Download [Processing](https://processing.org) and run this code. This code listens for OSC messages from Wekinator and forwards them to Reaper. It also splits them into individual parameters and only sends them if they have changed beyond a certain threshold. This is useful for controlling individual parameters in Reaper, such as volume, pan, or effects.

```java
import oscP5.*;
import netP5.*;

OscP5 oscP5;
NetAddress reaperDest; // Reaper destination
float[] lastValues;
float threshold = 0.001; // Minimum change required to send an update

void setup() {
  size(400, 200);
  
  // Start listening for OSC messages on port 12000 (per Wekinator settings)
  oscP5 = new OscP5(this, 12000);
  
  // Set Reaper as the OSC destination (default port for Reaper OSC input is 8000)
  reaperDest = new NetAddress("127.0.0.1", 8000);
  
  println("Listening for OSC messages on port 12000...");
  println("Forwarding processed messages to Reaper on port 8000...");
}

void draw() {
  background(0);
  fill(255);
  text("Receiving OSC from Wekinator on port 12000...", 20, 50);
  text("Sending OSC to Reaper on port 8000...", 20, 70);
}

// Handle incoming OSC messages from Wekinator
void oscEvent(OscMessage msg) {
  if (msg.checkAddrPattern("/wek/outputs")) {  // Match Wekinator's output path
    println("Received OSC: " + msg);
    
    int numParams = msg.arguments().length;
    if (lastValues == null || lastValues.length != numParams) {
      lastValues = new float[numParams]; // Initialize if necessary
    }
    
    // Parse each value and send only if it has changed beyond the threshold
    for (int i = 0; i < numParams; i++) {
      float value = msg.get(i).floatValue();
      if (abs(value - lastValues[i]) > threshold) { // Only send if value has changed
        println("Value " + (i + 1) + " changed: " + value);
        sendToReaper(i + 1, value);
        lastValues[i] = value; // Update last known value
      }
    }
  }
}

// Send an OSC message to Reaper
void sendToReaper(int parameterIndex, float value) {
  String oscAddress = "/wek/param" + parameterIndex;
  
  OscMessage reaperMsg = new OscMessage(oscAddress);
  reaperMsg.add(value);
  oscP5.send(reaperMsg, reaperDest);

  println("Sent to Reaper: " + oscAddress + " -> " + value);
}
```

Then, setup your Reaper settings like this: 

![alt text](../reaper-osc.png)