# HagiwoHatNoise SMT - first steps in PCBA

https://jlcpcb.com/parts/all-electronic-components

- we won't have pots, jacks or power header assembled, just resistors/caps/transistors/maybe LED
- it's better/less costly to place components just on one side of the board
- for v1.0 we continue to mount arduino on pin headers
- for v2.0 we can aim to just use atmega chip directly (though it likely won't be cheaper)
- it is possible to use BOM tool to autodetect parts, though its detection isn't great
	- it's a bit chicken and egg i.e. our BOM is through-hole parts and we need to know which SMT parts to use
- to save cash look for 'basic' parts, as extended parts incur a picking/loading fee
	- though not many fall into that category 
	- some resistors are classed as 'basic'
- some specifics for the Hagiwo hat circuit are:
-- you can use any common NPN type transistor, not just 2SC1815
-- Schottky diodes have low forward voltage drop (Vf) which provides earlier protection to the Arduino pins

- choose parts, download footprints

JLCPCB’s Online Tools: JLCPCB offers tools like the "SMT Parts Library" where you can select components and automatically download their corresponding footprints.

https://componentsearchengine.com/
https://github.com/uPesy/easyeda2kicad.py

There is a tick box for 'basic parts', and a github which lists them all:
https://github.com/josemariaaraujo/JLCPCB-Basic-Parts/blob/master/Basic%20Parts.csv


you preorder parts to reserve them before submitting a PCBA order

PCBA
- MLCCs, 50V
- you can search for all values at once, check package and manufacturer
- some have thumbs up symbol (no feeder fee)
2 x 100pF (101) ceramic capacitor
1 x 22nF (223) ceramic capacitor
1 x 3.3nF (332) ceramic capacitor
1 x 2.2uF (225) ceramic capacitor
1 x 100nF (104) ceramic capacitor
1 x 10uF electrolytic capacitor
6 x BAT43 diodes (Vf < 0.3V) rated at 10mV
1 x 2SC1815 transistor 
6 x 1K resistor
1 x 33K resistor
1 x 470 resistor
1 x 2.7K resistor
4 x 100K resistor

Self-Assembly
1 x LED
3 x 100K pots
4 x thonkiconns
1 x Eurorack_Power_16pin_Shrouded

PCBA requires compatible BOM and CPL files

There are two support articles for getting these from KiCad
https://jlcpcb.com/help/article/81-How-to-generate-the-BOM-and-Centroid-file-from-KiCAD
https://jlcpcb.com/help/article/66-How-to-Generate-BOM-and-Centroid-Files-from-KiCad-in-Linux

This plugin described in the 2nd article can help
https://github.com/fullyautomated/KiJLC
In eeschema must choose Tools -> Generate Legacy Bill of Materials

AttributeError: `BOARD` object has no attribute `GetModules`
https://github.com/fullyautomated/KiJLC/issues/3

Also:
https://gist.github.com/arturo182/a8c4a4b96907cfccf616a1edb59d0389

This one seems best/most up to date:
https://github.com/Bouni/kicad-jlcpcb-tools

There’s another one which is in the PCM by bennymeg which would be more straightforward to install, search in the PCM.

https://pretalx.kicad.org/kicon-europe-2024/cfp

https://github.com/kweiwen/benjolin/tree/master


# Part Picks

Foshan Blue Rocket Elec 2SC1815M-GR C305425
50V 300mW 200@2mA,6V 150mA NPN SOT-23 Bipolar Transistors - BJT ROHS
SOT-23

TOSHIBA CUS10S30,H3F C146335
30V 230mV@100mA 1A SC-76(SOD-323) Schottky Barrier Diodes (SBD) ROHS
SC-76(SOD-323)

Capxon International Elec HV100M050C055ETR C402532
10uF 50V ±20% SMD,D5xL5.5mm Aluminum Electrolytic Capacitors - SMD ROHS
SMD,D5xL5.5mm

CCTC TCC1206X7R225K500HT C2903669
50V 2.2uF X7R ±10% 1206 Multilayer Ceramic Capacitors MLCC - SMD/SMT ROHS
1206

HRE CGA0402X7R104K500GT C6119785
50V 100nF X7R ±10% 0402 Multilayer Ceramic Capacitors MLCC - SMD/SMT ROHS
0402

Walsin Tech Corp 0402B332J500CT C237209
50V 3.3nF X7R ±5% 0402 Multilayer Ceramic Capacitors MLCC - SMD/SMT ROHS
0402

Darfon Elec C0603NP0101JGT C258474
50V 100pF NP0 ±5% 0201 Multilayer Ceramic Capacitors MLCC - SMD/SMT ROHS
0201

HUI JU NL0805B223K500CPBN C969994
50V 22nF ±10% 0805 Multilayer Ceramic Capacitors MLCC - SMD/SMT ROHS
0805

UNI-ROYAL(Uniroyal Elec) AS0606J0272T5E C966063
600mW Thick Film Resistors 200V ±100ppm/℃ ±5% 2.7kΩ 1206 Chip Resistor - Surface Mount ROHS
1206

UNI-ROYAL(Uniroyal Elec) HP05W3J0333T5E C2774724
333.333mW Thick Film Resistors 150V ±100ppm/℃ ±5% 33kΩ 0805 Chip Resistor - Surface Mount ROHS
0805

UNI-ROYAL(Uniroyal Elec) CQ05W8J0102T5E C966525
125mW 150V ±100ppm/℃ ±5% 1kΩ 0805 Chip Resistor - Surface Mount ROHS
0805

UNI-ROYAL(Uniroyal Elec) NQ06W4F1003T5E C965069
250mW 200V ±100ppm/℃ ±1% 100kΩ 1206 Chip Resistor - Surface Mount ROHS
1206

Ever Ohms Tech CR0402F470RQ10Z C881342
63mW Thick Film Resistors ±100ppm/℃ ±1% 470Ω 0402 Chip Resistor - Surface
0402