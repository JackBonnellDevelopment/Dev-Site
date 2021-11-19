+++
author = "Jack Bonnell"
title = "Adaptive Computing Challenge: Week 1"
date = "2021-11-19"
description = "the first in a hopefully weekly report on my Adaptive Computing Challenge project"
tags = [
    "Xilinx",
    "Kria",
    "FPGA",

]
+++

# Adaptive Computing Challenge: Week 1

I am happy to announce that I have been chosen to receive free hardware for the Adaptive Computing Challenge for my project working on "Cattle Detection on the edge".

## Utilising Depth Perception

### ON Semi IAS Camera Module
![IAS Camera](/img/IAS_camera.jpg)

One of the main progressions I have made with this year's challenge is to find the best way to utilise depth perception on the KV260. The current accessory pack only supplies one IAS camera module, meaning that I would have to purchase a second Camera priced at approximately £150.

### Stereo USB Cameras
![USB Camera](/img/USB_Camera.jpg)

The next option will be a stereo USB camera such as this camera module. This would allow me to utilise the stereo functionality on the Vitis vision library. 

My only concern with this method is the robustness of the setup. Gstreamer and the VCU IP block have shown hanging characteristics when running cameras for long periods. Even though this is purely conceptual, it would be nice to work in real-world environments where this would run 24 hours a day, seven days a week.

### Realsense
![Realsense](/img/Realsense.png)

I will be looking into a third method using the Realsense D435i, which I can use for both RGB and Depth imagery. The main issue with Realsense currently is the latency, as Gstreamer does not currently support Realsense. There is a third-party Gstreamer plug-in, but I still need to test its validity to see if it has a positive impact on performance.