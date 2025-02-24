+++
title = "Introduction to Wekinator for Interactive Machine Learning in Music"
outputs = ["Reveal"]
[logo]
src = "github-logo.png"
[reveal_hugo]
custom_theme = "reveal-hugo/themes/robot-lung.css"
margin = 0.2
separator = "##"
+++


# Interactive Machine Learning (IML) for Audio  

**Exploring AI-Driven Sound and Gesture Interaction**  

---

## What is Interactive Machine Learning (IML)?

- **Definition:** IML is a form of machine learning where users train models in real time through iterative feedback.
- **Why It Matters?**
  - Unlike traditional ML, IML allows artists, musicians, and designers to create custom AI models quickly.

---

## IML Principles

- **Definition:** IML involves a cyclical process where users iteratively train, evaluate, and refine models based on immediate feedback.
- **Human-in-the-Loop:** Emphasizes collaboration between humans and machines to improve learning efficiency and model performance.
- **Applications in Audio:** Real-time sound synthesis, adaptive musical interfaces, and responsive audio effects.


---

<img width="500px" src="https://mermaid.ink/img/eyJjb2RlIjoiZ3JhcGggVEQ7XG5Vc2VyIC0tPnxQcm92aWRlcyBFeGFtcGxlc3wgTW9kZWw7XG5Nb2RlbCAtLT58UHJlZGljdHMgT3V0cHV0fCBTeXN0ZW07XG5TeXN0ZW0gLS0-fFVzZXIgQWRqdXN0c3wgVXNlclxuICAgICAgICAgICAgIiwibWVybWFpZCI6eyJ0aGVtZSI6ImRlZmF1bHQiLCJ0aGVtZVZhcmlhYmxlcyI6eyJiYWNrZ3JvdW5kIjoiI0ZDRUFFRCIsInByaW1hcnlDb2xvciI6IiNFMTNGNUUiLCJzZWNvbmRhcnlDb2xvciI6IiNGRkZGRkYiLCJ0ZXJ0aWFyeUNvbG9yIjoiaHNsKDE4OC41MTg1MTg1MTg1LCA3Mi45NzI5NzI5NzMlLCA1Ni40NzA1ODgyMzUzJSkiLCJwcmltYXJ5Qm9yZGVyQ29sb3IiOiJoc2woMzQ4LjUxODUxODUxODUsIDMyLjk3Mjk3Mjk3MyUsIDQ2LjQ3MDU4ODIzNTMlKSIsInNlY29uZGFyeUJvcmRlckNvbG9yIjoiaHNsKDAsIDAlLCA5MCUpIiwidGVydGlhcnlCb3JkZXJDb2xvciI6ImhzbCgxODguNTE4NTE4NTE4NSwgMzIuOTcyOTcyOTczJSwgNDYuNDcwNTg4MjM1MyUpIiwicHJpbWFyeVRleHRDb2xvciI6IiM0ZTRjNGQiLCJzZWNvbmRhcnlUZXh0Q29sb3IiOiIjMDAwMDAwIiwidGVydGlhcnlUZXh0Q29sb3IiOiJyZ2IoMTkyLCA1Mi45OTk5OTk5OTk5LCAzMCkiLCJsaW5lQ29sb3IiOiIjMjMyNTJDIiwidGV4dENvbG9yIjoiIzIzMjUyQyIsIm1haW5Ca2ciOiIjRkNFQUVEIiwic2Vjb25kQmtnIjoiI0Y2QjRDMiIsImJvcmRlcjEiOiIjRjY3MDhFIiwiYm9yZGVyMiI6IiNFMzQ4NkEiLCJhcnJvd2hlYWRDb2xvciI6IiMyMzI1MkMiLCJmb250RmFtaWx5IjoiXCJ0cmVidWNoZXQgbXNcIiwgdmVyZGFuYSwgYXJpYWwiLCJmb250U2l6ZSI6IjE0cHgiLCJsYWJlbEJhY2tncm91bmQiOiIjZmZmZmZmIiwibm9kZUJrZyI6IiNGQ0VBRUQiLCJub2RlQm9yZGVyIjoiI0Y2NzA4RSIsImNsdXN0ZXJCa2ciOiIjRjZCNEMyIiwiY2x1c3RlckJvcmRlciI6IiNFMzQ4NkEiLCJkZWZhdWx0TGlua0NvbG9yIjoiIzIzMjUyQyIsInRpdGxlQ29sb3IiOiIjMjMyNTJDIiwiZWRnZUxhYmVsQmFja2dyb3VuZCI6IiNmZmZmZmYiLCJhY3RvckJvcmRlciI6ImhzbCgzNDYuNTY3MTY0MTc5MSwgODguMTU3ODk0NzM2OCUsIDkzLjE5NjA3ODQzMTQlKSIsImFjdG9yQmtnIjoiI0ZDRUFFRCIsImFjdG9yVGV4dENvbG9yIjoiIzIzMjUyQyIsImFjdG9yTGluZUNvbG9yIjoiZ3JleSIsInNpZ25hbENvbG9yIjoiIzIzMjUyQyIsInNpZ25hbFRleHRDb2xvciI6IiMyMzI1MkMiLCJsYWJlbEJveEJrZ0NvbG9yIjoiI0ZDRUFFRCIsImxhYmVsQm94Qm9yZGVyQ29sb3IiOiJoc2woMzQ2LjU2NzE2NDE3OTEsIDg4LjE1Nzg5NDczNjglLCA5My4xOTYwNzg0MzE0JSkiLCJsYWJlbFRleHRDb2xvciI6IiMyMzI1MkMiLCJsb29wVGV4dENvbG9yIjoiIzIzMjUyQyIsIm5vdGVCb3JkZXJDb2xvciI6IiNFMzQ4NkEiLCJub3RlQmtnQ29sb3IiOiIjRjY3MDhFIiwibm90ZVRleHRDb2xvciI6IiMyMzI1MkMiLCJhY3RpdmF0aW9uQm9yZGVyQ29sb3IiOiIjMkMyRDMyIiwiYWN0aXZhdGlvbkJrZ0NvbG9yIjoiI0Y2QjRDMiIsInNlcXVlbmNlTnVtYmVyQ29sb3IiOiIjMkMyRDMyIiwic2VjdGlvbkJrZ0NvbG9yIjoiI0Y2QjRDMiIsImFsdFNlY3Rpb25Ca2dDb2xvciI6IndoaXRlIiwic2VjdGlvbkJrZ0NvbG9yMiI6IiNmZmY0MDAiLCJ0YXNrQm9yZGVyQ29sb3IiOiIjRTEzRjVFIiwidGFza0JrZ0NvbG9yIjoiI0Y2NzA4RSIsInRhc2tUZXh0TGlnaHRDb2xvciI6IndoaXRlIiwidGFza1RleHRDb2xvciI6IndoaXRlIiwidGFza1RleHREYXJrQ29sb3IiOiJibGFjayIsInRhc2tUZXh0T3V0c2lkZUNvbG9yIjoiYmxhY2siLCJ0YXNrVGV4dENsaWNrYWJsZUNvbG9yIjoiI0UxM0Y1RSIsImFjdGl2ZVRhc2tCb3JkZXJDb2xvciI6IiNFMTNGNUUiLCJhY3RpdmVUYXNrQmtnQ29sb3IiOiIjRjY3MDhFIiwiZ3JpZENvbG9yIjoibGlnaHRncmV5IiwiZG9uZVRhc2tCa2dDb2xvciI6ImxpZ2h0Z3JleSIsImRvbmVUYXNrQm9yZGVyQ29sb3IiOiJncmV5IiwiY3JpdEJvcmRlckNvbG9yIjoiI0UxM0Y1RSIsImNyaXRCa2dDb2xvciI6InJlZCIsInRvZGF5TGluZUNvbG9yIjoicmVkIiwibGFiZWxDb2xvciI6ImJsYWNrIiwiZXJyb3JCa2dDb2xvciI6IiM1NTIyMjIiLCJlcnJvclRleHRDb2xvciI6IiM1NTIyMjIiLCJjbGFzc1RleHQiOiIjNGU0YzRkIiwiZmlsbFR5cGUwIjoiI0UxM0Y1RSIsImZpbGxUeXBlMSI6IiNGRkZGRkYiLCJmaWxsVHlwZTIiOiJoc2woNTIuNTE4NTE4NTE4NSwgNzIuOTcyOTcyOTczJSwgNTYuNDcwNTg4MjM1MyUpIiwiZmlsbFR5cGUzIjoiaHNsKDY0LCAwJSwgMTAwJSkiLCJmaWxsVHlwZTQiOiJoc2woMjg0LjUxODUxODUxODUsIDcyLjk3Mjk3Mjk3MyUsIDU2LjQ3MDU4ODIzNTMlKSIsImZpbGxUeXBlNSI6ImhzbCgtNjQsIDAlLCAxMDAlKSIsImZpbGxUeXBlNiI6ImhzbCgxMTYuNTE4NTE4NTE4NSwgNzIuOTcyOTcyOTczJSwgNTYuNDcwNTg4MjM1MyUpIiwiZmlsbFR5cGU3IjoiaHNsKDEyOCwgMCUsIDEwMCUpIn19LCJ1cGRhdGVFZGl0b3IiOmZhbHNlfQ">

