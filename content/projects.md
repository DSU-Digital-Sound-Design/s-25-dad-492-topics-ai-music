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
   
---

# **Étude 2 - Audio Mosaic**  

## **Objective**  

In this project you will create a piece of music using MIR features from the Freesound API. You have two routes to choose from: coding or non-coding.

If you choose the **coding route**, you will extend the **Audio Mosaic App** by incorporating **sound selection and playback techniques using Tone.js**. Instead of selecting sounds randomly, you will extract **low-level sound features** from an initial sound to retrieve similar sounds dynamically. You will also explore **different playback and processing methods** using **Tone.js** and **p5.js**.

If you **do not have coding experience**, you may choose **Option 4** for your sound variation, which does not require modifying code. Instead, you will use the Freesound search app to explore sound features and create a short composition.


If you choose **Option 4**, **skip Step 1 and Step 2**.

---

## **Understanding the Base Project**  

[**Starter Project**](https://glitch.com/~5-content-search-based-on-analysis)  

The base project includes a **search-and-playback system** using **Freesound API** and **Tone.js**.

<details>
  <summary>How the Base App Works (Click to Expand)</summary>

### **Retrieves an Initial Sound:**  
- Searches **Freesound** based on an instrument tag and duration constraint.  
- Extracts **low-level sound features** from the selected sound:  
  - **Spectral Centroid** (brightness)  
  - **Spectral Complexity** (tonal vs. noisy content)  
  - **Zero Crossing Rate** (percussive vs. tonal sound)  
  - **MFCCs** (Mel-Frequency Cepstral Coefficients - timbral characteristics)  
- Displays the **sound’s metadata** and provides basic playback controls.  

### **Finds Similar Sounds Based on Features:**  
- Uses **content-based search** to retrieve **sonically similar sounds**.  
- The search is based on extracted **low-level descriptors** (e.g., spectral centroid, pitch, MFCCs, etc.).  
- Displays a **list of similar sounds** with playback controls.  

### **Manages Audio Playback:**  
- Uses **Tone.js** to create and manage multiple **Tone.Player** instances.  
- Implements **play and stop functionality** for each retrieved sound.  
- Uses a **map-based structure** to track active players.  

</details>

---

## **Step 1: Experiment with Feature Extraction (Skip if Choosing Option 4)**  

The base project retrieves a fixed set of features (**spectral centroid, spectral complexity, zero crossing rate, and MFCCs**). You must **experiment with additional low-level features** from [Freesound's API Analysis documentation](https://freesound.org/docs/api/analysis_docs.html).

<details>
  <summary>Low-Level Features to Experiment With (Click to Expand)</summary>

- **Spectral Features:**  
  - **Spectral Centroid** (Brightness - perceived pitch distribution)  
  - **Spectral Complexity** (Amount of tonal vs. noisy content)  
  - **Spectral Flatness** (How noisy or tonal a sound is)  

- **Temporal Features:**  
  - **Zero Crossing Rate** (How percussive or tonal a sound is)  
  - **Spectral Flux** (How fast the spectrum changes over time)  
  - **Temporal Centroid** (Where the energy is concentrated in time)  

- **Rhythmic Features:**  
  - **Onset Rate** (Number of detected note attacks)  
  - **BPM Estimation** (Tempo detection)  

- **Timbre Features:**  
  - **MFCCs** (Timbral characteristics, useful for classifying sound types)  
  - **Loudness Curve** (Loudness over time)  

</details>

Modify `handleFirstSearchResult()` to extract new features and log them to the console.

---

## **Step 2: Modify the Similar Sound Search (Skip if Choosing Option 4)**  

Once you've experimented with extracting features, modify `searchSimilarSounds()` to use new feature combinations for retrieving similar sounds.

<details>
  <summary>Example Adjustments to the Content-Based Search Query (Click to Expand)</summary>

- **Retrieve sounds with similar timbre characteristics:**  
  ```js
  const target = `.lowlevel.mfcc.mean:${mfccMean} + .lowlevel.spectral_complexity.mean:${complexityMean}`;
  ```
  
- **Retrieve rhythmically similar sounds:**  
  ```js
  const target = `.lowlevel.rhythm.bpm.mean:${bpm} + .lowlevel.onset_rate.mean:${onsetRate}`;
  ```

- **Retrieve percussive sounds with similar spectral characteristics:**  
  ```js
  const target = `.lowlevel.spectral_flux.mean:${fluxMean} + .lowlevel.zero_crossing_rate.mean:${zcr}`;
  ```

</details>

---

## **Step 3: Choose One of Four Playback and Sound Processing Variations**  

Once you have modified the search behavior (or if you are skipping coding and choosing **Option 4**), implement **one of the following playback variations**. Each variation explores a different **Tone.js event type** for triggering and manipulating sounds while incorporating **p5.js** for interactive control.

<details>
  <summary>Option 1: Sequenced Playback with Sound Feature Modulation</summary>

### **Overview**  
Transform retrieved sounds into a **pattern-based composition**, where playback is triggered at regular intervals using **Tone.js sequencing tools**.

### **Implementation Steps:**  
- Use **`Tone.Sequence`** to create a rhythmic or evolving playback sequence.  
- Modify playback order based on **spectral centroid** or another extracted feature.  
- Apply **LFOs (`Tone.LFO`)** to automate **pitch, filter sweeps, or volume** over time.  
- Use effects like **reverb (`Tone.Reverb`)**, **delay (`Tone.FeedbackDelay`)**, or **distortion (`Tone.Distortion`)**.  

**🎼 Example Use Case:**  
An evolving **ambient soundscape** where retrieved sounds play in a **repeating pattern**, shifting in timbre and position over time.

</details>

<details>
  <summary>Option 2: Performance-Based Triggering with Keyboard Input</summary>

### **Overview**  
Allows users to **trigger and manipulate sounds in real time** using **p5.js keyboard input functions**.

### **Implementation Steps:**  
- Use `p5.js keyPressed()` to trigger different retrieved sounds.  
- Implement **`Tone.Player`** to load and play sounds dynamically.  
- Allow **real-time pitch shifting (`Tone.PitchShift`)** or filtering (`Tone.Filter`).  
- Map keys to different effects (e.g., pressing ‘A’ applies **delay**, ‘B’ triggers a **filter sweep**).  

**🎼 Example Use Case:**  
An **interactive sampler** where retrieved sounds are played and manipulated **based on keyboard input**.

</details>

<details>
  <summary>Option 3: Interactive Layered Textures with Randomized Playback</summary>

### **Overview**  
Focuses on **asynchronous, layered playback**, where retrieved sounds are triggered at varying intervals to create a more organic composition.

### **Implementation Steps:**  
- Use **randomized scheduling** with `setTimeout()` or `Tone.Transport.schedule`.  
- Layer multiple sounds with slight timing offsets for a **shifting texture**.  
- Introduce **probability-based triggering**, where some sounds play more frequently than others.  
- Apply **granular processing (`Tone.GrainPlayer`)** and **spatialization (`Tone.Panner3D`)**.

**🎼 Example Use Case:**  
A **constantly shifting sound collage**, with each playback slightly different, creating an **unpredictable yet cohesive texture**.

</details>

<details open>
  <summary>Option 4: Feature-Based Sample Collage (No Coding Required)</summary>

### **Option 4: Feature-Based Sample Collage (No Coding Required)**  

This option allows you to explore **sound selection using audio features** without modifying code. Instead, you will use the **Freesound API AC Filter Search** app to find and filter sounds based on their **acoustic characteristics**, then create a short composition using those sounds.  

> **App Link**: [**Freesound API AC Filter Search**](https://glitch.com/~freesound-api-ac-filter-search)  

### **Implementation Steps**  

#### **1. Search for Sounds Using the App**  
- Experiment with available **AC filters**, or add ones from this list that aren't in the app, such as:  
  - **Timbre & Spectral Features**: `ac_brightness`, `ac_sharpness`, `ac_warmth`, `ac_roughness`, `ac_hardness`  
  - **Loudness & Dynamics**: `ac_loudness`, `ac_dynamic_range`  
  - **Time & Envelope Features**: `ac_log_attack_time`, `ac_temporal_centroid`  
  - **Rhythm & Pitch Features**: `ac_tempo`, `ac_tonality`, `ac_note_midi`, `ac_note_frequency`  
  - **Other Descriptors**: `ac_reverb`, `ac_loop`, `ac_single_event`  
- Click on the provided link to go to freesound.org and download the sounds for your composition.  
- Observe how changing the filters impacts the types of sounds retrieved.
- Tip: If you want to find a similar sound, just change one parameter at a time.

#### **2. Create a Composition**  
- Import the selected sounds into a **DAW**.  
- Arrange them into a **one-minute composition** that explores **sound relationships** and **textures**.  
- You may apply **effects** (EQ, reverb, pitch shift, etc.), but focus on using the **original characteristics** of the sounds.  

#### **3. Write a Short Reflection**  
- How did **AC features** influence your composition?  
- What were your **challenges in selecting sounds**?  
- How did your **audio choices** shape the final piece?  

</details>

---

## **Step 4: Create a Composition**  

All students must create a **one-minute composition** using their selected sounds.

---

## **Step 5: Write a Reflection**  

Write a **short (1-2 paragraph) reflection** addressing:  
- How did using **low-level features** or **search filters** in the search process influence your composition?  
- What changes did you make (if applicable) to the search algorithm?  
- How did the **audio characteristics** of your chosen sounds shape your creative decisions?  

---

## **Evaluation Criteria (50 Points Total)**  

| **Criteria**               | **Points** | **Description** |
|----------------------------|------------|------------------------------------------------|
| **Feature-Based Searching** | 15  | Successfully finds and uses sounds based on their features. |
| **Code Modification** (if applicable) | 10  | Successfully modifies the search system. |
| **Composition Quality**     | 15  | Effectively integrates selected sounds into a cohesive piece. |
| **Reflection & Analysis**   | 10  | Thoughtful discussion of feature-based searching and creative decisions. |


<!-- # Etude 2 - Audio Mosaic

## Objective  
In this project, you will extend the Audio Mosaic App by incorporating sound selection and playback techniques using Tone.js. You will modify how sounds are retrieved from the Freesound API and experiment with different playback event types, focusing on creative sound manipulation.

Instead of selecting sounds randomly, you will extract low-level features from an initial sound and use them to retrieve similar sounds dynamically. You will also implement different playback and processing methods using Tone.js and p5.js.

---

## Understanding the Base Project  

[Starter Project](https://glitch.com/~5-content-search-based-on-analysis)

The base project already includes a search-and-playback system using Freesound API and Tone.js. Below is a breakdown of how it works and what you can modify:

### How the Base App Works  

**Retrieves an Initial Sound:**
   - Searches Freesound based on an instrument tag and duration constraint.  
   - Extracts MIR features from the selected sound:  
     - Spectral Centroid (brightness)  
     - Pitch  
     - Spectral Spread (harmonic distribution)  
     - Dissonance  
   - Displays the sound’s metadata and provides basic playback controls.  

**Finds Similar Sounds Based on Features:**  
   - Uses content-based search to retrieve sonically similar sounds.  
   - The search is based on extracted MIR descriptors (e.g., spectral centroid, pitch, etc.).  
   - Displays a list of similar sounds with playback controls.  

 **Manages Audio Playback:**
   - Uses Tone.js to create and manage multiple Tone.Player instances.  
   - Implements play and stop functionality for each retrieved sound.  
   - Uses a map-based structure to track active players.  

---

## Your Task: Expanding the Search Process  

### Step 1: Experiment with Feature Extraction  
The base project retrieves a fixed set of features from the first sound (spectral centroid, pitch, spectral spread, and dissonance). You must experiment with additional features to refine the search for similar sounds.  

Freesound API Analysis Documentation:  
> [https://freesound.org/docs/api/analysis_docs.html](https://freesound.org/docs/api/analysis_docs.html)  

Some useful features you could extract:  
- MFCCs (Mel-Frequency Cepstral Coefficients): Timbre descriptors useful for classifying sound types.  
- Zero Crossing Rate: Determines whether a sound is percussive or tonal.  
- Spectral Flatness: Measures noisiness vs. tonal structure.  
- Rhythm Descriptors: Such as BPM or onset rate for rhythmic sounds.  
- Envelope Shape: How a sound evolves over time (attack, sustain, decay).  

Modify the `handleFirstSearchResult()` function to extract additional features and log them to the console. Once you find features that meaningfully differentiate sounds, use them to improve the content-based search query.

---

### Step 2: Modify the Similar Sound Search  
Once you've experimented with extracting features, modify `searchSimilarSounds()` to use new feature combinations for retrieving similar sounds.  

#### Example Adjustments to the Content-Based Search Query:  
- Retrieve tonally similar sounds:  
  ```js
  const target = `.lowlevel.mfcc.mean:${mfccMean}+.lowlevel.spectral_flatness.mean:${flatnessMean}`;
  ```
- Retrieve rhythmically similar sounds:  
  ```js
  const target = `.lowlevel.rhythm.bpm.mean:${bpm}+.lowlevel.onset_rate.mean:${onsetRate}`;
  ```
- Retrieve percussive sounds with similar spectral characteristics:  
  ```js
  const target = `.lowlevel.spectral_flux.mean:${fluxMean}+.lowlevel.zero_crossing_rate.mean:${zcr}`;
  ```

---

## Step 3: Implement One of Three Playback and Sound Processing Variations  

Once you have modified the search behavior, implement one of the following playback variations. Each variation explores a different Tone.js event type for triggering and manipulating sounds while incorporating p5.js for interactive control.

This is not an exhaustive list of possibilities; feel free to combine elements from different variations or propose your own creative approach. You don't need to implement every feature listed in the variations; focus on the ones that align with your creative vision.

---

### Option 1: Sequenced Playback with Sound Feature Modulation  
This variation transforms retrieved sounds into a pattern-based composition, where playback is triggered at regular intervals using Tone.js sequencing tools.

#### Implementation Steps:  
- Use `Tone.Sequence` to create a rhythmic or evolving playback sequence.  
- Modify playback order based on spectral centroid or another extracted feature.  
- Apply LFOs (`Tone.LFO`) to automate pitch, filter sweeps, or volume over time.  
- Use effects like reverb (`Tone.Reverb`), delay (`Tone.FeedbackDelay`), or distortion (`Tone.Distortion`) to shape the sound.  

#### Example Use Case:  
An evolving ambient soundscape where retrieved sounds play in a repeating pattern, shifting in timbre and position over time.

---

### Option 2: Performance-Based Triggering with Keyboard Input  
This variation allows users to trigger and manipulate sounds in real time using p5.js keyboard input functions.

#### Implementation Steps:  
- Use p5.js `keyPressed()` to trigger different retrieved sounds when a key is pressed. 
  - see: [p5.js Keyboard Input](https://p5js.org/reference/p5/keyPressed/) 
- Implement `Tone.Player` to load and play sounds dynamically.  
- Allow real-time pitch shifting (`Tone.PitchShift`) or filtering (`Tone.Filter`) based on key input.  
- Map keys to different effects (e.g., pressing ‘A’ applies a delay, ‘B’ triggers a filter sweep).  


#### Example Use Case:  
An interactive sampler where retrieved sounds are played and manipulated based on keyboard input.

---

### Option 3: Interactive Layered Textures with Randomized Playback  
This variation focuses on asynchronous, layered playback, where retrieved sounds are triggered at varying intervals to create a more organic composition.

#### Implementation Steps:  
- Use randomized scheduling with `setTimeout()` or `Tone.Transport.schedule`.  
- Layer multiple sounds with slight timing offsets for a shifting texture.  
- Introduce probability-based triggering, where some sounds play more frequently than others.  
- Apply granular processing (`Tone.GrainPlayer`) and spatialization (`Tone.Panner3D`) for movement.  

#### Example Use Case:  
A constantly shifting collage of retrieved sounds, with each playback slightly different, creating an unpredictable yet cohesive texture.

---

## Evaluation Criteria (50 Points Total)  

| **Criteria**               | **Points** | **Description** |
|----------------------------|------------|------------------------------------------------|
| Feature-Based Querying     | 10         | Successfully extracts and uses additional MIR features to refine the search process. |
| Code Implementation        | 20         | Functional, well-structured code with clear documentation. |
| Creative Demonstration     | 10         | Effectively showcases the new system through a vide screen recording. |
| Reflection & Analysis      | 10         | Thoughtful discussion of MIR principles and musical creativity. |

---

## Submission Requirements
- Your code with clear comments explaining audio parameters
- A brief write-up explaining:
   - Which extension you chose and why
   - How your sound design relates to word relationships
   - Your musical decision-making process
- A short video demonstration with audio  -->