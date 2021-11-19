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

![IAS Camera](/img/Adaptive_Hardware_Winner.png)

I am happy to announce that I have been chosen to receive free hardware for the Adaptive Computing Challenge for my project working on "Cattle Detection on the edge".



## Utilising Depth Perception

### ON Semi IAS Camera Module
![IAS Camera](/img/IAS_camera.jpg)

One of the main progressions I have made with this year's challenge is to find the best way to utilise depth perception on the KV260. The current accessory pack only supplies one IAS camera module, meaning that I would have to purchase a second Camera priced at approximately £150.

### Stereo USB Cameras
![USB Camera](/img/USB_Camera.jpg)

The next option will be a stereo USB camera such as this [Camera Module]. This would allow me to utilise the stereo functionality on the Vitis vision library. 

My only concern with this method is the robustness of the setup. Gstreamer and the VCU IP block have shown hanging characteristics when running cameras for long periods. Even though this is purely conceptual, it would be nice to work in real-world environments where this would run 24 hours a day, seven days a week.

### Realsense
![Realsense](/img/Realsense.png)

I will be looking into a third method using the Realsense D435i, which I can use for both RGB and Depth imagery. The main issue with Realsense currently is the latency, as Gstreamer does not currently support Realsense. There is a third-party Gstreamer plug-in, but I still need to test its validity to see if it has a positive impact on performance.

[Camera Module]: https://www.amazon.co.uk/Security-Monitoring-Industrial-Equipment-Recorders/dp/B07QXQKH11/ref=asc_df_B07QXQKH11/?tag=googshopuk-21&linkCode=df0&hvadid=372392981517&hvpos=&hvnetw=g&hvrand=12950875273478932173&hvpone=&hvptwo=&hvqmt=&hvdev=c&hvdvcmdl=&hvlocint=&hvlocphy=9046155&hvtargid=pla-820343686028&psc=1&tag=&ref=&adgrpid=79401595434&hvpone=&hvptwo=&hvadid=372392981517&hvpos=&hvnetw=g&hvrand=12950875273478932173&hvqmt=&hvdev=c&hvdvcmdl=&hvlocint=&hvlocphy=9046155&hvtargid=pla-820343686028