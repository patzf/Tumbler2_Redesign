# Tumbler 2 Redesign

Corrected / upgraded version of HL Tumbler2

# Changes

| Original                              | Redesign                             |
| ------------------------------------- | ------------------------------------ |
| VBAT to 5V LDO regulator              | VBAT to 5V buck converter            |
| 5V to 3.3V LDO regulator              | 5V to 3.3V buck converter            |
| CH340 UART‑USB bridge                 | CP2102 UART‑USB bridge               |
| 5V logic ECHO to ESP32                | Voltage divider to 3.3V ESP32 GPIO   |
| Single USB‑C for UART                 | Dual USB‑C for UART and USB          |
| Standard diode for reverse protection | Ideal diode for reverse protection   |
| No bypass capacitors for WS2812B      | Added bypass capacitors for WS2812B  |
| 100nF capacitors for BTN and GPIO0    | Removed capacitors for BTN and GPIO0 |

# Discarded

| Change                                              | Reason                                                |
| --------------------------------------------------- | ----------------------------------------------------- |
| LDO regulator for stable 3.3V rail (e.g. ESP32 ADC) | VCC and VCCA directly connected inside WROOM 1 module |
