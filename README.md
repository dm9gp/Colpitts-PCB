# Colpitts-PCB
PCB for a Colpitts Oscillator in common base configuration. 

Open in Fritzing to view the schematics, inspect or modifiy the circuit. 

There are more accurate oscillators available today, if for example your are looking to make a radio transmitter.
Nevertheless, the Colpitts Oscillator, here in common base configuration, works and produces a nice sine wave.
Because it can be built on a Breadboard or with the PCB available here,
and because it can be made from components that are ready available,
it is a great tool to grasp the concept of a tank circuit and a fun soldering project too.
Inspect one with an Oscilloscope too, for example.

See it here in this video in action: https://www.youtube.com/watch?v=HrsZrhiRcEc


GET STARTED:

To make the Oscillator you will need a Breadboard or 
print the PCB file (in the latest version) or have the PCB printed for you,
the PCB file is in "Fritzing" format .fzz.
You can open it in "Fritzing" (https://fritzing.org/) to first check it, modify it 
and then have it printed by a PCB printing service of your choice,
such as AISLER (https://aisler.net/), if you wish.

You will also need the componets listed below.
	
	C1 	Ceramic Capacitor	3.3nF
	C2 	Ceramic Capacitor	680pF
	C3 	Ceramic Capacitor	68pF to 220pF
	C4 	Variable Capacitor	0-120pF variable (optional)
 	C5 	Variable Capacitor	0-120pF variable (optional)
	C6 	Ceramic Capacitor	1µF
	C7 	Ceramic Capacitor	30pF
	L1 	Inductor		3.3 µH
	R1 	Resistor		100kΩ 
	R2 	Resistor		100kΩ 
	R3 	Resistor		47kΩ
	R4 	Resistor		1kΩ
 	Q1 	NPN-Transistor		BC547 or 2N3904
  	GND&SIG Generic male header	2 pins 	pin spacing 0.1in (2.54mm)
 	+9V	Screw terminal		2 pins 	pin spacing 0.2in (5.08mm)
	SMA 	SMA Antenna Connector	(optional)


BOARD AND CIRCUIT DESIGN:

You will need ONLY ONE SMA Antenna Connector as shown in the Schematics and Breadboard diagrams in these files:
	Colpitts_Bread Board.jpg
	Colpitts_schematic.jpg

The why reason you will find two SMA connectors in the .fzz Schematics and Breadboard 
is because the PCB is made double sided, to accept the SMA to be soldered on both sides, two had to be inluded in the drawing.

By calculation, the Tank Circuit oscillates at a frequency within the HAM Radio 80m Band, with the following values:
		L = 3.3 µH 
		C = 560 pF
		fRes = 3.702 MHz

C1 and C2 should make for the oscillation around 3.700 MHz when L1 is 3.3 µH but didn't in my first tests. I measured a frequency too close to 3.800 MHz, 
close the upper edge for the 80m HAM Radio Band in IARU Region 1, so it is not of use to build a Transmitter for experimental use in Europe.

Measuring the Ceramic Capacitors I found that they tend to have LESS capacitance than their label says.
Hence I added C3 for additional capacity.
With C3 68pF I obtained a nice wave form at 3.7MHz. 
With C3 220pF I got a nice sine wave @ 3.740 MHz on a different board  also in the 80m HAM Radio Band, but just:
the components have tolerance.

I left space to add C4 and C5 that can be Variable Capacitors for more precision and compliance to transmission rules.
With C4 Variable Capacitor 0-120pF, I could tune the signal between 3.63 MHz and 3.70 MHz, which is well withinin the HAM Radio 80m Band for all modes. 
With C4 100pF I measure 3.63 MHz fixed frequency, again, these parts have tolerance.
However, I found that adding variable capacitors decreases the amplitude of the signal even down to 1.5V less peak-to-peak, 
the variable capacitors dampen the signal. I decided to leave them out for myself.

What worked best for me was testing C3 by inserting it on the PCB before soldering it to the board.

With this board design, one is not limited to a frequency in the 80m Band.
By varying the values of L1 and C1 and combined value of C2+C3+C4+C5,
other frequencies can be indeed obtained without changing other components.
It is best practice that C1 and C2+Cn are in a ratio of 1:10 or 3:10.



COMPONETS KITS EXAMPLES:

	80pcs 6 mm trimmer capacitor variable capacity ceramic electronic capacitor kit 5/10/20/30/40/60/70/120P 

	BOJACK 20 Values 200 Pieces Inductors 1 uH to 4.7 mH 0.5 W Colour Ring Inductors 1/2 Watt Assortment Kit 

	AUKENIEN 24 Value 600 Piece Ceramic Capacitor Set Capacitors Assortment from 10pF to 100nF Ceramic Capacitor Kit 

	BOJACK 600-Piece 15 Value Ceramic Capacitor Kit (10 pF, 20 pF, 30 pF, 47 pF, 56 pF, 68 pF, 100 pF, 220 pF, 330 pF, 680 pF, 1 nF, 4.7 nF, 10 nF, 47 nF, 100 nF) 

	HUAREW 10 Values 300 Pieces Ceramic Capacitor 0.1 0.15 0.22 0.33 0.47 0.68 1 2.2 4.7 10 uF / 100-10000 nF Classification Kit 

	Heevhas 60 Pieces 5.08 mm 2 Pin & 3 Pin PCB Screw Terminal Block Solderable Connector 300 V 16 A for Arduino DIY Project (50 x 2 Pin, 10 x 3 Pin) 



HOUSING:

The PCB is designed to be housed in a
"Circuit Board Instrument Aluminium Cool Box 40 x 50 x 80 mm DIY Electronic Project Housing".


POWER and FREQUENCY:

I run the board at 9V.
I tested the board @ 12V too.
At higher voltages the frequencies of oscillation increases, with a frequency counter I measured 0.1 Mhz higher at 12V than at 9V.
I compared the frequency reading of the same oscillator from 2 different oscillisocpes with a frequency counter.
I found the 2 readings from the oscilloscopes consistent between each other and both ever so slightly lower than the reading from the frequency counter, 
for example one board gave me 3.69 MHZ on the oscilloscope compared to 3.64 from the frequency counter. 50kHz difference is good enough for me here.


THE CIRCUIT:

The oscillation frequency is given by L1 and C1+C2 that make up the tank circuit.
C3 and C4 allow to add more capacitance to be added to C2 because the compenents have tolerance and the resulting capacity may fall short of the calcaluted value.
A best practice is to have the values of C1 and in C2 in ratio of 1:10 up to 3:10.
C6 is the coupling capacitor, it blocks the DC signal and only passes the AC signal:
after C6 the sine wave oscillates above and below the 0V value, rather than around a particular voltage value,
C6 filters the DC out, we have our signal. It removes the DC component at the output of the curcuit, after C6 the wave oscillates with values higher and lower around the 0V line on the oscilliscope, 
before C6 the same sine wave oscillates around a value that is below or above the 0V line, it is DC offset.
C7 maintains the voltage value seen at the base of the transistor.
Without C7 the oscillator does not work. I tested values higher than 1µF, these did not change the shape of the sine wave.
I got the best results in terms of waveform with values in some cases down to between 20pF and 100pF. 
R1+R2 and R3 are the voltage divider, to ensure sufficient voltage difference between the transistor's base and emitter.
The role of R4 is to control the amplifiers voltage gain.

Although I find the frequency to be stable, per their nature, Oscillators are susceptible to variations due to ambient temperature changes and heating up.
When I touched the inductor, the amplitude of the wave incremented every so slighlty, almost not at all, 
I was expecting and hoping for little more change for demonstration purposes of the effect of temperature change.
Hook it up to an Oscilloscope or Frequncy Counter and try warming the Inductor L1 (gently) to see what happens.



THE VOLTAGE DIVIDER:

I used 100kΩ for R1 and 100kΩ for R2 but they could be substituted with a 200kΩ Resistor;
the board allows flexibilty to play with different values for the voltage divider;
for example a total value for R1+R2 of 15kΩ with R3 5.6kΩ should work too with an R4 of 68Ω.

Some exaple tests:

	INPUT	9V
	R1+R2	200kΩ
	R3	47kΩ
	R4 	1kΩ
 	C7	1µF
	Vout	4V  Peak-to-peak

	This combination is giving me the purest waveform:
 	INPUT	9V		
	R1+R2	200kΩ
	R3	47kΩ
	R4 	1kΩ
 	C7	30pF
	Vout	3V  Peak-to-peak

	INPUT	9V
	R1+R2	200kΩ
	R3	47kΩ
	R4 	2kΩ
 	C7	1µF
	Vout	2V  Peak-to-peak

 	INPUT	9V
	R1+R2	200kΩ
	R3	47kΩ
	R4 	3kΩ
 	C7	1µF
	Vout	1.8V  Peak-to-peak

  	INPUT	9V
	R1+R2	200kΩ
	R3	47kΩ
	R4 	290Ω
 	C7	1µF
	Vout	9V  Peak-to-peak

 	INPUT	9V
	R1+R2	200kΩ
	R3	47kΩ
	R4 	290Ω
 	C7	20pF
	Vout	5V  Peak-to-peak

 	INPUT	12V
	R1+R2	200kΩ
	R3	47kΩ
	R4 	2.9kΩ
 	C7	1µF
	Vout	3V  Peak-to-peak

	
	With an 100Ω Potentiometer at R4 and got:

 	INPUT	9V
	R1+R2	15.6kΩ
	R3	5.6kΩ
	R4 	30Ω
 	C7	20pF
	Vout	9V  Peak-to-peak
 	
  	INPUT	9V
	R1+R2	15.6kΩ
	R3	5.6kΩ
	R4 	40Ω
 	C7	20pF
	Vout	12V  Peak-to-peak

	INPUT	12V
	R1+R2	15.6kΩ
	R3	5.6kΩ
	R4 	40Ω
 	C7	20pF
	Vout	8V  Peak-to-peak

	Try your own test perhaps? What values you obtain with the following?

	R1+R2	18kΩ
	R3	4.7kΩ
	R4 	100Ω
	Which value for C7 gives you the best waveform? 
  
 
 
USEFUL RESOUCES:

	Resonant Frequency Calculator (https://www.1728.org/resfreq.htm)

	Capacitors in Series Calculator (https://www.omnicalculator.com/physics/capacitors-in-series)

	Capacitor uF - nF - pF Conversion Chart (https://de.farnell.com/en-DE/uf-nf-pf-capacitor-conversion-table)



WARNING and DISCLAIMER: 

You may need a HAM Radio licence to operate this oscillator in your country 
unless your local regulations make exceptions such as: 
	for the very low power emitted;
	working under guidance of a licenced HAM Radio Operator.
Please don't attach an Antenna to it unless you know what you are doing, thank you, it will require a filter.
It is an electronics project that requires power, handle accordingly.



LICENSE:

This work is dedicated to the public domain.


