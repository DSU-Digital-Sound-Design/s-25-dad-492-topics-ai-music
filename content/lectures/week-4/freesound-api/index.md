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