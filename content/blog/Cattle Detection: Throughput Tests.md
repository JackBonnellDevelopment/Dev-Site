+++
author = "Jack Bonnell"
title = "Cattle Detection: Throughput Tests"
date = "2022-04-12"
description = "Initial Benchmarking on KV260 Ready Project Cattle Detect"
tags = [
    "Xilinx",
    "Kria",
    "FPGA",

]
+++

# Cattle Detection: Throughput Tests

After the Adaptive computing Challenge, I've been looking for a new project to keep me busy. Looking back at the Cattle Detection entry for ACC I feel there is a viable open-source opportunity to make a difference in the way Cattle is managed. So I've decided to build on my project entry and transform it from a concept to an open-source building block.

## Validating Throughput

After the Adaptive computing Challenge, I've been looking for a new project to keep me busy. Looking back at the Cattle Detection entry for ACC I feel there is a viable open-source opportunity to make a difference in the way Cattle is managed. So I've decided to build on my project entry and transform it from a concept to an open-source building block.

My first step for this project is to work out theoretical frame rates for the KV260.  Allowing me to scale my project according to the capabilities of the FPGA. There is little point in adding functionality when the latency is the bottleneck!

## Block Design

For my test used a test pattern generator to generate the footage for the VDMA as shown in the image and then used the PYNQ framework to mock up a quick script to configure and run the tests.

![Block Design](/img/block_design_VDMA.png)

## The Results


For the test, I ran the VDMA read in Async mode for 10000 cycles giving the VDMA time to settle and give a more accurate reading. The result was really promising, registering a throughput of 637FPS on 640x480p.

![480p test](/img/480p_VDMA.png)

Even when I tested at 1080P I was still able to get an average of 84 FPS!

![1080p test](/img/1080p_VDMA.png)

But for a more realistic throughput test I used 320x320, this is 320 s the average pixel number for TF_COCO. Which for now, will be the main AI dataset used for detection.

![1080p test](/img/320p_VDMA.png)

These are theoretical values but this test gives you an idea of the power of this FPGA. FPGA will always be limited by the frame rate for the camera and post processing that will occur.
