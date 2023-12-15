---
title: "NETWORK CLOCK"
collection: publications
permalink: /publication/network_clock
excerpt: ''
date: 2023-09-06
venue: 'Digital Electronics'
paperurl: ''
citation: 'CLOCK'
---
## INTRODUCTION
<div style="text-align:justify"> A table clock will be designed that will display the hour, minutes and seconds. It is called a network clock because the time base will be obtained through the frequency available in the 230V AC socket. It will display the seven segments that show the data in BCD code. A system to set the clock in time will be implemented. This proyect will consist of three perfectly differentiated sections.</div>

<div style="text-align:justify">         1. In the first section the clock will be implemented in the Proteus simulation program with logic gates and flipflops.
simulation program with logic gates and flipflops. All this to implement the given syllabus. It is
The schematic and simulation created will be presented. </div> 

<div style="text-align:justify">         2. In the second section, dedicated integrated circuits will be used for its implementation this time.
dedicated integrated circuits will be used for its implementation. In this case the dedicated circuit 4510, 4040 will be used.
Finally, a conclusion is drawn. </div> 
<br>
## First Step: Gates and FF  
# Power supply
We start by incorporating the power supply by which our system will work and also by which our system will take the frequency. We start by putting a sinusoidal alternating signal generator and connect it to a Nand gate (trigger schmitt) but the resulting signal from that connection will be the CLK signal, but inverted so we will place another Nand gate (trigger schmitt) and if the resulting quadratic signal would already be for our system. To see that everything works correctly an oscilloscope is placed with the three elements: The sinusoidal input of the circuit. The output of the first quadratic gate inverted and the output of the second final quadratic gate. All this will be done by means of terminals that will be called input, inverseclk and clkoutput. 

# FF as frequency dividers
In the frequency divider the JK 4027 will be applied and the set and reset will be set to values of GND in this case is associated with the VSS tag. The voltage will be applied to the JK with the tag VDD. The CLK will be applied from the previous frequency source. This arrangement is repeated six times. Then the Q is connected to the CLK of the next one. Finally, the Q of the last JK will have the output connected to a timer to measure output connected to a timer to measure the resulting frequency. At In this case, one should be output. As can be seen in figure two is correct.

# 4-Bit Counter
The same structure of the frequency divider is taken, but this time only four JK. This time we assign an output to the Q'. They are named from left to right. This time the input CLK will be the 1Hz output of the previous circuit. These values will be assigned to the Q' because they will be the values that will go into our decoder and into a logic gate circuit that will reset the circuit to prevent it from counting beyond the number nine. 

# Encoder for Reset
We continue with the previous 4 bit counter and this time we want to apply a Reset when the counter reaches nine. Therefore, we want the counter to be reset when the counter reaches 1010. Therefore, inputs A and C will be those at zero and inputs B and D will be those at one. To perform the reset an encoder containing two Not gates and three Nand gates is made. When all the gates are connected, if it reaches ten, the Reset is set to one and therefore the system starts again to count from zero. To improve the jump in the display the reset will be assigned to the JK sets. 

# Counter Display with Reset 
Now that the Reset and the Counter have been completed, there is only one step left to display the figures that are being counted. counting. With the display we will be able to observe the numbers that are being counted besides to verify that indeed it stops counting when arriving at number nine and it is put in zero. We will take a seven-segment display that is a common cathode and assign the inputs from a decoder to the display. In this case between the decoder and the display we could put a resistor to protect the display leds. The last three inputs of the encoder are placed as follows: both LT and BI are assigned the VDD and LE is assigned the ground with the name of VSS. 

