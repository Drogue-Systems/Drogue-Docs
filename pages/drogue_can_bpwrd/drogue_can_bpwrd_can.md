---
title: CAN-BPWRD | CAN
keywords: Drogue, Drogue Systems, CAN, CAN FD, Development, Board, Kit, Development Board, Dev Board
last_updated: 26/11/23
tags: [CAN]
summary: "An overview of the CAN capabilities of the CAN-BPWRD development board"
sidebar: drogue_can_bpwrd_sidebar
permalink: drogue_can_bpwrd_can.html
folder: drogue_can_bpwrd
---

<div><br></div>
{% include important.html content="The CAN-BPWRD Docs are still under development, so may be subject to change." %}
<div><br></div>


### 1.0 Overview

<div><br></div>

The CAN-BPWRD development board features 2 full CAN interfaces each driven by a MCP2542FD-E/SN CAN transceiver, compatible with both standard CAN and CAN FD.

<div><br></div>

- For more information, find the data sheet [here](https://ww1.microchip.com/downloads/en/DeviceDoc/MCP2542FD-MCP2542WFD-4WFD-Data-Sheet-DS20005514C.pdf). 

<div><br></div>

The CAN transceivers are interfaced directly with the CAN peripherals of the STM32 micro-controller (FDCAN1, FDCAN2).

<div><br></div>

{% include note.html content="The MCP2542FD supports CAN FD up to 8 Mbps, however a common mode choke is recommended for speed above 1 Mbps, which the CAN-BPWRD-V0.2 does not include due to potential problems with transient voltages. As such, some commination error / packet loss may be experienced at higher speeds. Future versions may include a common mode choke." %}

<div><br><br></div>




### 2.0 Configuration

<div><br></div>



#### 2.1 Termination Resistors

The CAN-BPWRD development board has built in 120 Ohm termination resistors on each of the two CAN busses. These termination resistors can be optionally enabled or disabled using a pin jumper on the pins shown in the image below:

{% include image.html file="drogue_can_bpwrd/CAN-BPWRD_term.jpg" alt="CAN-BPWRD Image with Highlighted Pinout of CAN 'TERM' Pins" caption="CAN-BPWRD Image with Annotated Pinout of CAN 'TERM' Pins" max-width="500"%}

With the jumper in place, the termination resistor is connected to the CAN bus, and provides 120 Ohms of resistance between the CAN High and CAN Low pins on the network.

<div><br></div>

{% include tip.html content="On a properly configured CAN bus, the measured resistance between CAN High and CAN Low should be around 60 Ohms, this is due to there being a 120 Ohm termination resistor at each end of the network, forming a parallel resistance of (1 / (2/120))." %}


{% include links.html %}
