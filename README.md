### EXPERIMEN-07-DEVELOPMENT-OF-LADDER-LOGIC-FOR-TIMER-ONDELAY-FUCTION-ON-PLC-HARDWARE-

### AIM 
To develop and execute a ladder logic program using an ON-Delay Timer (TON) in Delta SV2 PLC, and observe its behavior on PLC hardware.
### Hardware & Software Required:
Component	Specification
PLC	Delta SV2 Series (e.g., DVP-SV2)
Programming Cable	USB to RS232/RS485
PLC Software	WPLSoft (for programming Delta PLCs)
Input Devices	Push Button (NO)
Output Devices	LED Indicator / Lamp
Power Supply	24V DC for I/O, 230V AC for PLC (as per specs)
### Theory:
An ON-Delay Timer (TON) starts counting after the input condition is TRUE. The output turns ON after the preset time elapses.

## TON Instruction Format in Delta PLC:
T0 K500  // T0 = timer number, K500 = 500 x 10ms = 5 sec delay
Wiring Diagram (Example):
PLC Input	Description
X0	Push Button (NO)
Y0	Output Indicator (e.g., lamp)
## Ladder Logic Diagram:


|-----[ X0 ]------------[TON T0 K50]------------------|
|                                               |
|-----[ T0 ]------------------------------------[ Y0 ]|

X0: Start push button
T0: Timer 0
K50: Time delay (K50 = 50 × 10ms = 0.5 sec)
Y0: Output coil (Lamp or LED)
## Steps to Program in WPLSoft:
1.	Open WPLSoft and create a new project.
2.	Select PLC Model: DVP-SV2.
3.	In the ladder editor: Add a normally open contact X0.
4.	Add a TON instruction for T0 with preset K50.
5.	Add a normally open contact T0 connected to coil Y0.
6.	Compile the ladder logic.
7.	Connect PLC via USB and download the program.
8.	Set PLC to RUN mode.
Procedure:
•	Wire the push button to X0 and lamp to Y0.
•	Power ON the PLC and load the program.
•	Press X0; the timer starts.
•	After 0.5 sec, Y0 turns ON.
•	Release X0; the timer resets.
### Observation Table:
S.No	Input (X0)	Time Delay (sec)	Output (Y0)
1	Pressed	0.5	ON
2	Not Pressed	0	OFF
### Conclusion:
The ON-Delay timer function was successfully implemented using Delta SV2 PLC. The output activated after a 0.5-second delay once the input was turned ON.