# Hour Reset Encoder
In order to be able to count in units and tens, the previous encoder has been duplicated about four times more since both the tens of seconds and the tens of minutes comply that when the counter reaches six the circuit is reset. But on the other hand in the hours another encoder must be made so that it is reset when it reaches the figure of twenty-four hours. To do this we will put two encoders linked with an AND gate in which in the units only counts up to four as long as in the tens it reaches two. We had also created an encoder the same as the others in the units to count up to the number nine. To tell it to reset both when the units reach new and when it reaches twenty-four, an OR gate will be placed that will apply a reset in both cases. All this can be visualized in figures six and seven. It can be seen in the OR gate that both in the case that resetting of the time units in the time units in one and that the reset of the of the tens of hours is set to one, the counter of the hours is reset and counter is reset and reset to zero.

# Reset of unit counters.
In order to be coordinated, a pulse signal linked to OR gates is introduced to all the units reset so that it is executed in the two states. The resulting signal of this circuit will be put in the 4 bit counters of the units of seconds, minutes and hours. 

# Set the time
The circuit has already been completed as a counter from scratch, but it still needs one last step to become a clock. That is to say, to set the clock to start counting from the time entered. To do this we will have to create a switch that switches between two states: the normal CLK that we have had so far and the set time that is created new at this time. When the switch is with the CLK the system will count and when it is in the set time we will be able to assign the time with specific buttons. Each button is pressed to give voltage to the circuit that can count on each pulse. We will have to create three multiplexers for each one. In the case of the seconds we will set the clock signal to vary depending on the pulse, the time and the clk. If the pulse is one, the reset will be set to one. If it is zero, the normal clk will be executed. This circuit structure is also true for the other two multiplexers and each pulse is assigned to each four-bit counter. In order to achieve that you should not be constantly pressing the button to set the time can be placed directly from the outputs of the FF of the frequency divider outputs and assign them to the buttons so that when left pressed is a quadratic signal that enters. 

# Complete circuit construction
In order to relate the units to the tens in seconds, minutes and hours, the following will be done. The 4-bit counter will be duplicated five more times since we need tens and units for seconds, minutes and hours. In total five encoders are created. The outputs of the units encoders are assigned to the reset of the counters which has a pulse. the reset of the counters which has a pulse. The outputs of the counter reset are assigned to the sets of the unit counters. the unit counters. The encoder of the hours will have two conditions and not only one. and not only one, so an OR gate is set. The output of the same is put in the OR gate with the pulse input. pulse input. The different encoders with their displays are renamed and assigned corresponding names. The different encoders with their displays are renamed and assigned the corresponding names. Finally, everything explained above about the multiplexers and their the multiplexers and their relation to the switches is applied to the system. 

## Second section: Simplification with IC.
In order to simplify the circuit, various integrated circuits are applied.
# Frequency divider
In order to replace the six JKs that we have to make the frequency divider, we will replace the whole circuit with an integrated circuit called 4040. This integrated circuit has a clock input that will be put the one that comes out of the source that has 50 Hz and has twelve outputs. The higher the output number the lower the output frequency of the circuit making our counter slower. It is arranged that the first six outputs are labeled to be able to make later with the buttons and with the switch automatic changes when leaving the button pressed and to be able to choose different speeds depending on what is needed at the moment. 

# Counters
In this case, all the FF chains have been replaced by integrated circuits of type 4510. In the first one, the input has been assigned to the clock signal of the first multiplexer in order to operate both the count clock signal and the signal that is produced when a button is pressed to make the signal manually and thus be able to set the clock on time. The VDD voltage is added to the U/D' input and the rest of the input pins are grounded. Each output Q will be assigned to its corresponding decoder to be connected to the display so that it can show the numbers. The CO output will be assigned to the next tens of seconds counter so that it can start the signal when the unit counter is reset. The tens of second counter will receive the CO output as its clock signal. The difference between the tens and the units is its reset and therefore the MR port will be connected to the tens of seconds encoder to stop counting up to six. In this case the integrated circuit without the need of new encoders counts only up to nine. The minute counters will have the same structure as the second counters, having the connection of the CO port with the CLK of the next one. In the case of the hours it will be connected to the encoder that can only count up to the number twenty-four. Only the unit counters receive the clock signal from the multiplexers for the correct operation of the buttons.

# Final circuit


