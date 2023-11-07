---
title: CAN-BPWRD | Low Input Voltage Operation
keywords: Drogue, Drogue Systems, CAN, CAN FD, Development, Board, Kit, Devlopment Board, Dev Board
last_updated: 07/11/23
tags: [CAN]
summary: "How to use the CAN-BPWRD if the available voltage is lower than required for the Vin pins"
sidebar: drogue_can_bpwrd_sidebar
permalink: drogue_can_bpwrd_low_voltage.html
folder: drogue_can_bpwrd
---

### 1.0 Overview

This page describes how different regualtors on the CAN-BPWRD development board can be bypassed. Through doing so, the development board is capable of accepting - and running on - lower input voltages than otherwise possible.

{% include warning.html content="When bypassing the primary regulator, many of the on-board safeties are also bypassed. Ensure the voltage supplied is stable and well within the stated limits on this page, otherwise the development board may be damaged." %}


<div><br></div>

### 2.0 Powering the Board with a 5V Supply

<div><br></div>

The primary 5V regulator on the CAN-BPWRD development board is able to accept between ~6.5V and 40V, and regulates the input down to 5V. To directly provide a voltage closer to 5V, the primary regulator can be bypassed.

To bypass the regulator, the 5V-EN jumper pin can be removed, and a +5V input provided to then XXX pin, as shown below. Ground can be connect to any GND pin on the board.

<div><br></div>

#### 2.1 5V Supply Limits

<div><br></div>

When bypassing the 5V ragulator to provide a 5V supply directly, the below limits should be observed:

<div><br></div>

|  | Min | Max |
|-------|--------|---------|
| CAN Required | 4.5V | 5.5V(1) |
| CAN Not Required(2) | >3V | 5.5V(1) |

> (1) 5.5V is the maximum voltage under normal conditions, the 'absolute maximum' is 6.5V - limited by the 3.3V regulator input. Approaching 6.5V will risk damage to the 3.3V regulator.

> (2) If CAN is not required, then the permitted input voltage is lower. However, this may cause some undefined behaviour from the CAN trenaceivers when supplying less than 4.5V and more than 3.2V (the internal shutdown voltage of the transceivers). It is recommended the STBY pin of the transceivers 

<div><br></div>



{% include links.html %}
