+++
title = "Tone.js Introduction"
outputs = ["Reveal"]
[logo]
src = "github-logo.png"
[reveal_hugo]
custom_theme = "reveal-hugo/themes/robot-lung.css"
margin = 0.2
separator = "##"
+++

## Introduction to Tone.js and Glitch

- [Tone.js](https://tonejs.github.io/) is a JavaScript library for creating interactive audio applications.
- [Glitch.com](https://glitch.com) is a platform for quick prototyping and hosting web apps.

{{% note %}}

- Tone.js enables developers to create sounds and music directly in the browser, making it ideal for web-based audio projects. 
- Glitch is beginner-friendly, allowing students to code collaboratively and deploy apps effortlessly. 
- The goal is to combine the power of Tone.js and Glitch to create dynamic and interactive sound experiences.
- By the end of this session, students will have a working Tone.js-based project and a foundational understanding of its key concepts.

{{%/ note %}}

---

## Getting Started with Glitch 

- Visit Glitch.com and sign up or log in.
- [Fork](https://glitch.com/edit/#!/tonejs-starter-1) a starter project with Tone.js preloaded.
- Explore key project files: `index.html`, `script.js`, and `style.css`.
- Look at glitch live updates and collaborative coding. 

{{% note %}}

- Guide students to create or fork projects effortlessly on Glitch, a crucial step for collaborative coding. 
- Use a pre-prepared starter template that links Tone.js to ensure students focus on learning without setup frustrations.
- Walk through the basic file structure, highlighting where to write HTML, CSS, and JavaScript.
- Highlight the real-time updating feature in Glitch that simplifies debugging and experimentation.

{{%/ note %}}

---

## Basic Tone.js Example 

**Open script.js and add the following example to play a simple sound:**
```js
const synth = new Tone.Synth().toDestination();

document.getElementById("playButton").addEventListener("click", () => {
  synth.triggerAttackRelease("C4", "8n");
});

```

**Update `index.html` to add a button element.**
```html
<button id="playButton">Play Sound</button>
```



{{% note %}}

- Introduce students to the core Tone.js feature: creating and triggering sounds using a Synth object. 
- Example: Clicking a button triggers a note, providing instant feedback for students.
- Debugging together helps students understand common mistakes and the collaborative spirit of coding.
- Ensure everyone successfully hears the sound to build confidence and engagement.

{{%/ note %}}

---

## Experimentation with Tone.js

- Now try to modify the example to play different notes or durations.
- Add multiple buttons for unique sound triggers.

**Optional `Tone.Loop`**

```js   
const loop = new Tone.Loop((time) => {
  synth.triggerAttackRelease("E4", "8n", time);
}, "4n").start(0);

Tone.Transport.start();
```

{{% note %}}

- Encouraging experimentation helps students engage with Tone.js creatively, applying what they’ve learned.
- For example, students can replace "C4" with "G4" to hear the difference in pitch or explore timing variations.
- Introduce optional looping to show how Tone.js can handle more complex timing and patterns.
- Provide hints to foster learning but encourage students to troubleshoot independently.

{{%/ note %}}

---

## Wrap-Up and Next Steps 

- Check out the [Tone.js documentation](https://tonejs.github.io/docs/) for more features and examples.
  

{{% note %}}

- Recap the session’s highlights, ensuring students understand how to create sounds with Synths and control timing using Tone.js. 
- Emphasize the value of Glitch for sharing and collaboration, empowering students to work on projects together.
- Encourage exploring more advanced features like `PolySynth` or adding effects for homework to deepen their learning.
- Build excitement for the next class by showcasing the possibilities of Tone.js.

{{%/ note %}}

---

## Extra Time?

**Reverb**

```js
const reverb = new Tone.Reverb(0.5).toDestination();
synth.connect(reverb);
```