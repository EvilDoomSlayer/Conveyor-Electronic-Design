# Conveyor-Electronic-Design

This repository contains the electronic design automation (EDA) files for the **Luggage Classification Conveyor** custom PCB. It is a submodule of the main firmware repository.

## Overview

This PCB consolidates the connections between the ESP32 microcontroller, the motor drivers, and the various sensors used in the sorting system. It replaces a breadboard setup to provide a robust and reliable connection for the sorting machinery.

## Project Contents

* **/KiCad_Project**: The full project folder containing:
    * `.kicad_sch`: The schematic file.
    * `.kicad_pcb`: The PCB layout file.
* **/Gerbers**: Production files generated for PCB fabrication (Zip file usually required by manufacturers like JLC or PCBWay).

## Schematic Details

The board is designed to interface with an **ESP32-WROOM-32** dev module.

### Key Interfaces
* **Power Input**: 5V DC (Powers the ESP32 and the Servos/DC Motor).
* **Motor Driver**: On-board socket for an **L293D** motor driver IC.
* **Sensor Headers**:
    * 3-pin headers for Servos (Signal, VCC, GND).
    * 4-pin header for HX711 (Load Cell Amplifier).
    * Digital headers for IR (E18-D80NK) and Magnetic (KY-024) sensors.

### Pinout Mapping
This PCB routes the ESP32 GPIOs strictly according to the firmware configuration:

| Component | ESP32 GPIO |
| :--- | :--- |
| **L293D (1A/2A)** | GPIO 16, 17 |
| **Load Cell (SCK/DT)** | GPIO 19, 23 |
| **Servos (1 & 2)** | GPIO 21, 22 |
| **Magnetic Sensor** | GPIO 32 |
| **IR Sensor** | GPIO 34 |

## Fabrication

The design is a 2-layer board. Standard manufacturing tolerances apply:
* **Thickness**: 1.6mm
* **Copper Weight**: 1oz
* **Solder Mask**: Green (or preferred color)

## Software Used

* **KiCad**: For Schematic capture and PCB Layout.
 