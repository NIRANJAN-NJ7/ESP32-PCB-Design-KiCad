# ESP32-WROOM-32E Development Board — KiCad 10

Open `ESP32_DevBoard.kicad_pro` in KiCad. This revised layout is shaped as a compact development board and uses the official ESP32-WROOM-32E module footprint plus standard KiCad footprints for the headers, USB-C receptacle, regulator, passives, and buttons. The module and connector parts will appear in 3D instead of as bare custom pad outlines.

## Included

- `ESP32_DevBoard.kicad_sch`: schematic for the WROOM-32E, left/right GPIO headers, USB-C 5 V input, 5.1 kΩ CC resistors, AP2112K-3.3 regulator, decoupling capacitors, EN pull-up, and reset/boot buttons.
- `ESP32_DevBoard.kicad_pcb`: 27.94 × 58.42 mm, 2-layer board placement with 2.54 mm side headers, USB-C connector at the bottom edge, ground pours, and an antenna copper keepout.
- `ESP32_DevBoard.kicad_pro`: KiCad project settings.

## Programming and use

USB-C provides **power only** in this version. Program the ESP32 with a separate 3.3 V USB-to-UART adapter connected to GND, GPIO3/RX0, and GPIO1/TX0 on the right header. The BOOT and RESET buttons support manual bootloader entry. Do not feed 5 V into any GPIO or power the board from two 5 V sources at once.

GPIO12, GPIO0, GPIO2, GPIO5, and GPIO15 are boot strapping pins. GPIO34–GPIO39 are input-only. GPIO6–GPIO11 are reserved for the module flash and are not exposed on the headers.

## Fabrication status

This is a substantially more complete editable project, but it is still a **layout prototype**, not a board ready to order: the PCB copper tracks are not routed, and ERC/DRC plus the exact selected parts and manufacturer clearances have not been checked. Route the connections, run ERC and DRC, and inspect the Gerbers before fabrication.
