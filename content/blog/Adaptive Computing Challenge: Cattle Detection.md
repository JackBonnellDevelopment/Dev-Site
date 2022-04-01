+++
author = "Jack Bonnell"
title = "Adaptive Computing Challenge: Cattle Detection"
date = "2022-04-01"
description = "My entry into this year Adaptive Computing Challenge"
tags = [
    "Xilinx",
    "Kria",
    "FPGA",

]
+++


# Adaptive Computing Challenge: Cattle Detection

For this year's [Adaptive Computing Challenge] I want to pursue Agri-tech. Argi-tech is a sector I have been interested in for some time. This is the first time I have been able to work on a project from a hobbyist standpoint.

![Cow Detected](/img/cow_detect.gif)

The idea I had for this project was being able to keep track of large amounts of cattle using a drone that can identify cattle and then track individual cows around a set area.

## Inital Design

Sadly after leaving my last job I lost access to a lot of tools that would have allowed me to collect data for custom datasets. luckily this wasn't an issue as the Vitis Zoo Model library had a TFSSD dataset that included cows. This meant I did not need to train my custom dataset! 

Result!

So for my Proof of Concept I wanted to use Kernelized Correlation Filters. This would allow me to use the detected cow as a Region of Interest. With the ROI an initial tracking object can be selected that allows the KCF to follow where exactly the cow is whilst also allowing me to attach a unique identifier to the cow being tracked.

## How could this be used in Agri-tech?

The idea behind this system is that with the use of a depth camera such as the Oak-D Lite. Depth Perception could be used to detect the width of pixels from the tracked cows allowing the software to give real-time data regarding the size and length of the cow that is being tracked.

![Detect Markings](/img/cow_mask.png)

The software could have the ability to apply a negative mask to the ROI allowing for the cow to be identified in real-time by the markings on its back. This is possible as all Dairy Cow markings are unique, allowing for historical records of cows to be documented for farmers to keep track of growth.

## Future Plans

I will be building out this to take more advantage of the FPGA on the kv260 moving the KCF algorithm from the CPU to the FPGA along with the use of the [Vitis Vision Library] for FPGA based image masking.

As I do not have access to a depth perception camera I will also be looking into acquiring a second IAS camera that I can use for stereo camera functionality within the [Vision Vision Library].

[Vision Vision Library]: https://www.xilinx.com/products/design-tools/vitis/vitis-libraries/vitis-vision.html

[Adaptive Computing Challenge]: https://www.hackster.io/jack-bonnell2/xilinx-kv260-vitis-ai-1-4-cattle-tracking-16a404