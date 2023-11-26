---
title: CAN-BPWRD | Programming
keywords: Drogue, Drogue Systems, CAN, CAN FD, Development, Board, Kit, Development Board, Dev Board
last_updated: 26/11/23
tags: [CAN]
summary: "Programming the CAN-BPWRD Development Board"
sidebar: drogue_can_bpwrd_sidebar
permalink: drogue_can_bpwrd_programming.html
folder: drogue_can_bpwrd
---

<div><br></div>
{% include important.html content="The CAN-BPWRD Docs are still under development, so may be subject to change." %}
<div><br></div>



### 1.0 Overview
<div><br></div>

The CAN-BPWRD development boards have the SWD pins of the STM32G491 MCU exposed on a header, allowing for easy, direct programming of the MCU chip using an ST-Link interface. 

A large amount of programming languages and toolchains have support for ST-Link based programming as well as well documented libraries for using an STM32 micro-controller.

<div><br><br></div>

### 2.0 Getting Started
<div><br></div>

If you are unsure on how to get started, we recommend using [PlatformIO](https://platformio.org/) to program this board, take a look at these docs pages for more help:
<div><br></div>

> [Drogue Systems Documentation --- PlatformIO Installation](https://docs.drogue.co.uk/drogue_can_bpwrd_platformio_install.html)

<div><br></div>

Using PlatformIO, the board can be programmed in multiple frameworks (STM32Cube HAL, Arduino, libopencm3, CMSIS) depending on your preference, and once set-up, offers an easy environment for developing and programming.

{% include links.html %}