{{% note %}}
**Interactive Machine Learning (IML) Loop:**
1. **User** provides input data.
2. **Model** processes the data.
3. **System** outputs results.
4. **User** provides feedback.
5. **Model** updates based on feedback.
6. **System** improves over time.
{{% /note %}}


---

## Why Use IML in Music and Audio?

- **Creative Possibilities:**
  - Allows performers to control sounds dynamically using gestures or sensors.
  - Transforms real-world movements into sound interactions.
  - Enables composers and sound designers to experiment with generative AI tools.

{{% note %}}
Interactive Machine Learning (IML) offers unique opportunities for innovation in music and audio creation. Here's why IML is valuable in these domains:

- **Creative Potential:** IML enables intuitive design of gesture-to-sound mappings, allowing quick definition of mapping nodes through training examples. Users can create systems that accept various inputs and produce diverse outputs.

- **Control and Expression:** Performers can manipulate sound attributes via movement, seamlessly integrating dance and music in real-time. IML supports the creation of new gestural controllers, facilitating on-the-fly generation of gesture examples and real-time model evaluation.

- **Gestural Control of Music:** IML is specifically designed for musical applications, excelling in real-time audio analysis and gestural control.

- **Experimentation with Generative AI:** Sound designers can swiftly iterate over ideas, producing novel and imaginative sound elements.

