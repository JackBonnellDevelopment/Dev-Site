+++
author = "Jack Bonnell"
title = "Kria: Initial Thoughts"
date = "2021-09-17"
description = "Working with the Kira Starter Kit from Xilinx For the first time"
tags = [
    "Xilinx",
    "Kria",
    "FPGA"
]
+++

# Kria Starter Kit

Kria **Recently** released the [Kria KV260 Vision AI Starter Kit], a SOM with the added benefit of a FPGA. Different in the fact that you should technically be able to add a 12v power supply and run AI models to your heart's content.

![Kria KV260 Vision AI Starter Kit](https://www.xilinx.com/content/xilinx/en/products/som/kria/_jcr_content/root/parsystop/xilinxflexibleslab/xilinxflexibleslab-parsys/xilinxcolumns/childParsys-0/xilinximage.img.png/1618249833506.png)

## Inital Thoughts

I like the Design of the Kria carrier board it has plenty of IO available. up to 32 concurrent streams are possible through a number of IAS and CSI camera connections. 

One in particular I like is the ability to connect MIPI cameras to the Kria board. alongside this connection, Xilinx has made the MIPI IP block free for all users meaning that is very simple to access the 10 bit stream on the video out lane.

The initial applications available such as SmartCam are very easy to use. With SmartCam having many input and output options to play with. Running a 1080p webcam at 60 frames per second with pedestrian detection. This is impressive for a board so small and compact. comparing this to an [Nvidia Jetson] this is a big step forward in the budget small form factor market.

#### Pros

* Easy to initally set up: If you buy the accessory pack, it gives you everything you need to run the tutorial applications without any third party components. 

* Price Point: The starter kit coming in at £199 is a massive win for the industry as many companies and hobbyists have previously been priced out of using FPGA.

* Amount of IO Available: The board comes preconfigured with plenty of IO meaning that there are loads of projects that hobbyists can work on without expansion daughterboards.

#### Cons

* Documentation: A major issue for myself with Xilinx has been the lack of hobbyist level documentation, the PDF available are fine for industry professionals but when hobbyists want to sink their teeth into FPGA development they need A-Z tutorials to make the learning a process fun.

* Toolchain: It would have been nice to see a smaller LITE version of the Vitis Toolchain as the current software stack runs around 100GB and needs a minimum of 16Gb of usable RAM.

* Bugs: When using the online forums I seem to come across the same issues that occur in 20.15 still occur in 2021.1. This is annoying for both hobbyists and us professionals as this will put off potential small business and hobbyist customers from testing out Kria SOM's over Nvidia Jetsons which are seemly plug and play.

## Conclusion

I like the Kria System, There is plenty of IO to play with and many fun applications to test out. Where I see Xilinx falling short is the lack of informal documentation that will enable the new customer base they are focusing this board on to be able to create fun and innovative applications.

From an industry perspective, it will make it much easier to integrate software applications designed on the KRIA into different form factors for industrial use as companies will use the same basic infrastructure.

Likely these are teething problems and will be sorted in due course. But for now, It is stopping new companies and hobbyists from embracing the Kria SOM.

[Kria KV260 Vision AI Starter Kit]: https://www.xilinx.com/products/som/kria/kv260-vision-starter-kit.html
[Nvidia Jetson]: https://www.nvidia.com/en-gb/autonomous-machines/embedded-systems/
