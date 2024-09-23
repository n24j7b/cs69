java c
ECE 511: Analog Integrated Circuits 
Homework #4 
Fall 2024 
Due date: Monday, 23-Sep-2024
For the questions below, assume the following device parameters:
k’n=μnCox =100 μA/V2 , k’p=μpCox=50 μA/V2 , λ=0.12 V-1 at L=90nm, minimum L = 45nm Vto,N=|Vto,P|= 0.4V, neglect body effect and |VLIN|
1)   Design an NMOS simple current mirror that generates a 500 µA output current using a 100 µA reference current. This mirror should provide the output current with less than 5% error  across an output voltage that varies between 0.7 V and 1.5 V (this means the current can vary between 475 and 525 µA across 0.7 to 1.5 V). Do the following:
a.   Estimate the output resistance required of the current source using the following formula and DC current: Rout = {1.5 V – 0.7 V} / {Current(1.5V) – Current(0.7V)}
b.   Draw a clear and easy-to-read schematic of your design, specifying the width and length of both devices.
c.   Validate your results by calculating the output currents across the voltage range
d.  At which output voltage is the output current exactly equal to 500 µA?
e.   Calculate the small signal output resistance of the output and compare it to (a).
f.    Calculate the total area of your design, including both reference and output devices
g.   How much larger would the devices need to be to achieve 0.5% accuracy? 
2)   Design an NMOS cascode current mirror that generates a 500 µA output current using a
100 µA reference current. This mirror should provide the output current with less than 0.5% error across an output voltage that varies between 0.7 V and 1.5 V. Do the following:
a.   Estimate the output resistance required of the current source using the following formula and DC current: Rout = {1.5 V – 0.7 V} / {Current(1.5V) – Current(0.7V)}
b.   Draw a clear and easy-to-read schemat代 写ECE 511: Analog Integrated Circuits Homework #4 Fall 2024Python
代做程序编程语言ic of your design, specifying the width and length of all devices.
c.   Validate your results by calculating the output currents across the voltage range
d.  At which output voltage is the output current exactly equal to 500 µA?
e.   Calculate the small signal output resistance of the output and compare it to (a).
f.    Calculate the total area of your design, including both reference and output devices
g.   Compare the area of 2(f) with the area calculated in 1(g).
3)   For the differential amplifier below, assume that all devices have W/L=50, L=90nm, and Vdd=3.3V.
a.   Calculate the common-mode input range
b.   Calculate the differential-mode small-signal gain in decibels
c.   Calculate the common-mode small-signal gain in decibels
d.   Calculate the CMRR in decibels
4)   Design a differential amplifier with a current-mirror load to achieve >25 dB differential-
mode gain with CMRR > 30 dB. You should use one of your current mirrors from Q1 or Q2 and assume Vdd=3.0V. All other aspects of the design are up to you.
a.   Specify W and L for all devices. Note: in this problem, I want you to notice how 
many degrees of freedom exist. In fact, there will be an infinite number of possible solutions. This is often the case in design, especially ones that do not have many performance metrics. As we progress, we will add more metrics, such as power consumption, bandwidth, output swing, noise performance, and stability. 
b.  Validate the performance of your amplifier for a common-mode bias of 1.2 V.
c.   If you work in a group to complete the homework, please ensure that each person in the group turns in a different design point and then include a short statement on what distinguishes your design compared to your partner(s).







         
加QQ：99515681  WX：codinghelp
