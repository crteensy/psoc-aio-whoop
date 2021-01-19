# psoc-aio-whoop
PSoC6 based AIO FC, whoop size

KiCad files for a quadcopter AIO FC, whoop size, PSoC6 based.

Overall specs:
- 1-3S, 40 A (80 A for 5 sec)
- main controller: CY8C6347BZI-BLD34, dual core (144 MHz M4F + 72 MHz M0+)
- blackbox flash: 8 MB
- IMU: ICM-20602
- at least 3 serial interfaces (UART or I2C), including one invertible UART
- USB
- BLE
- 4 LEDs
- SWD pads
- gate drivers: NCP81253 or NCP81161
- FETs: PSMN1R8-30MLH
- current sensor: IMU185A2 (50V/V); shunt: Vishay WSKW0612, 0m5

Design goals:
- most hard to assemble components (PSoC, most other ICs and small components) are on the bottom layer with sufficient wiggle room for manual placement
- smallest package: 0402
- easy to solder components (large caps for example) are on the top layer. If it can be soldered with an iron, it's on the top
- ready to fly once the flight controller firmware (whichever that happens to be) is ported
- FETs are chosen to be sufficiently robust for ESC algorithm development

PCB Design rules:
- 6 layers
- 0.1 mm traces, 0.1 mm gap
- 0.2 mm / 0.4 mm vias
- no via-in-pad or other special via technologies required
- castellations on 4 edges
- stackup: (top) signal - gnd - power - power - gnd - signal (bot)

Design files provided:
- KiCad project
- schematic pdf
- gerbers
- BOM
- tbd: assembly helper pdfs
- tbd: SWD jig design