- **Accessibility:** IML provides a user-friendly tool for developing sensor interactions through an in-engine visual node workflow, requiring no prior machine learning expertise.

- **Customization:** Both developers and players can iteratively train IML models, enabling the development of bespoke controllers for individuals with motion impairments and game mechanics centered around player-customized actions.

- **Real-Time Interaction:** IML offers a comprehensive environment for all learning stages, allowing users to guide and modify mappings in a dynamic, performative manner.

- **Composition:** Tools like Wekinator facilitate the application of music information retrieval techniques based on machine learning to real-time musical performance.

- **Data Structuring:** IML is effective in imparting structure to unstructured data, enhancing its utility and interpretability.
{{% /note %}}




---

## Meet Wekinator – A Tool for IML in Music

- **What is Wekinator?**
  - A free, real-time machine learning software for musicians, artists, and developers.
  - Created by Rebecca Fiebrink to make AI more accessible for creative applications.
- **How does it work?**
  - **Inputs:** (MIDI controllers, webcams, sensors).
  - **User trains the model** with examples.
  - **Outputs:** (Sound changes, MIDI data, visuals).

**Resource:** [Wekinator Website](https://wekinator.org/)

{{% note %}}

**Wekinator Overview:**
- **Purpose:** Wekinator is a user-friendly tool designed to facilitate the integration of machine learning into creative projects, particularly in the realm of music and sound design.
- **Features:** Wekinator enables real-time machine learning, allowing users to train models with examples and apply them to control sound synthesis, MIDI data, and visual elements.
- **Accessibility:** Wekinator is freely available, making it an accessible tool for musicians, artists, and developers interested in incorporating AI into their creative workflows.
- **Creator:** Rebecca Fiebrink developed Wekinator to bridge the gap between machine learning and creative applications, empowering users to leverage AI for expressive and interactive projects.

{{% /note %}}

---

## Wekinator in Action – Applications in Music

- **Live Performance:** Control reverb and sound parameters using hand motion.
  - [Wekinating 000000Swan: Using Machine Learning to
Create and Control Complex Artistic Systems](https://citeseerx.ist.psu.edu/document?repid=rep1&type=pdf&doi=52320c4fef8fc10bd1380caf1b6dd7dde3b90e72), [A Meta-Instrument for Interactive, On-the-fly Machine Learning](https://ualresearchonline.arts.ac.uk/id/eprint/16687/1/FiebrinkTruemanCook_NIME2009.pdf)
- **Instrument Augmentation:** Smart bow tracking for expressive cello performance.
  - [A Demonstration of Bow Articulation Recognition with Wekinator and K-Bow](https://quod.lib.umich.edu/i/icmc/bbp2372.2011.053/1)
- **Sound Art & Installations:** Interactive sonic experiences.

{{% note %}}
Wekinator, with its interactive machine learning (IML) capabilities, has a wide array of applications in music, especially in live settings. Here are some examples of Wekinator in action:

*   **Live Performance**: Wekinator facilitates the dynamic manipulation of sound through body movement. For example, a performer can control the EQ on a synthesizer patch using the downward motion of an aerial dancer. Performers can also use Wekinator to create unique controller mappings during a performance, broadening the sonic space and enabling expressive play. Specifically, Wekinator may be used to control reverb and other sound parameters using hand motions.
*   **Instrument Augmentation**: Wekinator can classify different playing techniques, such as bow articulations, in real-time. The Wekinator, coupled with a sensor bow (K-Bow), enables musicians to build their own gesture models and employ them in various ways in their work. This creates opportunities for **smarter instrument interfaces**, such as smart bow tracking for expressive cello performance.
*   **Sound Art and Interactive Installations**: Wekinator is useful in creating interactive sound installations and experiences. For example, it has been used in installations where light sensors embedded in tree bark drive sound synthesis parameters through Wekinator-created models. The interactive nature of Wekinator, where users can train models and observe the results in real-time, facilitates experimentation and the creation of engaging, responsive sound environments.

Overall, Wekinator's ability to translate complex data streams into musical control, combined with its interactive and adaptable nature, makes it a valuable tool for musicians and sound artists seeking to expand their creative possibilities in live performance, instrument design, and interactive installations.

{{% /note %}}

---

## Gesture Recognition & Sound Interaction

- **How does gesture-based control work?**
  - **Motion sensors** (IMU, webcam, Leap Motion, Kinect) capture movement.
  - **Machine learning classifies gestures** (e.g., "fast motion = loud sound").
  - **Outputs control sound synthesis** in real time.

---

### Kinect x Wekinator x Touchdesigner Audiovisual Demonstration

<iframe width="560" height="315" src="https://www.youtube.com/embed/0gwJdzd6Gng?si=I3KzhVT4ws7GiF9r" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

---

## From the Waters (2012)

**Performed by:** PLOrk  
**Composer:** Anne Hege  
**Tools Used:** GameTrak Tether Controllers, ChucK Programming Language, and the Wekinator  

<iframe width="560" height="315" src="https://www.youtube.com/embed/aGjNbzWLVMA?si=tU1unxT6wBxm24aQ" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

{{% note %}}
Here are the key details about *From the Waters*, an interactive sonic experience by Anne Hege and Sideband:

### **Composition and Performance**
- Created by **Anne Hege** and performed by the ensemble **Sideband**.
- Uses **Wekinator**, a machine learning tool, to interpret performers' gestures into musical outputs.
- Employs **GameTrak-controlled instruments**, which respond to performers' movements for real-time expressive control.
- Focuses on an **interactive and dynamic auditory experience** through performer-computer collaboration.

### **Conceptual Foundation**
- Inspired by **deep listening practices** and designed as an **ensemble listening exercise**.
- Aims to aid in the **grieving process**, emphasizing the therapeutic potential of interactive music-making.
- Encourages **collective listening and emotional engagement** through improvisation and machine interactivity.

### **Technical Implementation**
- **Wekinator** is used to map **gestures to sound**, creating a seamless interaction between human movement and machine-generated music.
- Allows performers to **train the system in real time**, adapting the sonic output based on learned movement patterns.
- Utilizes **supervised learning techniques** such as **neural networks, linear regression, and polynomial regression** for gesture recognition.

This project represents a **fusion of human expression and machine learning**, expanding the possibilities of live electronic music performance.

{{% /note %}}

---

## Michelle Nagai — MARtLET

<iframe title="vimeo-player" src="https://player.vimeo.com/video/19980514?h=c5cdf1479c" width="640" height="360" frameborder="0"    allowfullscreen></iframe>

{{% note %}}


*   The MARtLET is an instrument created by Michelle Nagai.
*   It uses **light sensors embedded in tree bark to drive sound synthesis parameters**.
*   The MARtLET uses **Wekinator-created models** to translate the sensor data into sound.
*   The MARtLET is a project that exemplifies the use of Wekinator in **interactive sonic experiences**.

{{% /note %}}

---

### Laetitia Sonami playing and discussing the Spring Spyre in her NIME 2014 Keynote

<iframe width="560" height="315" src="https://www.youtube.com/embed/aMYYbelPTuc?si=vCi_h9YDXa9tiyK2" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

{{% note %}}

In her 2014 NIME keynote, Laetitia Sonami introduced the Spring Spyre, an instrument she developed to explore unpredictability in performance. This marked a shift from her previous work with the Lady's Glove, focusing on embracing inefficiency and unpredictability in musical expression. 

**Design and Functionality**

- **Construction**: The Spring Spyre features a metal ring with three thin springs attached to audio pickups from reverb units. citeturn0search5
- **Sound Generation**: Movements of the springs produce audio signals processed in Max/MSP. citeturn0search8
- **Machine Learning Integration**: Utilizes neural networks via Wekinator to map gestures to sound synthesis parameters. citeturn0search8

**Philosophical Approach**

Sonami emphasizes transitioning from control-based systems to exploration-based systems, valuing unpredictability and inefficiency in performance. citeturn0search1

**NIME 2014 Keynote Performance**

During the keynote, Sonami demonstrated the Spring Spyre's capabilities, highlighting its responsive and exploratory nature. A recording of this performance is available online. citeturn0search0

For a visual demonstration, you can watch the performance here:

{{% /note %}}

---

## The Snakinator: A Bio-Inspired Interactive Music System

<iframe width="560" height="315" src="https://www.youtube.com/embed/mf-0nQWWrRw?si=5dGtQm9QZFBUbTQW" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

{{% note %}}
The "Snakinator" is an interactive music system developed during a seminar led by Rebecca Fiebrink at Princeton University. This innovative project maps the movements of a live snake to an FM synthesis space, allowing the snake's natural motions to influence and generate musical output. By utilizing real-time data from the snake's behavior, the system creates a unique and dynamic auditory experience, blending biological movement with electronic sound synthesis.

{{% /note %}}

---

## Sonification – Data into Sound

- **What is sonification?**
  - The process of turning **data into sound** for artistic or scientific purposes.
- **Examples:**
  - **Genomic Data Sonification** – Sonifying DNA sequences.
  - **Biodata Sonification** – Transforming brainwaves or environmental sounds into music.

---

## COVID-19 Genomic Navigator

<iframe src="https://assets.pubpub.org/1te0fkzu/71648862145927.mp4" width="560" height="315" frameborder="0" allowfullscreen></iframe>

{{% note %}}

### **COVID-19 Genomic Navigator: Key Points**

- **Overview**:  
  - Electronic musical instrument using a **motion-sensing glove** to **sonify COVID-19 protein genomic data**.

- **Data Source**:  
  - Extracted from **NCBI** and **Protein Data Bank (PDB)**.  
  - Uses three datasets: **7B3C, 7D4F, 7KRP** (RNA-dependent RNA polymerase structures).  

- **Sonification Process**:  
  - Data formatted into **prn/csv files**, processed in **Max** and sent via **OSC to Kyma**.  
  - **3D structure** mapped using **spherical binaural panner** for immersive sound positioning.  

- **Motion Sensing Glove**:  
  - Captures **hand gestures** via **Arduino**, sends data to **Max** via OSC.  
  - Controls **synth parameters** in **Kyma**, with **machine learning** aiding gesture recognition.  

- **Performance**:  
  - Uses **categorized gestures** (for gesture recognition) and **non-categorized gestures** (for musical expression).  

- **Protein Structures & Drugs**:  
  - **7B3C**: SARS-CoV-2 RdRp with **Remdesivir**.  
  - **7D4F**: COVID-19 RdRp bound to **Suramin**.  
  - **7KRP**: RNA backtracking & transcription.  
  - **Remdesivir & Suramin**: Inhibit enzymatic activity, RNA replication & transcription.  

- **Musical Expression**:  
  - Contrast between **protagonist** and **antagonist** proteins shapes musical structure.  
  - Gesture recognition in a **machine learning model** triggers musical events.  

- **Instrumental Sonification**:  
  - Explores electronic musical instruments in **physical form**, with potential for **non-physical** expansions.  

- **Potential Applications**:  
  - Accepts **different genomic data (PDB format)** for customized sonification.  
  - Allows comparisons with **SARS-CoV, influenza viruses, etc.**  

- **Ecological Genomics**:  
  - Sonifies genetic mechanisms, integrating **bioinformatics** and **ubiquitous computing**.  
  - Potential contribution to **ecological genomics research**.  

{{% /note %}}

