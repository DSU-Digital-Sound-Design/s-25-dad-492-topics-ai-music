---
title: "Projects"
date: "2018-07-18"
author: ""
---

{{< toc >}}


# Etude 1 - Sonic Poetry Generator 

## Overview
In this assignment, you will create a sonic poetry generator that explores the relationship between words and sound. Building upon our [in-class examples](../lectures/week-2/word2vec-intro/), you will implement one musical extension that demonstrates your understanding of synthesis, sound design, or music theory.

## Core Requirements

### Basic Implementation (Required)
1. Load and use the word2vec model to find related words
2. Create a basic melody system
3. Display words on screen with animation
4. Include start/stop functionality
5. Handle errors appropriately

### Musical Extension (Choose One)
Select one of these extensions to make the poetry generator your own. Each option emphasizes different aspects of sound design or music theory.

#### Extension 1: Timbre Evolution
Create meaningful relationships between words and synthesizer timbre. 

Implementation guidance:
- Start by modifying the oscillator type between sine and triangle for different words
- Experiment with attack and release times to create different note characteristics
- Consider how word relationships might map to timbral qualities (e.g., similar words = warm tones, distant words = bright tones)

#### Extension 2: Musical Intervals
Design melodic relationships using specific musical intervals based on word relationships. 

Implementation guidance:
- Begin with simple mappings like major thirds for similar words
- Add minor intervals for more distant relationships
- Create small collections of intervals that work well together
- Consider using pentatonic scales to ensure pleasant combinations

#### Extension 3: Effects Processing
Change audio effects as the poem progresses depending on the word relationships.

Implementation guidance:
- Start with subtle reverb adjustments
- Add delay for more distant word relationships
- Keep effect levels moderate to maintain clarity
- Consider how the space changes with different word combinations

## Assessment Rubric (50 points)

### Core Functionality (25 points)
- Word generation works correctly (7 points)
- Basic audio plays reliably (7 points)
- Visual display functions (7 points)
- Start/stop works properly (4 points)

### Musical Extension (17 points)
- Sonic implementation (6 points)
- Musical effectiveness (6 points)
- Creative use of parameters (5 points)

### Documentation and Process (8 points)
- Documentation of musical choices (3 points)
- Clear explanation of parameters (3 points)
- Thoughtful sound design decisions (2 points)


## Submission Requirements
1. Your code with clear comments explaining audio parameters
2. A brief write-up explaining:
   - Which extension you chose and why
   - How your sound design relates to word relationships
   - Your musical decision-making process
3. A short video demonstration with audio 
   
# Project 2 
<!-- 
### **Expanding the Audio Mosaic App with MIR Principles and Advanced Sound Processing**  

#### **Objective**  
In this project, you will enhance the existing Audio Mosaic App by incorporating new techniques for querying and processing sounds. You will apply principles from Music Information Retrieval (MIR) to retrieve relevant sounds from the Freesound API and use advanced Tone.js functionalities to manipulate them.  

Your sound selection should be based on meaningful features such as spectral centroid, pitch, tempo, duration, and loudness rather than random selection alone. You will also incorporate new methods of sound processing in Tone.js to expand musical creativity.

---

## **Part 1: Understanding the Base Project**  
Before modifying the app, review the existing Audio Mosaic App, which:  
- Uses the Freesound API to retrieve random and similar sounds  
- Plays sounds using Tone.js  
- Includes a basic sequence-based playback system  

Explore the Freesound API documentation to understand how sound features can be used to retrieve meaningful audio results instead of selecting sounds arbitrarily.

---

## **Part 2: Expanding Creativity – Choose One Path**  
Select one of the following variations, each introducing a new querying strategy and a unique sound processing technique.

### **Option 1: Feature-Based Sound Retrieval with Generative Processing**  
This approach focuses on automated composition by retrieving and layering sounds based on MIR features such as spectral centroid, loudness, and pitch. Your system will continuously evolve over time without direct user input, creating a dynamic generative soundscape.

#### **Freesound API Queries**  
Modify the existing query system to retrieve sounds based on specific MIR features:  
- **Timbre selection:** Use spectral centroid to control whether sounds are bright or dark.  
  - Example query: `"spectral_centroid:[2000 TO 10000]"` for bright sounds.  
- **Melodic or atonal elements:** Retrieve sounds based on pitch salience.  
  - Example query: `"pitch_salience:[0.5 TO 1]"`.  
- **Dynamic contrast:** Retrieve sounds based on loudness.  
  - Example query: `"loudness:[-40 TO -10]"`.  

#### **Tone.js Implementation**  
- Use **Tone.Loop** or **Tone.Sequence** to generate an evolving soundscape.  
- Apply **granular synthesis** by slicing samples into small segments.  
- Randomize **filtering, reverb, and panning** to add movement.  
- Introduce **automated transformations** over time, making the soundscape unpredictable.  

