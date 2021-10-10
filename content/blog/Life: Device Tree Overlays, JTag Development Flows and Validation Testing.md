+++
author = "Jack Bonnell"
title = "Life: Device Tree Overlays, JTag Development Flows and Validation Testing"
date = "2021-10-07"
description = "Working through Device Tree Overlay Issues and Jtag Development flow optimisation"
tags = [
    "Xilinx",
    "Kria",
    "FPGA",
    "Jtag",
    "Vivado"
]
+++

# Life: Device Tree Overlays, JTag Development Flows and Validation Testing

This week, I've been working on creating a more efficient Workflow for myself regarding mocking up block designs and Vitis applications, along with trying to brush up on my validation testing in Vivado.

![Lynsyn Lite](/img/lynsyn_lite.jpg)

## Device Tree Overlays

With my current workflow structure, I do not come across Device tree overlays very often as usually, the PetaLinux build is bespoke to the task at hand. With the KV260 I've been looking to utilise the Vitis IDE for creating applications based on my pre-configured block designs.

My current problem has been with the DPU RTL Kernel Example creates an SD card image that will not boot on the KV260. Therefore I need to use the FPGA manager in the PetaLinux software to make an application that I can load through the terminal using xmutil.

Currently, the main issue is that the DPU is automatically implemented through the Vitis example, meaning that I have no way to set the interrupts and device tree flow manually.

After some digging, I found an old tutorial on the Xilinx documentation based on 2018.3 that shows how you can use a helper [TCL script] to create the Device Tree Overlay.

Now that I have found this shortcut I am now able to progress with my DPU tutorial. Keep an eye out for it on my [Projects] page.

## JTag Development Flows

I've always been a lazy person, so finding the shortest way around a project is usually my first thought when working on a development flow. I have started to look at the virtual Cable utilisation within the Xilinx toolchain to load data onto my ZCU104.

Currently, due to the crazy resources needed to run the Xilinx toolchain, I use AWS to host my toolchain so that I am able to set the resources to the tasks I am undertaking. This has worked great for processing applications and synthesising block designs, but it falls short in getting the data to the device itself.

AWS falls short because I need to package the data, then compress and upload it to my online file platform and then do the reverse before I am able to load it onto my ZCU104.

![ZCU104](/img/zcu104.jpg)

Realising that this was adding at least an hour to my development time, I decided to utilise a [Lynsyn Lite] and a VPN to port forward the IP address of my local virtual cable to the AWS machine. This allowed me to load up my image file directly from PetaLinux without the need for an SD card.

Even though this is slower than loading from a local SD card, this has lowered my development time by around 20 minutes and means I do not need to keep track of which sd card is which.

Great Success! 

## Validation Testing

With the KV260 I want to utilise the simulation testing available within Vivado to validate my block designs. Currently, my main issue has been that there is minimal utilisation of simulation for visual projects.

![Vivado ML](/img/vivado.png)

This week I've started at the beginning. The DPU utilises Interrupts to let the workflow path know that processing has been complete and the information is ready to be received. Currently, the idea I'm working with this to utilise JTag to AXI IP. This will allow me to send and read data from the block design loaded onto real-time hardware. In theory, this means I can emulate the interrupt pattern and data output on the DPU and MIPI IP to debug any intermittent issues from my design.

Currently, I am working on the real-time TCL script that will send and read the data to create a validation test for the block design. This should, in theory, give me a much better granularity in my Block Design workflow.



[TCL script]: https://xilinx-wiki.atlassian.net/wiki/download/attachments/18841847/dt_overaly%20.tcl?version=1&modificationDate=1536676250116&cacheVersion=1&api=v2

[Projects]: /projects

[Lynsyn Lite]: https://store.sundance.com/product/lynsyn-lite/