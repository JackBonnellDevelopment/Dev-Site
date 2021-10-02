+++
author = "Jack Bonnell"
title = "Life: Vitis AI Libraries, Anniversaries, New Addition"
date = "2021-10-01"
description = "Implementing Vitis AI Libraries, ROS2 and our new addition"
tags = [
    "Life",
    "Xilinx",
    "ROS2",
    "Puppy"
]
+++


# Life: Vitis AI Libraries, Anniversaries, New Addition

This weeks life update continues my adventure with Xilinx KV260. The focus this week is the Vitis AI Libraries and implementing these onto the KV260. A huge inspiration in my life hits the 30-year milestone, and our new addition arrives.

## Vitis AI Libraries

Work started this week on implementing the Vitis AI Libraries onto the KV260. My first observation was that the Vitis AI Libraries were missing from the latest toolchain. I needed to add the libraries using a meta-layer manually rather than adding the command to the root config file to achieve this. You can read how to do this in my tutorial: [Xilinx KV260 -petalinux 2021.1 - Build Vitis AI Libraries]

![Vitis AI Libraries](/img/vitis-ai-logo.png)

Once the PetaLinux project was compiled successfully, I created the Vitis platform and ran the DSA example from Vitis-AI to implement the DPU into the hardware block design. With some minor teething problems, this was a success, and I compiled the DPU targetting the KV260 board.

A minor setback was that the Vitis-AI example exports an SD card image. This image should burn to an SD card and then run on the KV260. The initial boot was unsuccessful. Because the SD card is not booting, I will need to create an FPGA-Manager template in PetaLinux and create a WIC image to load it onto KV260.

Annoyingly this goes against my need for a simplistic workflow where one tool flows into another. Watch out for a tutorial on how to configure a DPU project soon.

## ROS2

With Xilinx announcing the support for ROS2 on the Kria platform, I have been working on accelerated packages that can utilise critical features of the [Kria Robotics Stack (KRS)] to lower latency and increase edge processing for small form factor robots. 

![Kria Robotics Stack (KRS)](/img/kria-robotoics-stack-diagram.png)


Once the DPU has been configured for Vitis AI Libraries, my next step with ROS2 on Kria will be to Implement an accelerated vision package for ROS2 that can utilise key Robotics features such as object detection and adaptive route planning. For now, it's nice to see that ROS2 is being installed into the PetaLinux, without the need to use 3rd part meta-layers or operating systems such as ubuntu.

# New Addition


This week We picked up the new addition to our house. A cute little puppy named Millie. Millie has already been a learning curve for me as I barely look after myself without the added responsibility of looking after a dog. In the short time since she arrived, she has become a large part of our family, and I look forward to many years making memories.

![Little Millie](/img/Millie.png)

[Kria Robotics Stack (KRS)]: https://xilinx.github.io/KRS/sphinx/build/html/index.html
[Xilinx KV260 -petalinux 2021.1 - Build Vitis AI Libraries]: https://www.hackster.io/jack-bonnell2/xilinx-kv260-petalinux-2021-1-build-vitis-ai-libraries-dd3025