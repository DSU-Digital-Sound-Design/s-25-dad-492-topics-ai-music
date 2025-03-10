---
title: "Schedule"
date: "2021-01-02"
author: ""
---

{{< toc >}}

# Week 1 (1/13): Introduction to AI and Creativity

## Tuesday

- Syllabus Review
- **Topics**: Overview of course themes, questions: “What does it mean to make music with AI?” and “Is this even a good idea?”
- **Key Concepts**: Brainard’s creativity framework (novelty, value, agency, curiosity).
- Discussion
  - When you hear the term 'AI music,' what comes to mind?
  - What are some examples of how you think AI might be used to create music?
  - What are your initial feelings or reactions to the idea of AI creating music?
- Listen to some tracks from [Suno](https://suno.com/) and [AIVA](https://www.aiva.ai/).
  - Take some notes on what you hear and how you feel about it. Focus on musical elements. 
- Discussion
  - What aspect of the music helped you tell that it was created by an AI system?
  - Would you listen to any of this music again? Why or why not?
  - What's the place of music like this in society?


> **For next class**: Read Brainard’s *Introduction* and *Section 2.1*. 
> Download [here](https://philpapers.org/archive/BRATCC-9.pdf)

## Thursday 

- **Reading**: Brainard’s *Introduction* and *Section 2.1*.
  - [slides](../lectures/week-1/brainard-intro-2.1/)
- Prepping for the etudes
  - [Intro to Tone.js (Web Audio API)](../lectures/week-1/tonejs-intro) 

# Week 2 (1/20): Foundations of AI in Music

## Tuesday

- No class - (out of town for Professional Development)

<!-- - **Topics**: GOFAI techniques (rule-based systems, algorithmic composition) and their relevance today.
- **Activity**: Analyze algorithmic compositions for novelty. -->
  
## Thursday

- **Assignment**: Etude 1 (word2vec Poetry).
- [Intro to word2vec](../lectures/week-2/word2vec-intro)
- Mapping word embeddings to musical features
- **Etude due 2/4** - [Etude 1: Sonic Poetry Generator](../projects#etude-1-sonic-poetry-generator)
  
> **For next class** read Brainard’s *Section 2.2* (Novelty) and *Section 2.3* (Value).

# Week 3 (1/27): Hands-On with word2vec

## Tuesday 

- **Topics**: Generative poetry and interactive systems using word2vec.
- [Tone.js Presets](https://www.guitarland.com/MusicTheoryWithToneJS/Presets-gh-pages/)
- Helpful p5.js functions 
  - [map](https://p5js.org/reference/p5/map/)
  - [ceil](https://p5js.org/reference/p5/ceil)
  - [floor](https://p5js.org/reference/p5/floor)
  - [random](https://p5js.org/reference/p5/random)
  - [text](https://p5js.org/reference/p5/text)
- Continue with 
  - [Intro to word2vec](../lectures/week-2/word2vec-intro)
- Show instructions for [Etude 1: Sonic Poetry Generator](../projects#etude-1-sonic-poetry-generator)

## Thursday

- Demoing Additions to Etude 1
  - Timbre Evolution
  - Musical Intervals
  - Carter demo? 
- Etude 1 Workshop
- **Etude 1 Due**: 1/31.
  
<!-- - **Assignment**: Reflection: "What is creativity in AI systems?" -->
# Week 4 (2/3): Machine Learning for Music

## Tuesday

- A few students show their etude 1 projects
- **Topics**: MIR techniques (k-NN, SVM, HMM) and applications in feature extraction and classification.
  - [slides](../lectures/week-4/machine-learning-for-music/)

## Thursday 

- Finish MIR techniques discussion 

<!-- 
- **Reading**: Brainard’s *Section 2.4* (Agency).
- **Assignment**: Etude 2 (Genre Classifier and Audio Mosaic). -->
  
# Week 5 (2/10): Audio Feature Extraction

## Tuesday

- [Freesound API](../lectures/week-4/freesound-api)

## Thursday

- [Text and Content Search](../lectures/week-5/freesound-api-search)
- Check out Etude 2 - [Audio Mosaic](../projects#etude-2---audio-mosaic)
  - Due 2/25 before class starts


<!-- - **Topics**: Extracting timbre, pitch, and rhythm features; training classifiers for genre identification.
- **Key Concepts**: Agency and ethical implications of automated systems.
- **Activity**: Debate: “Does automation devalue human musicianship?”
- **Reading**: Supplemental article on copyright and AI. -->
  

# Week 6 (2/17): Creative Audio Manipulation

## Tuesday


- implementing the audio mosaic
- More examples of sequencing with Tone.js 
  - see: [Total Serialism](https://github.com/tmhglnd/total-serialism)
  - [Tone.js Sequencing](../lectures/week-6/sequencing-with-tonejs)

## Thursday

- Check out the updated content search example
- More Tone.js sequencing examples
  - [Tone.js Sequencing](../lectures/week-6/sequencing-with-tonejs)
- implementing the audio mosaic
- Sharing in progress work?

# Week 7 (2/24): Interactive Machine Learning and HCI

## Tuesday

- Etude 2 presentations 
- **Topics**: Wekinator and humans-in-the-loop systems.
  - [slides](../lectures/week-7/hil-wekinator-intro/)
- **Key Concepts**: Human agency in collaborative systems; impact of AI on musicians.

## Thursday

- finish slides from Tuesday
- More in depth with Wekinator - theory and practice 
  - Install Wekinator [here](http://www.wekinator.org/downloads/)
  - Look at [overview](http://www.wekinator.org/instructions/)
  - Go through [walkthrough](http://www.wekinator.org/walkthrough/)

<!-- - **Activity**: Analyze AI-generated works for balance between human and AI contributions. -->
<!-- - **Reading**: Brainard’s *Section 2.5* (Curiosity). -->
<!-- - **Assignment**: Etude 3 (Wekinator Interactive Toys). -->


# Week 8 (3/3): Designing Interactive AI Systems

## Tuesday

- Finish going through [Wekinator](http://www.wekinator.org/walkthrough/) walkthroughs 
- [Wekinator to Reaper](../lectures/week-8/wek-reaper/)

## Thursday

- **Assignment**: Etude 3 (Wekinator Interactive Toys).
- [Face and Body Tracking](https://github.com/tatecarson/facetrack-test)

<!-- 
Ideas: in reaper have wekinator control the jog rate of the cursor in the timeline then record with birdbird. 
 -->

<!--   
- **Topics**: Building Wekinator-based prototypes.
- **Key Concepts**: Balancing human involvement and AI autonomy in creative processes.
- **Reflection**: “What level of human involvement is needed for creativity?”


## **Week 9 (3/10): Spring Break – No Class**
  
## **Week 10 (3/17): AI and Deep Learning for Music**
- **Topics**: RNNs, GANs, VAEs, transformers for music generation.
- **Key Concepts**: Preserving cultural authenticity in AI models.
- **Activity**: Explore culturally specific music datasets and discuss ethical guidelines for their use.
- **Etude 3 Due**: 3/19.
- **No Class**: 3/20 (MoxSonic).
  
## **Week 11 (3/24): Final Project Introduction**
- **Topics**: "Escaping the Turing Trap"—conceptualizing systems for human-AI collaboration.
- **Key Concepts**: Ethical considerations: copyright, cultural authenticity, and human impact.
- **Activity**: Begin brainstorming and prototyping.
- **Reading**: Assign supplemental paper on cultural representation in AI.
  
## **Week 12 (3/31): System Design for AI and Music**
- **Topics**: Discriminative vs. generative systems; inclusive and ethical design principles.
- **Activity**: Draft project proposals addressing ethical challenges.
  
## **Week 13 (4/7): Progress Check-In**
- **Topics**: Peer feedback and collaborative critique on prototypes.
- **Key Concepts**: Balancing automation and human interaction in design.
- **Activity**: Discuss how projects align with ethical guidelines.
  
## **Weeks 14-16 (4/14 – 4/28): Final Project Work**
- **Topics**: Refinement and implementation of final projects.
- **Key Concepts**: Iterative design, agency, and ethical considerations.
- **Activity**: In-class work sessions, one-on-one consultations with the instructor, peer reviews.
  
## **Final Exam Day: Final Presentations**
- **Topics**: Showcase completed projects to peers and possibly an external audience.
- **Activity**: Presentations followed by a class discussion reflecting on course learning goals, creativity, and ethical insights. -->

