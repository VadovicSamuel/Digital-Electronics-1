# Morse code reciever

### Team members

* Member 1 (responsible for xxx)
* Member 2 (responsible for xxx)
* Member 3 (responsible for xxx)
* ...

### Table of contents

* [Project objectives](#objectives)
* [Hardware description](#hardware)
* [VHDL modules description and simulations](#modules)
* [TOP module description and simulations](#top)
* [Video](#video)
* [References](#references)

<a name="objectives"></a>

## Project objectives

Our project objective is to recieve and convert a morse code signal and represent it on 7-segment display embedded to Nexys-A7-50T circuit board. <br>

By recieving a morse signal either through Arduino microcontroller or switch embedded on Nexys-A7-50T board we desire to count the lenght of impulse
and then assume the represented morse code character. 
![Objective](https://github.com/VadovicSamuel/Digital-Electronics-1/blob/main/Project-Images/ObjectiveIMG1.png)


<a name="hardware"></a>

## Hardware  
#### Nexys-A7-50T

The Nexys A7 board is a complete, ready-to-use digital circuit development platform 
based on the latest Artix-7™ Field Programmable Gate Array (FPGA) from Xilinx®. 
With its large, high-capacity FPGA, generous external memories, and collection of 
USB, Ethernet, and other ports, the Nexys A7 can host designs ranging from introductory combinational circuits to powerful embedded processors. 
Several built-in peripherals, including an accelerometer, temperature sensor, MEMs digital microphone, a speaker amplifier
,and several I/O devices allow the Nexys A7 to be used for a wide range of designs without needing any other components.
<br>
![Nexys-A7-50T](https://github.com/VadovicSamuel/Digital-Electronics-1/blob/main/Project-Images/NexysA750T.png)<br>
#### Arduino Uno
Arduino Uno is a microcontroller board based on the ATmega328P. 
It has 14 digital input/output pins (of which 6 can be used as PWM outputs), 6 analog inputs, a 16 MHz ceramic resonator (CSTCE16M0V53-R0), 
a USB connection, a power jack, an ICSP header and a reset button.

![Nexys-A7-50T](https://github.com/VadovicSamuel/Digital-Electronics-1/blob/main/Project-Images/ArduinoUnoFF.png)<br>



<a name="modules"></a>


## VHDL modules description and simulations

### clock_enable.vhd
  1. generates clock signal pulses
  2. enables clock signal by counting rising edges
  3. outputs the clock enable signal
  4. resets the local counter
  
[Link to clock_enable.vhd](https://github.com/VadovicSamuel/Digital-Electronics-1/blob/main/ProjectDS/clock_enable.vhd)
### counter.vhd 
  1. counts the clock enable impulses
  2. if counter signal exceedes the limit of numbers it can process, it resets the overflow output
  3.
  4.
  
[Link to counter.vhd](https://github.com/VadovicSamuel/Digital-Electronics-1/blob/main/ProjectDS/counter.vhd)
### d_ff_rst.vhd
  1. prevents reset if input is held for too long 
  2. after longer period of time, while input is still being pressed, writes input into output
  3.
  3.
  4.
  
[Link to d_ff_rst.vhd](https://github.com/VadovicSamuel/Digital-Electronics-1/blob/main/ProjectDS/d_ff_rst.vhd)
### d_ff_rst7bit.vhd
  1. switches 7-segment display off
  2. after longer period of time, while input is still being pressed, writes input into output
  3.
  4.
  
[Link to d_ff_rst7bit.vhd](https://github.com/VadovicSamuel/Digital-Electronics-1/blob/main/ProjectDS/d_ff_rst7bit.vhd)
### decoder.vhd
  1. takes the lenght of counter output 
  2. if counter output is less than 3, decoder sets its output to '0', which is represented as dot
  3. if counter output is more than 3, decoder sets its output to '1', which is represented as dash
  4. after recieving counter output higher than 7, decoder resets and determines the number of characters recievied, which are then conveyed to its output
  
[Link to decoder.vhd](https://github.com/VadhovicSamuel/Digital-Electronics-1/blob/main/ProjectDS/decoder.vhd)
### display control.vhd
  1. assigns characters their display positions
  2.
  3.
  4.
  
[display_control.vhd](https://github.com/VadovicSamuel/Digital-Electronics-1/blob/main/ProjectDS/display_control.vhd)
### edge detector.vhd
  1. changes input from low to high or high to low 
  2. 
  3.
  4.
  <br>
[Link to edge_detector.vhd](https://github.com/VadovicSamuel/Digital-Electronics-1/blob/main/ProjectDS/edge_detector.vhd)
### hex_7seg.vhd
  1. assigns decoder output and {}{}{}{}{} their respected characters from alphabet or decimal numbers
  2. as every character has its specific set of on and off segments, this module proceeds to display it on 7-segment display
  3. 
  4.
  
[Link to hex_7seg.vhd](https://github.com/VadovicSamuel/Digital-Electronics-1/blob/main/ProjectDS/hex_7seg.vhd)
### shift_register.vhd
  1. stores the dots and dashed obtained in decoder
  2. 
  3.
  4.
  
[Link to shift_register.vhd](https://github.com/VadovicSamuel/Digital-Electronics-1/blob/main/ProjectDS/shift_register.vhd)
### shift_register7bit.vhd
  1. 
  2.
  3.
  4.
  
[Link to shift_register7bit.vhd](https://github.com/VadovicSamuel/Digital-Electronics-1/blob/main/ProjectDS/shift_register7bit.vhd)





<a name="top"></a>

## TOP module description and simulations

### top.vhd

[Link to top.vhd](https://github.com/VadovicSamuel/Digital-Electronics-1/blob/main/ProjectDS/top.vhd)

<a name="video"></a>

## Video

Write your text here

<a name="references"></a>

## References

1. Write your text here.

