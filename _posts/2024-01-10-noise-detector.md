---
layout: post
title:  "Analogue video noise detection for your FPV footage"
date:   2023-12-16 21:37:00 +0100
categories: [drones]
tags: [fpv, drones, dotnet, wpf, github]
---
Every drone pilot who ever flew analogue drones therefore also Tiny Whoops probably has tons of video footage with a lot of recorded static noise, which is a automatically recorded between batteries. This takes up quite a lot of space, since the video is practically a definition of randomness and there's almost no way to reduce the size of it using jpeg compression.

During the years of my FPV experience I tried different ways to downsize the videos. Obviously reducing resolution and compression helps, but removing the noise parts is more practical.
I've been thinking about a way to remove the noise automatically from the videos, but it's not that straightforward. The computer needs to figure out when the noise starts. I found 2 options.

>I used OpenCV to calculate the difference between frames, by analyzing the whole video. Since when flying and not crashing the frames don't change all that much it works, but the moment the drone hits something, the movement is so rapid, that it recognizes the change.

>The other - use machine learning. I taught a model what noise is. Unfortunately it's dumb enough not to recognize it for different resolutions. So the model needs noise/valid frames from pretty much every type of recorder. Which implies gathering frames from users on the Internet.

In fact neither of these options are great, but they do a good enough job and the app allows noise detection of the whole playlist and merges flights between separate files too. You can of course adjust it manually afterwards.

I posted this thing on a FPV Discord channel of International Game of Whoop (or IGOW, in which I took part in in 2022), but unfortunately ppl complained it works only on Windows. I do have an idea how to implement it for other platforms, but I need to move away from the library I used. I hope to explore this option in the future.

I had fun building it and even built GitHub actions with Semantic-Release, to build new versions of the app on merges, with automatic updates and stuff. Cool experience for a solo project. Besides I did have an Asana project with tasks and regular meetings with my girlfriend to keep track of what has to be built ;)

The app is available on [my github](https://github.com/mkorzunowicz/fpvnoisedetector). Have fun testing it!
