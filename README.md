# Tumbler 2 – Redesign

Corrected / upgraded version of HL Tumbler2

## Overview

This redesign focuses on:

- Improved power efficiency
- Better signal integrity
- Safer power architecture
- Modernized components
- Increased expandability

# Changes

| Original Design                      | Redesign Improvement                       |
| ------------------------------------ | ------------------------------------------ |
| VBAT to 5 V LDO regulator            | VBAT to 5 V buck converter                 |
| 5 V to 3.3 V LDO regulator           | 5 V to 3.3 V buck converter                |
| CH340 USB-UART bridge                | CP2102 USB-UART bridge                     |
| 5 V ECHO signal directly to ESP32    | Voltage divider to 3.3 V ESP32 GPIO        |
| Single USB-C (UART only)             | Dual USB-C (UART + native USB)             |
| Schottky diode reverse protection    | Ideal diode reverse protection             |
| No local decoupling for WS2812B LEDs | Added proper bypass capacitors for WS2812B |

# Pending Improvements

| Planned Change                         | Reason                                               |
| -------------------------------------- | ---------------------------------------------------- |
| Replace MPU-6050 with ST LSM6DS3TR-C   | Active part, lower noise, lower power consumption    |
| Replace TB6612FNG with dual TI DRV8870 | Integrated current limiting, modern architecture     |
| Add piezo buzzer                       | Acoustic feedback for faults, boot events, debugging |
| Add I2S microphone                     | Voice input / future speech recognition              |
| Add SPI SD card slot                   | Local data logging and firmware storage              |

# Discarded Ideas

| Idea                                            | Reason                                                    |
| ----------------------------------------------- | --------------------------------------------------------- |
| On-board charging circuit (IP5306, BQ25887RGER) | Not required. External USB charger included with battery  |
| Additional LDO for clean 3.3 V rail             | Not necessary. ESP32-WROOM internal VCC/VCCA already tied |
