---
title: "Freesound API"
---

## Overview

On this page, we will explore the [Freesound API](https://freesound.org/docs/api/resources_apiv2.html), a platform for sharing and downloading Creative Commons-licensed sounds. We will learn how to search for sounds, download them, and use them in our projects.

## What is the Freesound API?

The Freesound API is a RESTful API that allows you to search, browse, and download sounds from the Freesound database. The API provides access to a wide range of sound-related data, including sound metadata, sound analysis data, and user data.

## Getting Started

To get started with the Freesound API, you will need to create an account on the Freesound website and obtain an API key. You can create an account and obtain an API key [here](https://freesound.org/apiv2/apply/).

Once you have obtained an API key, you can start using the API to search for sounds, download them, and use them in your projects.

## Example 1

This example shows finding a random sound from Freesound then finding 10 similar sounds. Sounds are played with the Tone.js Player object.

<div class="glitch-embed-wrap" style="height: 420px; width: 100%;">
  <iframe
    src="https://glitch.com/embed/#!/embed/freesound-random-similar?path=script.js&previewSize=0"
    title="freesound-random-similar on Glitch"
    allow="geolocation; microphone; camera; midi; encrypted-media; xr-spatial-tracking; fullscreen"
    allowFullScreen
    style="height: 100%; width: 100%; border: 0;">
  </iframe>
</div>

## Example 2

Here's an example project that queries the Freesound database for one random sound. Then the user can find similar sounds to that random sound. 

Finally, we can create a sequence out of the similar sounds.

<!-- Copy and Paste Me -->
<div class="glitch-embed-wrap" style="height: 420px; width: 100%;">
  <iframe
    src="https://glitch.com/embed/#!/embed/freesound-random-similar-sequence?path=script.js&previewSize=0"
    title="freesound-random-similar-sequence on Glitch"
    allow="geolocation; microphone; camera; midi; encrypted-media; xr-spatial-tracking; fullscreen"
    allowFullScreen
    style="height: 100%; width: 100%; border: 0;">
  </iframe>
</div>

### User Story

- **User clicks a button** → Requests a **random sound** from Freesound.
- **Sound is loaded** into a Tone.js **Player**.
- **User plays the sound**, which is stored in a **Map** for reuse.
- **User can stop the sound** or request **similar sounds**.

### Key Sections

| **Concept**            | **Corresponding Code Section** | **Explanation** |
|------------------------|--------------------------------|----------------|
| **Setup & Initialization** | `setup()` | Sets up event listeners and loads an initial sound. |
| **Fetching Sounds** | `getRandomSound()` | Queries Freesound API for a random sound and loads it. |
| **Creating a Sound Player** | `createTonePlayer()` | Uses Tone.js to load and manage sounds. |
| **Playing and Stopping Sounds** | `playSound()` and `stopSound()` | Plays or stops the currently loaded sound. |
| **Finding Similar Sounds** | `getSimilarSounds()` | Searches for and loads sounds similar to the current one. |

---

### Interactive Debugging with Console Logs

Add console logs to show the **sound fetching process**:

```javascript
console.log("Fetching a random sound:", query);
console.log("Loaded sound object:", sound);
console.log("Playing sound:", id);
console.log("Stopping current sound");
```
This helps you **see what’s happening step by step**.

---

###   Sound Design Modifications

Let's make a few modifications to the sound design:

#### **Task 1: Change the Sound Categories**

Modify this line in `getRandomSound()`:
```javascript
const queries = ["dog", "cat", "water", "wind", "fire", "music", "bird", "rain"];
```

**Challenge:** Replace with different sound categories, such as:
```javascript
const queries = ["bells", "guitar", "thunder", "clapping", "footsteps"];
```

Then test how the changes affect the results.

---

#### **Task 2: Modify Playback Behavior**

Find this part of the `createTonePlayer()` function:

```javascript
const player = new Tone.Player({
  url: url,
  autostart: false,
}).toDestination();
```

**Challenge:** Modify playback settings by adding effects:
```javascript
const reverb = new Tone.Reverb().toDestination();
const player = new Tone.Player({
  url: url,
  autostart: false,
}).connect(reverb);
```

> **How does reverb change the sound?**

---

### **Task 3: Add a Loop Button**
Add a **looping feature** to the player.
```javascript
const loopButton = createButton("Loop");
loopButton.mousePressed(() => {
  if (currentPlayer) {
    currentPlayer.loop = !currentPlayer.loop;
    loopButton.html(currentPlayer.loop ? "Stop Loop" : "Loop");
  }
});
```
**Challenge:** Add this to the `container` so it appears in the UI.

---

### **Task 4: Change the Sound Playback Speed**
Modify `playSound()` to alter the playback speed:
```javascript
currentPlayer.playbackRate = random(0.5, 2);
```
> How does speed affect pitch?

---

## **5. Group Challenge: Customizing Sound Effects**

Now, lets try a group challenge: 

See: [Player](https://tonejs.github.io/docs/15.0.4/classes/Player.html)

- Group 1: Add a **delay effect** using `Tone.FeedbackDelay()`.
- Group 2: Make sounds **fade in and out** using the built in envelope on the `Tone.Player`.
- Group 3: Play **multiple sounds at once** in a sequence.
- Group 4: Alter the `Tone.Player` start offset to play a different part of the sample. 

Each group presents their changes and demonstrates the effect.

