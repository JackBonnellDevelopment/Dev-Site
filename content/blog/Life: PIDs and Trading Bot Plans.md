+++
author = "Jack Bonnell"
title = "Life: PIDs and Trading Bot Plans"
date = "2021-10-29"
description = "PID controllers to create drive correction on Agito and creating a trading bot using Recursive Programming"
tags = [
    "Xilinx",
    "Kria",
    "FPGA",
    "Path Planning",
    "Trading"
]
+++

# Life: PIDs and Trading Bot Plans

This week I have been working on PID controllers and started my side project of trying to get my head around implementing an effective trading bot to manage my portfolio.

![PID](/img/PID_example.png)

## Proportional-Integral-Derivative Controller (PID controller) 

PID Controllers regulate the output of a particular parameter. In the automotive industry, PIDs are used for autonomous driving, such as cruise control. In basic terms, the user does not feel hard acceleration or braking from their car because the PID creates a gradual response rather than an immediate one.

![PID](/img/PID.png)

I am trying to use a PID controller to correct the robot on a predetermined path for my implementation. This will help account for any drift or steering noise that can occur through the robot's mechanical makeup.

The next stage for the PID is to implement it within a basic simulator to tune the p gain for better accuracy. Once that has been done, I will create a PID IP for Kria that can run this calulation and publish for the KRS community

## Trading Bot: Recursive Programming

I've started a side project recently, which is to create a trading bot in python. The idea behind this was the use of recursive programming becoming more needed in workflows. This plan with my trading bot is not to use deep learning but to create a system of highly optimised algorithms based on preexisting indicators or mathematical expressions.

![Alpaca](/img/alpaca.jpeg)

The base API I am using is called Alpaca API. The reason for using Alpaca is that it has a paper stock-based system available for testing indicators. This means I will be able to run tests without any of my own money at risk. But who knows, if it works I may release it open sourced.

There is not too much to report as currently, I am working on Data frame structures to store stock information in a way that is easily accessible without the need for constant sorting and restructuring.




