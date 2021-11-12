+++
author = "Jack Bonnell"
title = "Getting Ready for the Adaptive Computing Challenge"
date = "2021-11-12"
description = "A brief walk through of my submission idea for the Adaptive Computing Challenge"
tags = [
    "Xilinx",
    "Kria",
    "FPGA",

]
+++

# Getting Ready for the Adaptive Computing Challenge

On the 15th of November, the Adaptive Computing Challenge will be announcing who gets allocated hardware to develop their competition idea.

![Adaptive Banner](/img/Adaptive_Banner.png)

 ## Cattle Detection on the Edge

This year I wanted to take a look at the emerging market for technology in the agricultural friend. More specifically, I want to look at cows and identify and document cows on mass. Currently, it is very labour intensive to raise cattle. This can lead to crucial information being missed through human error.

For this year's project, I will be looking to use Vitis AI to identify cows using the markings on their body.  I will do this by inverting the image and passing this image through a custom AI model.

![inverted Cow](/img/inverted_cow_image.png)

Using Stereo camera technology, I will be out the depth of the image. This allows me to work out a measurement per pixel from the image. With this information, I will be able to work out the width and length of the cow.

![Depth](/img/depth_disparity.png)

This information will then be accessible from ROS topics running on the KRIA system itself, giving the users the ability to see the output of all the relevant data, including all cow measurements, bounding box data, and imagery from the camera itself.

![cow](/img/measure_cow.png)

## Conclusion to the Idea

The idea of this project is for farmers better to understand FPGAs' abilities in the agricultural sector. Hopefully to allow both ourselves as developers and farmers better ways to come together to create more efficient work practices.