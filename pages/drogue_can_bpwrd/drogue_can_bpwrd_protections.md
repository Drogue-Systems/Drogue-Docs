---
title: CAN-BPWRD | Protections & Safeties
keywords: Drogue, Drogue Systems, CAN, CAN FD, Development, Board, Kit, Development Board, Dev Board
last_updated: 17/09/23
tags: [CAN]
summary: "An overview of the on board protections and safeties"
sidebar: drogue_can_bpwrd_sidebar
permalink: drogue_can_bpwrd_protections.html
folder: drogue_can_bpwrd
---

DROGUE - CAN-BPWRD protections page

### 1.0 Overview

<div><br></div>


The CAN-BPWRD Development Board has a number protections and safeties in place in regard to power supply over CAN.

The safeties implemented are often required in the physical specification of many CAN bus standards. For example:

- [Cyphal](https://forum.opencyphal.org/t/cyphal-can-physical-layer-specification-v1-0/1471)
- [DroneCAN](https://dronecan.github.io/Specification/8._Hardware_design_recommendations/)




<div><br><br></div>




### 2.0 Short Circuit & Over Current
<div><br></div>

By making use of diodes, the Vin input CAN bus 1 is independent from the Vin  CAN bus 2. This means you are able to connect two different power supplies - even at different voltages - to the board. The development board will take power from either input, providing redundancy if one was to fail.

{% include image.html file="drogue_can_bpwrd/CAN-BPWRD_VIN_DIODE.jpg" alt="Schematic Representation of Diode Protected Vin on CAN busses" caption="Schematic Representation of Diode Protected Vin on CAN busses" max-width="800"%}


<div><br><br></div>

### 2.1 Reverse Current
<div><br></div>





{% include links.html %}
