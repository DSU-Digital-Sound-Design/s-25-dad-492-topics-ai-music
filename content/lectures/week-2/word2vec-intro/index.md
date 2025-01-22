---
title: "Word2vec Intro"

---

 ## Step 1: Basic Word Display
 Let's start with the simplest version - displaying a word and finding related words using word2vec. This establishes our foundation. This first step introduces the core concepts of
- Setting up a basic p5.js canvas
- Loading the word2vec model
- Creating a simple user interface
- Finding and displaying related words

> Try running this code and enter different words to see their associations. Notice how we're just randomly positioning the related words on the canvas for now.


<!-- Copy and Paste Me -->
<div class="glitch-embed-wrap" style="height: 420px; width: 100%;">
  <iframe
    src="https://glitch.com/embed/#!/embed/1-basic-waveform-word2vec?path=TODO.md&previewSize=0"
    title="1-basic-waveform-word2vec on Glitch"
    allow="geolocation; microphone; camera; midi; encrypted-media; xr-spatial-tracking; fullscreen"
    allowFullScreen
    style="height: 100%; width: 100%; border: 0;">
  </iframe>
</div>

## Step 2: Adding Basic Sound
Now let's add our first synthesizer to create sound when words appear. We'll start with just a simple melody synth.UntitledClick to open codeIn this second step, we've added:

- A basic synthesizer using Tone.js
- A mapping between word similarity and musical notes
- Sequential playback of notes as words appear
- Visual sizing of words based on their similarity

The words now play notes when they appear, with more similar words playing higher notes. Try different words and notice how the sound helps represent the semantic relationships.

<div class="glitch-embed-wrap" style="height: 420px; width: 100%;">
  <iframe
    src="https://glitch.com/embed/#!/embed/2-adding-basic-sound?path=script.js&previewSize=0"
    title="2-adding-basic-sound on Glitch"
    allow="geolocation; microphone; camera; midi; encrypted-media; xr-spatial-tracking; fullscreen"
    allowFullScreen
    style="height: 100%; width: 100%; border: 0;">
  </iframe>
</div>


## Step 3: Adding Chords and Effects
Let's enhance the musical experience by adding chord progressions and audio effects.UntitledClick to open codeIn this third step, we've added:

- A chord progression that cycles continuously
- Reverb and delay effects for depth
- Fade-out animations for the words
- Rhythmic variations in the melody

Notice how the chords create a harmonic foundation while the melody notes dance on top. The audio effects add space and atmosphere to the sound.

<!-- Copy and Paste Me -->
<div class="glitch-embed-wrap" style="height: 420px; width: 100%;">
  <iframe
    src="https://glitch.com/embed/#!/embed/3-adding-chords-and-effects?path=script.js&previewSize=0"
    title="3-adding-chords-and-effects on Glitch"
    allow="geolocation; microphone; camera; midi; encrypted-media; xr-spatial-tracking; fullscreen"
    allowFullScreen
    style="height: 100%; width: 100%; border: 0;">
  </iframe>
</div>

## Step 4: The Final Poetry Generator
Now we're ready to combine everything into the final poetry generator. You can find this complete version in the original code, which adds:

- Structured poetry generation with stanzas and lines
- More sophisticated word selection
- Coordinated visual and musical elements
- Advanced animation effects

Each step builds upon the previous one, helping you understand how the pieces fit together. Try running each version, experiment with the code, and make your own modifications. You might:

- Change the chord progression for a different mood
- Modify the animation effects
- Adjust the timing of word generation
- Create different visual layouts
- Experiment with different synthesizer settings



<!-- Copy and Paste Me -->
<div class="glitch-embed-wrap" style="height: 420px; width: 100%;">
  <iframe
    src="https://glitch.com/embed/#!/embed/4-everything-together-word2vec?path=&previewSize=0"
    title="4-everything-together-word2vec on Glitch"
    allow="geolocation; microphone; camera; midi; encrypted-media; xr-spatial-tracking; fullscreen"
    allowFullScreen
    style="height: 100%; width: 100%; border: 0;">
  </iframe>
</div>