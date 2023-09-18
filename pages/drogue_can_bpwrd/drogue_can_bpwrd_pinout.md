---
title: CAN-BPWRD | Pinout
keywords: Drogue, Drogue Systems, CAN, CAN FD, Development, Board, Kit, Development Board, Dev Board
last_updated: 18/09/23
tags: [CAN]
summary: "Explaining the pinout of the CAN-BPWRD board"
sidebar: drogue_can_bpwrd_sidebar
permalink: drogue_can_bpwrd_pinout.html
folder: drogue_can_bpwrd
---

### 1.0 Pinout Overview

The CAN-BPWRD development board has 2.54mm pitch male pin headers which are compatible with most standard off-the-shelf 'DuPont' type jumper/breadboard wires.

{% include tip.html content="If you plan to make your own jumper wires, we recommend the Amphenol MinitoPV series receptacles with 'ultra high' spring force. These provide a strong, secure fitment." %}

The pins on the CAN-BPWRD board can be separated into 3 categories:

- ***Not Programmable I/O Pins***: These are pins such as Vin or GND, which do not provide programmable function.
- ***Internally Reserved Pins***: I/O Pins on the MCU which have dedicated roles on this board, such as the CAN pins or voltage measurement.
- ***Exposed / Available I/O pins***: These pins are available on the pin headers for you to use as you please.

### 2.0 Not Programmable I/O Pins

#### 2.1 CAN Bus Vin and GND pins

The CAN-BPWRD development board has 4 pairs of CAN bus Vin and GND pins exposed; two pairs for each CAN bus.

The two pairs with a bus are directly connected to one another, providing you the means to pass through the bus voltage to other devices in the network.

By making use of diodes, the two pairs in CAN bus 1 are completely independent from the two pairs in CAN bus 2. This means you are able to connect two different power supplies - even at different voltages - to the board. The development board will take power from either input, providing redundancy if one was to fail.

{% include image.html file="drogue_can_bpwrd/CAN-BPWRD_CAN_VIN.jpg" alt="Annotated Pinout of CAN bus Vin pins" caption="Annotated Pinout of CAN bus Vin pins" max-width="1000"%}

#### 2.2 CAN Bus Term Pins
#### 2.3 5V and 3V3 Enable Pins
#### 2.4 General use 5V, 3.3V and GND Pins

### 3.0 Internally Reserved MCU Pins

| Pin Name | Assigned Function | Description |
|-------|--------|---------|
| PAX | ADCXINX | Read CAN Bus 1 Vin voltage |
| PAX | ADCXINX | Read CAN Bus 2 Vin voltage |
| Item 3 | V0.2 spec | VX.X spec |

#### 3.1 Vin Voltage Measurements

### 4.0 Exposed / Available IO Pins

### 5.0 Using the STM32CubeIDE to Determine Pin Assignments

{% include links.html %}
