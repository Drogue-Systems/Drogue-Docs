---
title: CAN-BPWRD | Protections & Safeties
keywords: Drogue, Drogue Systems, CAN, CAN FD, Development, Board, Kit, Development Board, Dev Board
last_updated: 26/11/23
tags: [CAN]
summary: "An overview of the on board protections and safeties"
sidebar: drogue_can_bpwrd_sidebar
permalink: drogue_can_bpwrd_protections.html
folder: drogue_can_bpwrd
---

<div><br></div>
{% include important.html content="The CAN-BPWRD Docs are still under development, so may be subject to change." %}
<div><br></div>


### 1.0 Overview

<div><br></div>


The CAN-BPWRD Development Board has a number protections and safeties in place in regard to power supply over CAN.

The safeties implemented are often required in the physical specification of many CAN bus standards. For example:

- [Cyphal](https://forum.opencyphal.org/t/cyphal-can-physical-layer-specification-v1-0/1471)
- [DroneCAN](https://dronecan.github.io/Specification/8._Hardware_design_recommendations/)




<div><br><br></div>




### 2.0 Dual Power Supply
<div><br></div>

By making use of diodes, the Vin input CAN bus 1 is independent from the Vin  CAN bus 2. This means you are able to connect two different power supplies - even at different voltages - to the board. The development board will take power from either input, providing redundancy if one was to fail.

{% include image.html file="drogue_can_bpwrd/CAN-BPWRD_VIN_DIODE.jpg" alt="Schematic Representation of Diode Protected Vin on CAN busses" caption="Schematic Representation of Diode Protected Vin on CAN busses" max-width="800"%}

<div><br><br></div>

### 2.1 Reverse Current / Polarity
<div><br></div>

The diodes on each CAN bus serve to prevent any current flow in the incorrect direction, this mean both primary inputs (CAN 1 Vin and CAN 2 Vin) are protected against incorrect polarity.

<div><br></div>

{% include warning.html content="Although the diodes will prevent complete reverse current flow, it is possible that damage may still occur if incorrect polarity voltage is applied. If this happens, disconnect the power supply as quickly as safely possible." %}

{% include warning.html content="This protection protects the CAN-BPWRD board from incorrect polarity on a CAN bus. It will not protect the rest of the devices connected to the bus." %}


<div><br><br></div>

### 2.1 Short Circuit & Over Current
<div><br></div>

The [primary voltage regulator](https://www.mouser.co.uk/ProductDetail/968-ISL85418FRZ) on the development board is the only section of the board directly connected to the CAN bus voltage lines. This regulator generates the 5V supply used by the rest of the board.

The 5V output of the regulator has built in protections which cut the 5V output if a current draw of 1.2A or above is detected. This safety can protect the chip from a short circuit indefinitely.

These protections serve both to protect the development board from some common user errors (shorting 5v outputs to ground) and protects a CAN network from being brought down by the development board if shorted.




{% include links.html %}
