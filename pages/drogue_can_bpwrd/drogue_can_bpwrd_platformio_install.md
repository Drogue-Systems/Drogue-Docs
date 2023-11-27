---
title: CAN-BPWRD | PlatformIO Installation
keywords: Drogue, Drogue Systems, CAN, CAN FD, Development, Board, Kit, Development Board, Dev Board
last_updated: 27/11/23
tags: [CAN]
summary: "How to set up PlatformIO to program the CAN-BPWRD Development Board"
sidebar: drogue_can_bpwrd_sidebar
permalink: drogue_can_bpwrd_platformio_install.html
folder: drogue_can_bpwrd
---

<div><br></div>
{% include important.html content="The CAN-BPWRD Docs are still under development, so may be subject to change." %}
<div><br></div>


### 1.0 Installing PatformIO and the ST STM32 platform



#### 1.1 Install PlatformIO extension
<div><br></div>

PlatformIO can be installed as an extension to VSCode in the extensions tab.

<div><br></div>
{% include image.html file="drogue_can_bpwrd/platformio/1.png" alt="beep" caption="boop" max-width="600"%}
<div><br></div>




#### 1.2 Install ST STM32 platform
<div><br></div>

Once installed, PlatformIO can be opened, and we can navigate to the Platforms menu, open the embedded tab and search for stm32:

<div><br></div>
{% include image.html file="drogue_can_bpwrd/platformio/2.png" alt="beep" caption="boop" max-width="600"%}
<div><br></div>

Click on the ST STM32 option and install it, this may take some time.

<div><br></div>




#### 1.3 Force PlatformIO to download the stm32-arduino framework
<div><br></div>

Next, we have to make a project in order to force PlatformIO to install the arduino stm32 framework - this project can be deleted as soon as it's created.

<div><br></div>
{% include image.html file="drogue_can_bpwrd/platformio/3.png" alt="beep" caption="boop" max-width="600"%}
<div><br></div>

in the project wizard, choose any name you like and set the board to any STM32 board, set the framework to arduino and click finish. This may take some time as it will download the arduino-stm32 framework. Once this is complete the project can be deleted.

You may notice at this point that the Drogue CAN-BPWRD (or any STM32G491CC) board is not an option here. For now this isn't a problem, and the steps in section 2 will show how to add it.

<div><br></div>
{% include image.html file="drogue_can_bpwrd/platformio/4.png" alt="beep" caption="boop" max-width="600"%}
<div><br></div>







### 2.0 Adding PlatformIO support for the Drogue board.
<div><br></div>

In order to add support for this development board, we need to add and modify a few files in the PlatformIO core directory [1](https://docs.platformio.org/en/stable/platforms/creating_board.html#), [2](https://github.com/stm32duino/Arduino_Core_STM32/wiki/Add-a-new-variant-%28board%29). Each of the required files are provided in this Github Repo under the [PlatformIO_Install](TODO) folder.

All of the following changes will occur in the [PlatformIO core_dir](https://docs.platformio.org/en/stable/projectconf/sections/platformio/options/directory/core_dir.html#projectconf-pio-core-dir).

On Windows this path may look like `C:\Users\[USERNAME]\.platformio`

<div><br></div>



#### 2.1 Adding the board to the ST STM32 platform.
<div><br></div>

In the PlatformIO core directory, navigate to `/platforms/ststm32/boards`. This folder contains JSON files outlining specifications and details for different boards.

The JSON file for the Drogue CAN-BPWRD board can be found in the [PlatofmIO_Install/ststm32_platform_files](https://github.com/Drogue-Systems/CAN-BPWRD_CYPHAL/tree/main/PlatformIO_Arduino/PlatformIO_Install/ststm32_platfrom_files) folder in this repo, named `drogue_can_bpwrd_g491cc.json`.

Copy the `drogue_can_bpwrd_g491cc.json` JSON file into the `/platforms/ststm32/boards` folder.

<div><br></div>
{% include image.html file="drogue_can_bpwrd/platformio/5.png" alt="beep" caption="boop" max-width="600"%}
<div><br></div>





#### 2.2 Adding the board to the stm32-arduino framework
<div><br></div>


##### 2.2.1 Adding Variant Files
<div><br></div>

In the PlatformIO core directory, navigate to `/packages/framework-arduinoststm32/variants/STM32G4xx/G491C(C-E)U_G4A1CEU`. This folder contains information specific to boards using the STM32G491C series MCU's.

The files found in `PlatformIO_Install/arduino_framework_files/variants` should all be copied into this folder.

<div><br></div>
{% include image.html file="drogue_can_bpwrd/platformio/6.png" alt="beep" caption="boop" max-width="600"%}
<div><br></div>



##### 2.2.2 Add entry to boards.txt declaration
<div><br></div>

In the PlatformIO core directory, navigate to `/packages/framework-arduinoststm32/boards.txt`. This file contains the declaration for all of the boards in the arduino framework.

using a search function find the section for `Generic G4`.

<div><br></div>
{% include image.html file="drogue_can_bpwrd/platformio/7.png" alt="beep" caption="boop" max-width="600"%}
<div><br></div>

Copy the contents of the `board-entry.txt` file found in the [PlatformIO_Install/arduino_framework_files](https://github.com/Drogue-Systems/CAN-BPWRD_CYPHAL/tree/main/PlatformIO_Arduino/PlatformIO_Install/arduino_framework_files) folder of this repo and paste it into the `boards.txt` file just before the first generic board entry:

<div><br></div>
{% include image.html file="drogue_can_bpwrd/platformio/8.png" alt="beep" caption="boop" max-width="600"%}
<div><br></div>

Save and close the `boards.txt` file.

<div><br></div>




#### 2.3 Add the board to the PlatofrmIO core
<div><br></div>

In the PlatformIO core directory, create a new directory named `boards`

<div><br></div>
{% include image.html file="drogue_can_bpwrd/platformio/9.png" alt="beep" caption="boop" max-width="600"%}
<div><br></div>

Into this directory, copy the `drogue_can_bpwrd_g491cc.json` file found in the [PlatofmIO_Install/ststm32_platform_files](https://github.com/Drogue-Systems/CAN-BPWRD_CYPHAL/tree/main/PlatformIO_Arduino/PlatformIO_Install/ststm32_platfrom_files) folder in this repo.

<div><br></div>



#### 2.4 Edit the default HSE clock speed
<div><br></div>

In the PlatformIO core directory, navigate to `packages/framework-arduinoststm32/system/STM32G4XX` and open the file name `stm32g4xx_hal_conf_default.h`

Find the line which reads `#define HSE_VALUE` and set the value in brackets to `8000000UL`. This lets the framework know that the Drogue CAN-BPWRD board has an 8MHz external oscillator instead of a 24MHz one. Without this change the board would run at 1/3 the target speed.

<div><br></div>
{% include image.html file="drogue_can_bpwrd/platformio/10.png" alt="beep" caption="boop" max-width="600"%}
<div><br></div>




### 3.0 Testing
<div><br></div>

Once section 2 is complete, the Drogue CAN-BPWRD board should be available when creating a new project:

<div><br></div>
{% include image.html file="drogue_can_bpwrd/platformio/11.png" alt="beep" caption="boop" max-width="600"%}
<div><br></div>

This will generate a project with some basic arduino code. Test building by clicking the tick at the bottom of the screen:

<div><br></div>
{% include image.html file="drogue_can_bpwrd/platformio/12.png" alt="beep" caption="boop" max-width="600"%}
<div><br></div>


<div><br></div>
<div><br></div>



{% include links.html %}
