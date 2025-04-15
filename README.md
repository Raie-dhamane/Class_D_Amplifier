# CLASS D Amplifier

![Image](https://github.com/user-attachments/assets/ac7fbe0b-96c2-4320-b43f-442b9a394374)
![Image](https://github.com/user-attachments/assets/fea2148a-39ff-4611-8326-15ba9979bc86)

#Introduction

A Class D amplifier is a highly efficient audio amplifier that operates by rapidly switching its output transistors fully on and off. It generally uses a comparator, to which triangular wave and audio wave are given as input, driver for MOSFET or BJT and a LC low pass filter for filtering. Theoretically, Class D amplifiers can achieve 100% efficiency since the transistors either conduct with minimal voltage drop or are completely off, resulting in negligible power loss. In practice, efficiencies above 90% are common. Compared to other amplifier classes, Class D amplifiers are much more superior. So, I have designed a class D amplifier without using any specific IC but using simple components, here is how it goes.
Flow Chart
![Image](https://github.com/user-attachments/assets/d8093332-2c1c-493c-8e29-49505fa5682c)


#Components used and their Justification

1.	NE555 Timer  IC

This IC is used to generate triangular wave wave which serves as the carrier signal for PWM generation.It is highly stable, easily configurable timer timer capable of generating frequencies in the range needed for audio PWM applications. It is configured in astable mode to generate the triangle waveform.

2.	LM393 Comparator 

It Compares the incoming analog audio signal with the triangle wave to generate a PWM signal. It’s a dual comparator with an open collector output, making it suitable for PWM signal generation. Also known for fast response times and low output saturation voltage.

3.	LM2941CS 

It is a Linear Voltage regulator which Provides a stable regulated voltage supply for sensitive analog components like NE555 and LM393. In this circuit I have used a screw terminal to give input of 12 Volts and give that 12V to LDO which steps down it to 5V 

4.	Inductor (IFDC03030EZR101M)

I have used a 100Uh inductor for low pass filter followed by a capacitor. Suitable for filtering frequencies around the 100kHz PWM carrier. Value selected to balance between size, cost, and cutoff frequency.

5.	PJ-002AH-SMT-TR

It is a SMD audio jack which is used for input audio wave.

6.	Transistors

•	Small Signa BJT

NPN - I have used BC547. Ita max Collector Current is 100mA–200mA with Transition Frequency of 300 MHz for fast switching. it is widely available, low noise, fast, and reliable for signal-level tasks

PNP- BC557 is used. Its max Collector Current is 100mA–200mA and it is Complement to BC547 

•	High Signal BJT( More than 1A)

NPN - TIP31C is used. Its max Collector Current is 3A. Power Dissipation is High, with proper heatsinking. It is suitable for switching applications with good gain

PNP  - I have used TIP32C. its max Collector Current is 3A. it is Complementary to above NPNs Matches NPNs in specs; used in push-pull or H-bridge Class D topologies.


7.	LED 

Power-on or signal activity indicator.

#PCB Design Notes

1.	Component Placement:

•	PWM generator (NE555 & LM393) is placed close together to minimize noise and ensure tight timing.
•	Power components (BJTs, inductor) are grouped to shorten high-current traces and reduce EMI.
•	Filtering capacitors (input decoupling and output filtering) placed close to respective ICs to reduce noise and voltage ripple.

2.	Routing Strategy:

•	Ground plane on the bottom layer to reduce noise.
•	Signal traces routed away from power switching nodes to avoid coupling.

3.	Thermal Consideration:

•	BJTs have thermal relief pads.
•	Copper pour used around power components for heat spreading.


