# Colpitts-PCB
PCB for a Colpitts done in Fritzing

There are more practical oscillators available today, if for example your are looking to make a radio transmitter.
Nevertheless, the Colpitts Oscillator, here in common base configuration, works and produces a nice sine wave.
Because it can be built on a Breadboard or from the PCB 
and because it can be made from components that are ready available,
it is a great tool to grasp the concept of a tank circuit and a fun soldering project too.
Inspect one with an Oscilloscope for example.

To make the Oscillator you will need a Breadboard or to print the PCB or have the PCB printed for you.
The PCB file is in "Fritzing" format .fzz.
You can open it in "Fritzing" (https://fritzing.org/) to first CHECK it, modify it as you wish
and even have it printed by a PCB printing service of your choice such as AISLER (https://aisler.net/).

You will also need the componets listed below.
	
	C1 	Ceramic Capacitor	3.3nF
	C2 	Ceramic Capacitor	680pF
	C3 	Ceramic Capacitor	220pF
	C4 	Variable Capacitor	0pF- 100pF
	C5 	Ceramic Capacitor	1µF
	C6 	Ceramic Capacitor	1µF
	L1 	Inductor		3.3 µH
	R1 	Resistor		100kΩ 
	R2 	Resistor		100kΩ 
	R3 	Resistor		47kΩ
	R4 	Resistor		2kΩ 
 	Q1 	NPN-Transistor		BC547 or 2N3904
  	GND&SIG Generic male header	2 pins 	pin spacing 0.1in (2.54mm)
 	+9V	Screw terminal		2 pins 	pin spacing 0.2in (5.08mm)
	SMA 	SMA Antenna Connector

NOTES ON PARTS:

You will need ONLY ONE SMA Antenna Connector as shown in the Schematics and Breadboard diagrams in these files:
	Colpitts_Bread Board.jpg
	Colpitts_schematic.jpg

The reason you will find two SMA connectors in the .fzz Schematics and Breadboard 
is because the PCB is made double sided and to accept the SMA to be soldered on both sides, so two had to be inluded in the drawing.

By calculation, the Tank Circuit with the following values oscillates at a frequency within the HAM Radio 80m Band.:
		L = 3.3 µH 
		C = 560 pF
		fRes = 3.702 MHz

C1 and C2 should make for the oscillation around 3.700 MHz when L1 is .3 µH but didn't in my first tests. I measured a frequency too close to 3.800 MHz, 
that is the Upper band edge in Europe for the 80m HAM Radio Band, so it is not allowed and hence not of use to build a Transmitter for experimental use.

I found by measuring my Ceramic Capacitors that they tend in general to have LESS capacitance than their label says.
Hence C3. With C3 I got a nice sine wave @ 3.740 MHz, in the 80m HAM Radio Band, but just.
So I left space to add C4 that can be Variable Capacitor for more precision and compliance to transmission rules.

With this board design one is not limited to the frequency given here.
By varying the values of L1 and C1 and combined value of C2+C3+C4,
other frequencies can be indeed obtained without changing other components.
It is best practice that C1 and C2+Cn are in a ratio of 1:10 or 3:10.


POWER:

I run the board at 9V.
I tested the board @ 12V for a brief period of time.



USEFUL RESOUCES:

	Resonant Frequency Calculator
	https://www.1728.org/resfreq.htm

	Capacitors in Series Calculator
	https://www.omnicalculator.com/physics/capacitors-in-series

	Capacitor uF - nF - pF Conversion Chart
	https://de.farnell.com/en-DE/uf-nf-pf-capacitor-conversion-table



COMPONETS KITS:

	80pcs 6 mm trimmer capacitor variable capacity ceramic electronic capacitor kit 5/10/20/30/40/60/70/120P 

	BOJACK 20 Values 200 Pieces Inductors 1 uH to 4.7 mH 0.5 W Colour Ring Inductors 1/2 Watt Assortment Kit 

	AUKENIEN 24 Value 600 Piece Ceramic Capacitor Set Capacitors Assortment from 10pF to 100nF Ceramic Capacitor Kit 

	BOJACK 600-Piece 15 Value Ceramic Capacitor Kit (10 pF, 20 pF, 30 pF, 47 pF, 56 pF, 68 pF, 100 pF, 220 pF, 330 pF, 680 pF, 1 nF, 4.7 nF, 10 nF, 47 nF, 100 nF) 

	HUAREW 10 Values 300 Pieces Ceramic Capacitor 0.1 0.15 0.22 0.33 0.47 0.68 1 2.2 4.7 10 uF / 100-10000 nF Classification Kit 

	Heevhas 60 Pieces 5.08 mm 2 Pin & 3 Pin PCB Screw Terminal Block Solderable Connector 300 V 16 A for Arduino DIY Project (50 x 2 Pin, 10 x 3 Pin) 



HOUSING:

The PCB is designed to be housed in a
"Circuit Board Instrument Aluminium Cool Box 40 x 50 x 80 mm DIY Electronic Project Housing".



WARNING and DISCLAIMER: 

You may need a HAM Radio licence to operate this oscillator in your country 
unless your local regulations make exceptions such as: 
	for the very low power emitted;
	working under guidance of a licenced HAM Radio Operator.
Please don`t attach an Antenna to it unless you know what you are doing, thank you.
Will require a filter.



LiCENSE:

This work is dedicated to the public domain.


