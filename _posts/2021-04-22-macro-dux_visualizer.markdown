---
layout: post
title:      "Macro-Dux Visualizer"
date:       2021-04-22 13:59:24 +0000
permalink:  macro-dux_visualizer
---


 As a music producer, one of my go to software synthesizers is Massive by Native Instruments. A standout feature is its set of macro control knobs that can be connected to as many other parameters as you like, granting the user five customizable single points of control. 
The similarities between this and the Redux store are striking, and I thought it would be interesting to implement this macro control paradigm in a React application. I built three (melody, harmony, and bass) synthesizer components that use the Tone.js library. Each of these have parameters that are manipulated by the macros held in the Redux store. The final waveforms of these synthesizers are passed to analyser nodes that feed into the visualizer component. This component was built using the p5.js processing library. It receives the waveform data from the three voices as props, and for each voice renders three concentric circles that are made up of the voice's waveform reflected across the y-axis. The macros in the store also control aspects of the visualizer. Particles shoot out from the three orbs at varying speeds and colors depending on the macro settings. There is also an 'X' made up of waveform data that fades in from the background that is controlled by macro settings.
     While I'm happy with the basic architecture of the project, I ran into some issues on the audio processing side of this application. The synthesizer components clip and pop a fair amount. I have a few guesses as to the cause that I will pursue as I moved this project past it's MVP stage. At first I thought it was gain clipping, but many adjustments and the addition of gain limiter nodes didn't solve the problem. It may have something to do with multiple AudioContexts being present in the same page, which will be tricky to work around with the compartmentalized nature of React but probably doable. Another theory is that the processing necessary for all of the oscillator and effect nodes to run in real time is just over stressing the browser.
     Whatever the source of the issue, this project demonstrates what Redux is best at: maintaining a single source of truth that can be easily disseminated throughout all levels of an application.

