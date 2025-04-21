# Audio Player with Raspberry Pi Pico 2W

## Description of the Functionality

This project implements a compact WAV audio player using the Raspberry Pi Pico 2W microcontroller. 
The audio files are stored on a microSD card, read via SPI, and played through an I2S DAC (UDA1334A) connected to a 3.5mm headphone jack.
The user can control playback using physical buttons and adjust the volume with a potentiometer.

---

## Motivation

The motivation for choosing this project was to explore embedded audio playback using Rust and Embassy on the Raspberry Pi Pico 2W.
The goal was to build a minimal and cost-effective music player while learning low-level embedded I/O, SPI, I2S, and async execution using Rust.

---

## Architecture

### Components Overview

| Component             | Purpose                            |
|----------------------|------------------------------------|
| Raspberry Pi Pico 2W | Core microcontroller               |
| UDA1334A DAC          | Converts I2S digital signal to analog audio |
| LCD (ILI9341)        | Optional display for file browsing and now playing |
| SD Card (SPI)        | Stores WAV files                   |
| Potentiometer/Rotary Encoder        | Analog/Digital volume control              |
| Buttons              | Play/Pause, Next, Previous         |
| Breadboard + Wires   | Physical prototyping and connection |

### Interconnection

- The DAC is connected via I2S to the Pico.
- The SD card uses SPI for communication (shared with LCD or dedicated).
- The potentiometer is connected to one of Pico's ADC pins.
- Buttons are connected to GPIOs with internal pull-ups.
- LCD (optional) uses SPI and CS/DC/RST pins.

### Diagram

To-do using diagrams.net

---

## Weekly Log

To-do. This table is just for template

| Week | Summary                                              |
|------|------------------------------------------------------|
| 1    | Project planning, requirements, researching components |

---

## Hardware Design

### Hardware Description

The following hardware was used:

- Raspberry Pi Pico 2W
- UDA1334A I2S DAC
- LCD with built-in SD slot (will see if this is the best option)
- 10k potentiometer/Rotary Encoder (not sure which I should buy)
- 3 push buttons
- Breadboard and jumper wires
- 3.5mm jack socket

### Schematic

To-do in Kicad

---

## Software Design

### Detailed Design

To-do

### Functional Diagram

To-do 

---

## Bill of Materials

### Hardware

| Item                            | Quantity | Unit Price (RON) | Total (RON) | Notes                              |
|---------------------------------|----------|------------------|-------------|------------------------------------|
| Raspberry Pi Pico 2W            | 1        | 39.66            | 39.66       | Main controller                    |
| DAC UDA1334A I2S Module         | 1        | 56.76            | 56.76       | I2S DAC with stereo output         |
| Header pins (2.54 mm, 40p)      | 2        | 0.99             | 1.98        | For soldering to Pico              |
| Breadboard (830 tie points)     | 1        | 9.98             | 9.98        | Main prototyping base              |
| Push Button (white round cap)   | 3        | 1.99             | 5.97        | Play, Next, Previous controls      |
| LCD SPI Display 1.8" (128x160)  | 1        | 28.99            | 28.99       | Visual interface for the player    |
| Breadboard rigid wires          | 1        | 12.49            | 12.49       | Manual connections (precise)       |
| Breadboard jumper wires         | 1        | 7.99             | 7.99        | Flexible jumper wires              |

Total Estimated Cost (RON): 163.92 RON (for now)

### Software

To-do : complete later when I've finished

| Crate               | Purpose                        |
|---------------------|--------------------------------|
| `embassy`           | Async runtime for microcontrollers |
| `embassy-rp`        | Raspberry Pi Pico support      |
| `embedded-sdmmc`    | SD card access                 |
| `defmt`             | Logging                        |
| `embedded-hal`      | Hardware abstraction layer     |

---