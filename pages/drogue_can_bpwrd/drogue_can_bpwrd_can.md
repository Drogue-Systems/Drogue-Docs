---
title: CAN-BPWRD | CAN
keywords: Drogue, Drogue Systems, CAN, CAN FD, Development, Board, Kit, Devlopment Board, Dev Board
last_updated: 09/11/23
tags: [CAN]
summary: "An overview of the CAN capabilities of the CAN-BPWRD development board"
sidebar: drogue_can_bpwrd_sidebar
permalink: drogue_can_bpwrd_can.html
folder: drogue_can_bpwrd
---


### 1.0 Overview

<div><br></div>

The CAN-BPWRD development board features 2 full CAN interfaces each driven by a MCP2542FD-E/SN CAN transceiver, compatible with both standard CAN and CAN FD.

> For more information, find the data sheet [here](https://ww1.microchip.com/downloads/en/DeviceDoc/MCP2542FD-MCP2542WFD-4WFD-Data-Sheet-DS20005514C.pdf). 

The CAN transceivers are interfaced directly with the CAN peripherals of the STM32 micro-controller (FDCAN1, FDCAN2).

{% include note.html content="The MCP2542FD supports CAN FD up to 8 Mbps, however a common mode choke is recommended for speed above 1 Mbps, which the CAN-BPWRD-V0.2 does not include due to potential problems with transient voltages. As such, some commination error / packet loss may be experienced at higher speeds. Future versions may include a common mode choke." %}

<div><br><br></div>




### 2.0 Configuration

<div><br></div>



#### 2.1 Termination Resistors


{% include links.html %}
