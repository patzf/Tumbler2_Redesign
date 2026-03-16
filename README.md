# Tumbler 2 – Redesign

Corrected / upgraded version of HL Tumbler2

## Overview

This redesign focuses on:

- Improved power efficiency
- Better signal integrity
- Safer power architecture
- Retaining the original components where possible
- Increased expandability

# Changes

| Original Design                      | Redesign Improvement                             |
| ------------------------------------ | ------------------------------------------------ |
| 5 V to 3.3 V LDO regulator           | 5 V to 3.3 V buck converter                      |
| 5 V ECHO signal directly to ESP32    | Voltage divider to 3.3 V ESP32 GPIO              |
| No local decoupling for WS2812B LEDs | Added proper local bypass capacitors for WS2812B |
| 100 nF capacitors on BTN and GPIO0   | Removed unnecessary capacitors on BTN and GPIO0  |

# Discarded Ideas

| Idea                                            | Reason                                                    |
| ----------------------------------------------- | --------------------------------------------------------- |
| On-board charging circuit (IP5306, BQ25887RGER) | Not required. External USB charger included with battery  |
| Additional LDO for clean 3.3 V rail             | Not necessary. ESP32-WROOM internal VCC/VCCA already tied |