Your final system should generate an evolving composition where sounds shift, blend, and transform based on their characteristics.

---

### **Option 2: Sound Collage with Dynamic Effects and Pitch Manipulation**  
This approach allows you to build an interactive sound collage, where you select, arrange, and modify sounds manually. Unlike the generative system, this version lets you actively shape the composition by applying effects and pitch alterations.

#### **Freesound API Queries**  
Modify the existing query system to retrieve sounds based on categorical or descriptive tags:  
- **Instrument selection:** Search for specific sound types such as percussion, piano, or strings.  
  - Example query: `"tag:drums OR tag:piano OR tag:strings"`.  
- **Tonal characteristics:** Select sounds based on descriptions such as rough, smooth, or metallic.  
  - Example query: `"tag:metallic OR tag:soft OR tag:airy"`.  
- **Mood-based selection:** Retrieve sounds with expressive descriptors such as dark, ethereal, or glitch.  
  - Example query: `"tag:dark OR tag:ethereal OR tag:glitch"`.  

#### **Tone.js Implementation**  
- Implement **real-time pitch shifting** using **Tone.PitchShift**.  
- Allow users to **spatialize sounds** using **Tone.Panner3D**.  
- Integrate **reverb and filtering** to create depth.  
- Build a **drag-and-drop interface** where users can arrange sounds in a timeline.  

Your final system should allow users to shape a sound collage interactively, adjusting pitch, spatialization, and effects in real time.

---

### **Option 3: Beat Slicing and Rhythmic Manipulation with Adaptive Querying**  
This approach focuses on rhythm by retrieving percussive sounds and manipulating them using beat slicing and sequencing techniques. Instead of playing entire samples, you will divide them into rhythmic segments and reconstruct them dynamically.

#### **Freesound API Queries**  
Modify the existing query system to retrieve rhythmically relevant sounds:  
- **Tempo matching:** Retrieve sounds that match a specific BPM.  
  - Example query: `"bpm:[80 TO 120]"`.  
- **Percussive content:** Find rhythmic loops or drum samples.  
  - Example query: `"tag:drums OR tag:percussion OR tag:beat"`.  
- **Transient density:** Select sounds with multiple rhythmic events that can be sliced.  
  - Example query: `"note_dominant:[0 TO 100]"`.  

#### **Tone.js Implementation**  
- Implement **beat slicing** to divide sounds into equal segments.  
- Use **Tone.Loop** or **Tone.Sequence** to arrange sliced sounds into new patterns.  
- Allow users to **tap a tempo**, adjusting the playback BPM dynamically.  
- Apply **filters, distortion, and effects** to enhance rhythmic textures.  

Your final system should allow users to create new rhythmic structures by selecting, slicing, and rearranging percussive sounds.

---

## **Part 3: Implementation & Submission**  

### **Deliverables**  
1. **Feature-Based Query System (20%)**  
   - Modify the Freesound API query system to retrieve sounds based on meaningful features.  
   - Clearly document how your query parameters relate to MIR principles.  

2. **Code Implementation (40%)**  
   - Successfully integrate the selected modification into the Audio Mosaic App.  
   - Ensure that the new system functions correctly and efficiently.  

3. **Creative Demonstration (20%)**  
   - Record a short video or audio demonstration (3-5 minutes) showcasing your modified app in action.  
   - Explain how your enhancements improve the creative possibilities of the project.  

4. **Reflection & Analysis (20%)**  
   - Write a 1-2 page reflection discussing:  
     - The MIR techniques used in your project.  
     - The musical impact of your modifications.  
     - The challenges you encountered and how you addressed them.  

---

## **Evaluation Criteria**  

| **Criteria**               | **Points** | **Description** |
|----------------------------|------------|------------------------------------------------|
| Feature-Based Querying     | 20         | Effectively retrieves sounds using meaningful MIR-based parameters. |
| Code Implementation        | 40         | Functional, well-structured code with clear documentation. |
| Creative Demonstration     | 20         | Demonstrates the impact of the new features through a video or audio example. |
| Reflection & Analysis      | 20         | Thoughtful discussion of MIR principles and musical creativity. |

---

## **Bonus Challenge**  
If you combine two or more of the options into a single project, you can earn extra credit by demonstrating a higher level of complexity and creativity.

---

## **Conclusion**  
This project challenges you to apply MIR principles to real-world music technology development while expanding the creative potential of the Audio Mosaic App. By exploring feature-based sound retrieval and advanced Tone.js processing, you will gain a deeper understanding of algorithmic composition, sound design, and interactive music systems. -->