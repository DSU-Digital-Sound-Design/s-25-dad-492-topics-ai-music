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

| **Criteria**                          | **Points** | **Description**                                                          |
| ------------------------------------- | ---------- | ------------------------------------------------------------------------ |
| **Feature-Based Searching**           | 15         | Successfully finds and uses sounds based on their features.              |
| **Code Modification** (if applicable) | 10         | Successfully modifies the search system.                                 |
| **Composition Quality**               | 15         | Effectively integrates selected sounds into a cohesive piece.            |
| **Reflection & Analysis**             | 10         | Thoughtful discussion of feature-based searching and creative decisions. |

---

# Etude 3 - Interactive Machine Learning with Wekinator 

## Overview

In this project, you will design an interactive system that uses Wekinator to process real-time inputs and generate musical or sound design outputs. You may develop:
- A live performance tool
- A generative composition
- An interactive sound installation
- A sound design tool

## Learning Objectives

By completing this project, you will:
- Apply interactive machine learning concepts to sound and music.
- Design a custom AI model that maps inputs (gesture, motion, facial expression, etc.) to musical outputs.
- Train, evaluate, and refine a real-time machine learning system using Wekinator.
- Experiment with MIDI mapping, automation, and sound synthesis in Reaper.

---

## Project Components

### **1. Concept Development**

**Refer to the course lectures and resources for inspiration and ideas.**

> - [Introduction to Wekinator for Interactive Machine Learning in Music](../lectures/week-7/hil-wekinator-intro/)
> - The guide for connecting Wekinator to Reaper - [Wekinator to Reaper](../lectures/week-8/wek-reaper/)

- **Brainstorm an idea** for how machine learning can be applied to sound.
- Choose between:
  - **Performance**: A live interactive system controlled by movement, gestures, or sound.
  - **Composition**: A fixed work in any style that used Wekinator in some substantial way in the compositional process.
  - A **sound design tool** that uses machine learning to generate or manipulate sounds for a film or game project. 
- **Examples to Consider**:
  - **Body Tracking Instrument** – Move your hands or full body to shape a live instrument.
  - **Facial Expression Mapping** – Control parameters (reverb, delay, EQ) using eyebrow raises, mouth shapes, or head tilts.
  - **Dynamic Mixing System** – Adjust levels based on detected movement intensity.
  - **Gesture-Based Synth Controller** – Create a synth patch that is controlled by motion.
  - **Mouse/Trackpad-Based Effects Controller** – Use drawn shapes or strokes to modulate sound effects.
  - **Real-Time Sonification** – Convert movement into real-time ambient or melodic structures.

### **2. Input & Output Mapping**

