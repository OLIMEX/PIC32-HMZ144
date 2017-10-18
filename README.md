# PIC32-HMZ144 development board

Product web-page:

https://www.olimex.com/Products/PIC/Development/PIC32-HMZ144/open-source-hardware

Features:

* Completely OSHW (Open-Source HardWare)
* PIC32MZ2048EFG144 512KB RAM 2MB Flash (was PIC32MZ2048ECG144 prior to 20.10.2017)
* USB-OTG connector
* MicroSD card connector
* Standard ICSP for debugging and programming
* JTAG pins exposed on 0.1" step 6 pins
* EXT1 and EXT2 50 pin 0.1" connectors for all PIC ports
* RESET and USER buttons
* PWR and STATUS LEDs
* LiPo battery charger and connector
* UEXT connector
* Dimensions: 77 x 52 mm

Demo-software can be found in the software section of the board's web-page. 

Hardware revsion note:

A small number of initially distributed boards might beed a hardware patch for better operation. If your board is revision B and has Q1 with value of 24MHz make sure to apply all of the changes listed below (1, 2, and 3) manually. These hardware changes are required ONLY for boards with printed board revision B and crystal Q1=24Mhz. If your board has a printed revision C or newer, or if Q1=12MHz no hardware changes are required!  

Revision B patch and revision C notes:

1. The crystal Q1 was changed from 24MHz to Q12.000MHz/HC-49S/SMD/20pF/30ppm;
2. Crystal capacitors (C29, C32) were changed from 27pF to 20pF as required in the errata: "C2=Cload, C1=Cload-2pF" and to have some pF spare, because during production, the capacitance is increased due to flux or dirt;
3. R36=10k pull-up to 3.3V was added to the OSCO pin, i.e. MCU pin<72>;
