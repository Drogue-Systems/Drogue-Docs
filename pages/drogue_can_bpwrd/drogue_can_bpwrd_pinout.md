---
title: CAN-BPWRD | Pinout
keywords: Drogue, Drogue Systems, CAN, CAN FD, Development, Board, Kit, Development Board, Dev Board
last_updated: 09/11/23
tags: [CAN]
summary: "Explaining the pinout of the CAN-BPWRD board"
sidebar: drogue_can_bpwrd_sidebar
permalink: drogue_can_bpwrd_pinout.html
folder: drogue_can_bpwrd
---

<div><br></div>

### 1.0 Pinout Overview

The CAN-BPWRD development board has 2.54mm pitch male pin headers which are compatible with most standard off-the-shelf 'DuPont' type jumper/breadboard wires.

{% include tip.html content="If you plan to make your own jumper wires, we recommend the Amphenol MinitoPV series receptacles with 'ultra high' spring force and the respective MinitoPV housings. These provide a strong, secure fitment." %}

The pins on the CAN-BPWRD board can be separated into 3 categories:

- ***Not Programmable I/O Pins:*** These are pins such as Vin or GND, which do not provide programmable function.
- ***Internally Reserved Pins:*** I/O Pins on the MCU which have dedicated roles on this board, such as the CAN pins or voltage measurement.
- ***Exposed / Available I/O pins:*** These pins are available on the pin headers for you to use as you please.



<div><br><br></div>


### 2.0 Not Programmable I/O Pins

#### 2.1 CAN Bus Vin and GND pins

<div><br></div>

The CAN-BPWRD development board has 4 pairs of CAN bus Vin and GND pins exposed; two pairs for each CAN bus.

The two pairs within a bus are directly connected to one another, providing you the means to pass through the bus voltage to other devices in the network.

By making use of diodes, the two pairs in CAN bus 1 are independent from the two pairs in CAN bus 2. This means you are able to connect two different power supplies - even at different voltages - to the board. The development board will take power from either input, providing redundancy if one was to fail.

{% include warning.html content="Take care to not connect 2 different power supplies to the same CAN bus" %}

{% include image.html file="drogue_can_bpwrd/CAN-BPWRD_CAN_VIN.jpg" alt="CAN-BPWRD Image with Annotated Pinout of CAN Vin Pins" caption="CAN-BPWRD Image with Annotated Pinout of CAN Vin Pins with Representative Schematic" max-width="800"%}

The CAN bus Vin pins are designed to expect a 24V input - as per the [UCANPHY specification](drogue_can_bpwrd_cyphal.html). However, the acceptable range has been widened to allow ~6.5V* to 40V.

{% include important.html content="*Inputs as low as 6.5V have been shown to work in testing, however they may become unstable depending on peripheral current draw due to the increased voltage drop across some components" %}
{% include note.html content="If you would like to power the CAN-BPWRD development board from a lower voltage supply, please see the [low voltage documentation page](drogue_can_bpwrd_low_voltage.html) for the available options." %}



<div><br><br></div>

#### 2.2 CAN Termination Jumper Pins

<div><br></div>

Each CAN bus has pair of pins labeled 'TERM', these pins are intended to be optionally shorted together using a jumper to add a termination resistor across the CAN data lines.

{% include image.html file="drogue_can_bpwrd/CAN-BPWRD_term.jpg" alt="CAN-BPWRD Image with Annotated Pinout of CAN 'TERM' Pins" caption="CAN-BPWRD Image with Annotated Pinout of CAN 'TERM' Pins" max-width="500"%}

See the [CAN-BPWRD CAN documentation page](drogue_can_bpwrd_can.html) for more information on this function.

<div><br><br></div>

#### 2.3 5V and 3V3 Enable Jumper Pins
<div><br></div>

The CAN-BPWRD development board has pins dedicated to connecting and disconnecting the 5V and 3.3V regulators to the rest of the board.

<div><br><br></div>

#### 2.4 General use 5V, 3.3V and GND Pins

### 3.0 Internally Reserved MCU Pins

<div><br></div>

Internally .....

<div><br></div>

| Pin Name | Assigned Function | Description |
|-------|--------|---------|
| PAX | ADCXINX | Read CAN Bus 1 Vin voltage |
| PAX | ADCXINX | Read CAN Bus 2 Vin voltage |
| Item 3 | V0.2 spec | VX.X spec |

#### 3.1 Vin Voltage Measurements

### 4.0 Exposed / Available IO Pins

### 5.0 Using the STM32CubeIDE to Determine Pin Assignments


<div><br><br></div>

{% include links.html %}