> See the [Wekinator to Reaper](../lectures/week-8/wek-reaper/) guide for setting up communication between Wekinator and Reaper. 
> 
> Also - Explore input and output [examples](http://www.wekinator.org/examples/) compatible with Wekinator.


- Choose **an input device**:
  - **Face tracking** (e.g., eye movement, smiles, head position)
  - **Body tracking** (e.g., webcam-based tracking)
  - **Mouse/trackpad movements**
    - Note: as this is the simplest, and least interesting input, your final project should have a very creative and compelling output to compensate.
  - **Audio-based control** (e.g., volume levels, voice analysis)
  - **Custom sensors** (e.g., Leap Motion, MIDI controllers)
- Define your **output in Reaper**:
  - **MIDI control** (e.g., notes, CC messages, velocity, pitch bend)
  - **Effects modulation** (e.g., dynamic filtering, real-time reverb control)
  - **Automation curves** (e.g., map hand movement to volume fades)
  - **Generative music triggers** (e.g., movement-based sample triggering)

---

## **3. Model Training & Implementation**
- **Train your Wekinator model**:
  - Collect **training data** with a variety of inputs.
  - Assign **clear mappings** between input features and outputs.
  - Experiment with **classification, regression, or dynamic time warping**.
    - We didn't cover classification or dynamic time warping, but they might be useful for your project. See [Understanding Wekinator’s output types
](http://www.wekinator.org/detailed-instructions/#Dynamic_time_warping_in_Wekinator) for more information.
- **Connect Wekinator to Reaper**:
  - See [Wekinator to Reaper](../lectures/week-8/wek-reaper/) for detailed instructions. 
  - Use MIDI learning to map gestures to DAW parameters.
  - Ensure latency and response time are optimized.
  - Fine-tune input sensitivity and model responsiveness.
- **Test and Refine**:
  - Identify strengths/weaknesses in the model.
  - Gather feedback (from yourself and classmates).
  - Adjust training data for **better accuracy and control**.

---

## **4. Documentation & Presentation**

### **A. Technical Documentation**
- Provide a **video walkthrough** covering:
  - **Concept**: What inspired your idea?
  - **Technical Setup**: What inputs and outputs were used?
  - **Machine Learning Process**: How did you train your model?
  - **Challenges & Refinements**: What issues arose, and how did you fix them?
  - **Final Outcome**: What does your system do?

### **B. Final Demonstration**

- Prepare a **short demo to show the class**.
- Be prepared to discuss how your **interactive system enhances (or hinders) musical creativity**.

---

# **Rubric: Evaluation Criteria**

| **Category**                     | **Excellent (A: 45-50)**                                                                                                                                                                                                                                                                                   | **Good (B: 40-44)**                                                                                                                                                                                                                      | **Satisfactory (C: 35-39)**                                                                                                                                                                                                                                                | **Needs Improvement (D/F: <34)**                                                                                                                                                                                                                                            |
| -------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Creativity & Concept**         | Highly innovative and clearly articulated idea demonstrating strong originality in applying interactive machine learning. Concept fully aligns with chosen area (performance, composition, sound design tool, or installation) and presents significant artistic or technical depth.                       | Creative and well-articulated idea with clear exploration of interactive machine learning. Chosen area is evident, with notable artistic or technical depth, but may lack some originality or complexity.                                | Adequately developed concept with a basic level of originality and clear area of focus. Demonstrates some understanding of interactive machine learning applications but lacks depth.                                                                                      | Underdeveloped or unoriginal concept. Area of application unclear or poorly executed. Little meaningful use or understanding of interactive machine learning concepts.                                                                                                      |
| **Technical Execution**          | Inputs and outputs are effectively mapped and work seamlessly with Wekinator and Reaper. System performs smoothly with minimal latency, clearly optimized for real-time interaction. All components function reliably in live settings.                                                                    | Inputs and outputs are mostly effective with minor technical issues. Some latency or minor integration problems, but these do not significantly impact usability or real-time interaction.                                               | Inputs and outputs function adequately but with noticeable latency or occasional errors. Somewhat inconsistent integration with Reaper, impacting real-time responsiveness.                                                                                                | Significant technical issues prevent effective use. Inputs and outputs poorly integrated, frequent errors, and substantial latency make real-time interaction difficult or impossible.                                                                                      |
| **Machine Learning Use**         | Training data is thoughtfully designed, comprehensive, and effectively structured, resulting in an accurate and highly responsive Wekinator model. Clear mappings and successful experimentation with chosen ML methods (classification, regression, dynamic time warping).                                | Adequately structured training data providing generally accurate model behavior, though some refinement needed. Effective mapping with occasional minor inaccuracies or responsiveness issues.                                           | Training data has noticeable gaps or inconsistencies, resulting in unpredictable or limited model accuracy and responsiveness. Minimal experimentation with ML methods beyond basic setup.                                                                                 | Poorly structured or insufficient training data resulting in ineffective or unusable machine learning model. Little or no meaningful experimentation with Wekinator.                                                                                                        |
| **Musical/Sonic Outcome**        | System produces compelling, expressive, and nuanced musical or sonic results. Thoughtful integration of machine learning significantly enhances the musical experience or sound design application.                                                                                                        | System produces musically engaging results with clear value added by machine learning, though certain aspects could be more fully developed or expressive.                                                                               | System generates some musical interaction but lacks expressiveness, nuance, or clear added value from machine learning integration. Results are predictable or overly simplistic.                                                                                          | System fails to effectively demonstrate musical or sonic creativity. Little or no expressive interaction resulting from machine learning integration.                                                                                                                       |
| **Documentation & Presentation** | Thorough, clear, and insightful documentation and video walkthrough. Clearly explains concept inspiration, detailed technical setup, ML training process, challenges encountered, and specific refinements made. Demonstration effectively communicates the project's creative and technical achievements. | Good quality documentation and video walkthrough, clearly explaining most elements, though some minor gaps in detail or clarity are present. Demonstration successfully showcases project outcomes with minor areas needing elaboration. | Adequate documentation and video walkthrough covering basic process and project elements. Several details missing or insufficiently explained, leading to questions about training, setup, or refinements. Demonstration covers basic outcomes but lacks depth or clarity. | Poorly executed documentation and presentation, lacking clarity or completeness. Significant details missing, unclear explanations, or minimal reflection on challenges and solutions. Demonstration fails to effectively communicate project outcomes or learning process. |

