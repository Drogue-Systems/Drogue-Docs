---
title: CAN-BPWRD | Low Input Voltage Operation
keywords: Drogue, Drogue Systems, CAN, CAN FD, Development, Board, Kit, Devlopment Board, Dev Board
last_updated: 09/11/23
tags: [CAN]
summary: "How to use the CAN-BPWRD if the available voltage is lower than required for the Vin pins"
sidebar: drogue_can_bpwrd_sidebar
permalink: drogue_can_bpwrd_low_voltage.html
folder: drogue_can_bpwrd
---

### 1.0 Overview

This page describes how different regulators on the CAN-BPWRD development board can be bypassed. Through doing so, the development board is capable of accepting - and running on - lower input voltages than otherwise possible.

<div><br></div>

{% include warning.html content="When bypassing the primary regulator, many of the on-board safeties are also bypassed. Ensure the voltage supplied is stable and well within the stated limits on this page, otherwise the development board may be damaged." %}

{% include note.html content="Running on lower voltages may require some parts of the development board be disabled or powered off, resulting in reduced functionality" %}

{% include tip.html content="Bypassing the 5V regulator will allow you to power the development board with an independent power supply, rather than the CAN bus supply." %}

<div><br></div>


### 2.0 Powering the Board with a 5V Supply

<div><br></div>

The primary 5V regulator on the CAN-BPWRD development board is able to accept between ~6.5V and 40V, and regulates the input down to 5V. To directly provide a voltage closer to 5V, the primary regulator can be bypassed.

To bypass the 5V regulator, the 5V-EN jumper pin should be removed, and a +5V input provided to then XXX pin, as shown below. Ground can be connect to any GND pin on the board.

<div><br></div>
IMAGE HERE
<div><br></div>

When bypassing the 5V regulator, the 5V LED will no longer be lit whe the board is powered on.

<div><br></div>



#### 2.1 5V Supply Limits

<div><br></div>

When bypassing the 5V regulator to provide a 5V supply directly, the below limits should be observed:

<div><br></div>

|  | Min | Max |
|-------|--------|---------|
| CAN Required | 4.5V | 5.5V (1) |
| CAN Not Required (2) | >3V | 5.5V (1) |

> (1) 5.5V is the maximum voltage under normal conditions, the 'absolute maximum' is 6.5V - limited by the 3.3V regulator input. Approaching 6.5V will risk damage to the 3.3V regulator.

> (2) If CAN is not required, then the permitted input voltage is lower. However, this may cause some undefined behavior from the CAN transceivers when supplying less than 4.5V and more than 3.2V (the internal shutdown voltage of the transceivers). It is recommended the STBY pin of the transceivers PINXX is held high to force the transceivers into shutdown mode.


<div><br></div>




### 3.0 Powering the Board with a 3.3V Supply

<div><br></div>

{% include warning.html content="By bypassing the 3.3V regulator, the supply voltage will be directly powering the MCU chip. If the supply voltage is not sufficiently stable, then the MCU may exhibit unexpected behavior, errors or may be damaged" %}

<div><br></div>

If only a 3.3V supply is available, then the 3.3V regulator can also be bypassed. By doing so, the CAN transceivers will be completely un-powered, but the rest of the board should remain operational.

<div><br></div>
{% include note.html content="If, for some reason, a separate 5V - or higher - supply is also available, the the CAN transceivers can be powered using this supply, either by following the steps from section 2.0 of this page, or by leaving the 5V-EN jumper in place and supplying up to 40V to Vin. This will result in the majority of the board being powered by the external 3.3V supply, and the CAN transceivers powered by the higher voltage input." %}
<div><br></div>

To bypass the 3.3V regulator, the 3V3-EN jumper pin should be removed, and a +3.3V input provided to then XXX pin, as shown below. Ground can be connect to any GND pin on the board.

<div><br></div>
IMAGE HERE
<div><br></div>

When bypassing the 3.3V regulator, the 5V and 3.3V LED's will no longer be lit whe the board is powered on. - unless the 5V regulator is also being powered separately.

<div><br></div>


#### 3.1 3.3V Supply Limits

<div><br></div>

|  | Min | Max |
|-------|--------|---------|
| Voltage | 2.92V (1) | 3.6V |

> (1) 2.92V is the highest minimum voltage in the STM32G491XC data sheet. Voltages as low as 2.2V may be possible (2.2V limitation from the I2C memory chip), please consult the STM32G491XC data sheet.


<div><br></div>


{% include links.html %}
