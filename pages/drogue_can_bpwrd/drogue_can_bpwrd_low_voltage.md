---
title: CAN-BPWRD | Low Input Voltage Operation
keywords: Drogue, Drogue Systems, CAN, CAN FD, Development, Board, Kit, Devlopment Board, Dev Board
last_updated: 17/09/23
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

### 2.0 Providing the Board with 5V

The primary 5V regulator on the CAN-BPWRD development board is able to accept between 


{% include links.html %}
