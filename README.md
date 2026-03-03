# Tumbler 2 Redesign

Corrected / upgraded version of HL Tumbler2

# Changes

| Original                              | Redesign                            |
| ------------------------------------- | ----------------------------------- |
| VBAT to 5V LDO regulator              | VBAT to 5V buck converter           |
| 5V to 3.3V LDO regulator              | 5V to 3.3V buck converter           |
| CH340 UART‑USB bridge                 | CP2102 UART‑USB bridge              |
| 5 V logic ECHO to ESP32               | Voltage divider to 3.3 V ESP32 GPIO |
| Single USB‑C for UART                 | Dual USB‑C for UART and USB         |
| Standard diode for reverse protection | Ideal diode for reverse protection  |
| No bypass capacitors for WS2812B      | Added bypass capacitors for WS2812B |

# Pending

| Change                                | Reason                                           |
| ------------------------------------- | ------------------------------------------------ |
| Replace MPU-6050 with ST LSM6DS3TR-C  | Active part, less noise, lower power consumption |
| Replace TB6612FNG with two TI DRV8870 | Overcurrent protection, modern alternative       |

# Discarded

| Change                                              | Reason                                                |
| --------------------------------------------------- | ----------------------------------------------------- |
| Charging circuit on PCB (IP5306, BQ25887RGER)       | Not neccessary as USB charger delivered with battery  |
| LDO regulator for stable 3.3V rail (e.g. ESP32 ADC) | VCC and VCCA directly connected inside WROOM 1 module |
