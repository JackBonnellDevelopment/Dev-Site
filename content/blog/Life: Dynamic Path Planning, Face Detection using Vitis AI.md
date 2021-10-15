+++
author = "Jack Bonnell"
title = "Life: Dynamic Path Planning, Face Detection using Vitis-AI"
date = "2021-10-15"
description = "Dynamic Path planning processes and ideas and my thought process behind my latest tutorial"
tags = [
    "Xilinx",
    "Kria",
    "FPGA",
    "PAth Planning",
    "Face Tracking"
]
+++

# Life: Dynamic Path Planning, Face Detection using Vitis-AI
While creating a new tutorial around face tracking on the KV260, I have been working out how to implement a dynamic path planning structure from scratch this week.

![Faces](/img/face_tracking_front.png)


## Dynamic Path Planning
Working on autonomous movement sometimes is not as linear as it seems. When working with Ackerman Steering, you have to factor in that you need smooth flowing movements to counteract jittering with a more common tank-based steering model.

The first step taken was to create smooth flowing lines from waypoints. Splines can smooth out harsh angles in path planning the same way they work in graphical representations.

Once I achieved this first step, I then looked into the real-time dynamic processing of obstacles. Redirecting the robot on "No Go Zones" dynamically created from detected obstacles within the area.

![Path Planning Results](/img/Path_Planning.gif)

As you can see, this is in the initial stages of development, but I have happy with the concept currently being implemented and looking forward to seeing the results of my complete solution.

## Face Detection Using Vitis-AI

This week I have been working on my Vitis-AI tutorials using the new Vitis 1.4 libraries based on the Densbox 320x320 algorithms supplied by Xilinx.

The current implementation takes a webcam feed through the OpenCV library and resizes it to fit the DenseBox 320x320 resolution. The image passed through the inference function within the Vitis-AI Library, the resulting regions of interest are then drawn onto the image and passed to the GUI window.

![Face Tracking Results](/img/facetracking.gif)

My next step is to look into DMA to pass the MIPI connection directly from the FPGA to the CPU through direct memory access, meaning I can create a Vitis vision IP block. The IP block resizes the image on the FPGA side without CPU processing allowing for minimal latency.

you can check out my tutorial here: [Xilinx Kria KV260 - Vitis-AI 1.4 Face Detection]

[Xilinx Kria KV260 - Vitis-AI 1.4 Face Detection]: https://www.hackster.io/jack-bonnell2/xilinx-kria-kv260-vitis-ai-1-4-face-detection-90f914