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


# Week 9 (3/10): Spring Break – No Class
  
# Week 10 (3/17)

## Tuesday 

- [Etude 3](../projects/#etude-3---interactive-machine-learning-with-wekinator) Workshop and explanation
- **Etude 3 Due**: Friday 3/28.
  - See the [resources page](../lectures/week-10/iml-resources/) for more documentation on Wekinator and IML. 

## Thursday 

- **No Class**: 3/20 (MoxSonic).
- Next week we'll work more on Etude 3 and start talking about the final project.
  
# Week 11 (3/24)

## Tuesday 

- Interactive Machine Learning Workshop for [Etude 3](../projects/#etude-3---interactive-machine-learning-with-wekinator) - Due on Friday
  - Show me what you're working on and what problems your'e running in to 

## Thursday 

- no class - travel 

# Week 12 (3/31)

## Tuesday 

- Show Etude 3
- Introduce final project 

> Note: Until the end of the semester we'll do project work on Tuesdays and reading discussions on Thursdays. Look at the schedule to see what we'll be discussing on that day and what you'll need to be prepared to speak about. 

## Thursday 

- [Aaron Hertzmann (2023) – What is Creativity? Can Computers Be Creative?](https://aaronhertzmann.com/2023/09/27/what-is-creativity.html)
  - Hertzmann clearly outlines the philosophical and practical challenges of calling AI “creative.” It's accessible and provocative, and sets the tone for critically engaging with AI-generated music as art.
- Discussion Questions:
  - What do you define as creativity?
  - Can a machine be creative without intention or awareness?
  - How does this reading shape your view of AI-generated music?
  
# Week 13 (4/7)

## Thursday 

- [Selim Tan (2024) - Are We All Musicians Now? Authenticity, Musicianship, and AI Music Generator Suno](https://osf.io/preprints/socarxiv/4nt8z_v1)
  - Selim Tan critically explores how Suno, an AI music generator, challenges traditional notions of authenticity, authorship, and musicianship by enabling users to create music through prompts, raising questions about creativity, ownership, and the evolving meaning of being a musician.
- Discussion Questions: 
  - Can users who generate music through prompts in Suno be considered musicians, and how does this challenge or expand traditional definitions of musicianship?
  - In what ways might the lack of transparency in Suno’s training data affect the perceived authenticity and ethical legitimacy of its musical outputs?
  - How does Suno's ability to turn everyday experiences into music through text, audio, image, or video prompts reflect or reshape the concept of musical expression and personal identity?



# Week 14 (4/14)

## Thursday 

- [Nguyen & Mateescu (2024) – Generative AI and Labor: Power, Hype, and Value at Work](https://datasociety.net/wp-content/uploads/2024/12/DS_Generative-AI-and-Labor-Primer_Final.pdf)
  - This piece connects directly to questions of automation, creative labor, and what gets erased in the hype cycle. It emphasizes structural critiques over technical ones.
- Discussion Questions:
  - Who benefits and who loses in the shift to AI-generated media?
  - How might this change the role of the musician or sound designer?
  - How do you see labor (or the lack of it) in AI music tools? 

# Week 15 (4/21)

## Thursday 

- [Pelly (2019) – Big Mood Machine](https://thebaffler.com/latest/big-mood-machine-pelly)  
  - Or [here](../lectures/week-15/Pelly_bigMoodMachine.pdf) if that's paywalled. 
  - This article critically examines how Spotify commodifies listener mood and emotional data to fuel its advertising business, raising concerns about surveillance, manipulation, and the reshaping of music as a background marketing tool.  
- Discussion Questions:  
  - How does Spotify’s use of mood playlists influence what we listen to — and why we listen?  
  - What are the ethical implications of treating emotional data as a product for advertisers?  
  - In what ways does this system affect artists, musical diversity, or creative autonomy?

# Week 16 (4/28)

## Tuesday 

## Thursday 

# **Final Exam Day: Final Presentations**

- **Topics**: Showcase completed projects to peers and possibly an external audience.
- **Activity**: Presentations followed by a class discussion reflecting on course learning goals, creativity, and ethical insights. 
<!--   
- -->

