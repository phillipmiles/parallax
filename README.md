# Parallax Controller
Reusable module for handling parallax websites. The module makes use of a set and forget process. At initialisation you need to provide the module with an array of detailed Javascript objects dictating how the various parallax elements should behave. Then the parallax controller takes care of the rest.

**View demo https://phillipmiles.github.io/parallax-controller/**

This module uses many of the parallax best practices outlined by Dave Gamache here https://medium.com/@dhg/parallax-done-right-82ced812e61c. I've also included and extended upon parts of his code found here https://medium.com/@dhg/parallax-done-right-82ced812e61c. Main improvements made in this version include more granular control over animation timings as well as support for the parallax to initialise correctly no matter what scroll position the page loaded in at.

## Setup and use
1. You will need JQuery for the module to work.
2. Download and link the parallaxController.js file into your project.
3. Simply run var parallax = parallaxController(scenes); where 'scenes' is your scenes array as described below.
4. You'll probably want to set your wrapper elements specified in the scenes to have the CSS property position: fixed; so that all animation is getting handled by the parallax controller rather than throwing the natural page scroll into the mix.

## Scenes
Each object within the array that gets passed to the module details the script for a scene. Each scene contains the following...
- **wrapper** - The wrapper element in the DOM that contains all the parallax elements relavent for that scene.
- **duration** - The duration it takes for the scene to reach it's end. This is set as a percentage of the viewport height - remember that time or the duration in a parallax site is set by the user scrolling. A 100% duration means the scene will last until the the user has scrolled down the page a length equal to the height of the viewport.
- **animations** - An array of objects where each object describes the animation of a single specific element in the DOM. The animation's duration is equal to the scenes duration.

## Animations
< TODO! >

## Functions
A couple of simple getter functions are available from the controller.

- **getCurrentScene** - Returns the index of the active scene from the inital scenes array passed into the controller.
- **getCurrentWrapper** - Returns the active scene's wrapper element's ID. 
- **getTotalDuration** - Returns the total vertical scroll duration for all scenes. This is returned in pixels.

## Issues
- Resizing the browser breaks the calculations made at initialisation.
