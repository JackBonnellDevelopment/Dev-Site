+++
author = "Jack Bonnell"
title = "Life: FPGA work, Huel, Future thoughts"
date = "2021-09-23"
description = "Working with the Kira Starter Kit from Xilinx For the first time"
tags = [
    "Life",
    "Xilinx",
    "Kria",
    "FPGA"
]
+++

# Life: FPGA work, Huel, Future thoughts

This post is just a little weekly round-up of what I have been up to, thoughts and processes I have been working on, and any good and bad life choices.

## FPGA work

This week has been constant. With the release of the Kria board, the race is on to start adapting current processes to work. My current job supports Intel RealSense for computer vision work, so the need for this to be available on the Kria board is paramount.

![Kria KV260 Vision AI Starter Kit](/img/sundance-kria.png)

The way Kria supports its users with creating overlays for products is inherently similar but also different from previous work on boards such as the ZCU104. Our current workflow is to make the Petalinux project based on the XSA file produced through Vivado, creating the bitstream and then using this within Vitis to generate an application accelerated through the FPGA.

I like this procedure. It lowered the development time of projects for computer vision, many of the platforms are the same, and being able to integrate minor tweaks without building an entirely new one.

My main annoyance is lost time with the main bulk of the procedures being self-taught through picking apart example projects etc. Clear documentation or even a flow diagram showing the process phases would have increased my efficiencies.

I created a guide detailing how it is possible to implement LibRealSense, which are the libraries needed to run the RealSense onto the Kria system. Hopefully, this means people who are just starting to adopt the Kria system can plug and play with their Kria system much more effectively.

Guide: [RealSense Support for Kria KV260 PetaLinux 2021.1]

## Huel

![Huel Hot & Savoury](/img/huel.jpg)
Over the years, I have struggled with my work-life balance. It is apparent in my food intake. I often find myself working through lunch and then snacking all afternoon. I need to find a source of food that does not consist of noodles inside of a plastic container.

I did a bit of research and came across Huel. As I'm not a big fan of cold drink food substitutes, I've decided to go with the "Hot and Savoury" range.

Initial thoughts on the products are positive they taste delicious, and they're nutritionally balanced. The proof will be in the long term use as I have a terrible habit of going off flavours quickly.

## Future Thoughts

I am currently looking at the possibility of implementing Gstreamer for RealSense. This will increase the frame rate available on the Kria. Getting this to work at 20FPS for the RealSense will be a great precursor to creating a RealSense library that's accelerated on the FPGA.

Life wise-looking forward to seeing if this Huel positively impacts my life, allowing me to keep pushing with the Kria System. Allowing me to create some impactful projects for both industry and hobbyists alike.

## Key Goals for the Near Future

* Create first inital ROS2 KRS vision package for the Realsense.

* Apply vision accelerated for the Realsense using Gstreamer.

* Create another project on how to create application in vitis and petalinux.



[RealSense Support for Kria KV260 PetaLinux 2021.1]: https://www.hackster.io/jack-bonnell2/realsense-support-for-kria-kv260-petalinux-2021-1-f5dbe3