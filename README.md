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

A small number of initially distributed boards might beed a hardware patch for better operation. If your board is revision B and has Q1 with value of 24MHz make sure to apply all of the revision C changes listed below (1, 2, and 3) manually. These hardware changes are required ONLY for boards with printed board revision B and crystal Q1=24Mhz. If your board has a printed revision C or newer, or if Q1=12MHz no hardware changes are required!  

Hardware revisions:

* Revision B patch and revision C notes:

1. The crystal Q1 was changed from 24MHz to Q12.000MHz/HC-49S/SMD/20pF/30ppm;
2. Crystal capacitors (C29, C32) were changed from 27pF to 20pF as required in the errata: "C2=Cload, C1=Cload-2pF" and to have some pF spare, because during production, the capacitance is increased due to flux or dirt;
3. R36=10k pull-up to 3.3V was added to the OSCO pin, i.e. MCU pin<72>.

* Revision C1:

  This is the patched version of PIC32-HMZ144_Rev_C with soldered PIC32MZ2048EFG144-I/PH processors instead of PIC32MZ2048ECG144-I/PH

1. The main processor was changed from PIC32MZ2048ECG144-I/PH to PIC32MZ2048EFG144-I/PH (the ECG was declared "not recommended for new designs" by Microchip)
2. R36 was changed from 10k to 1.5k;
3. Removed quartz Q1. Q1, C29, C32 and R30 were changed to NA - this is because of the errata sheets of both chips. Refer to 4;
4. Added oscillator CD1 instead. CD1 is 24MHz oscillator;
5. Q2, C30 and C31 were changed to NA.

* Revision C2:

  Only difference compared to C1 is a typo in the schematic values, R36 should be marked as 150 Ohm resistor. 
  
  No boards with R36 = 1.5k were ever produced.