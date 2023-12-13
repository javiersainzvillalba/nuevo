---
title: "EPROM MEMORY"
collection: publications
permalink: /publication/emprom_memory
excerpt: ''
date: 2023-09-06
venue: ''
paperurl: ''
citation: 'EPROM'
---
# INTRODUCTION
<div style="text-align:justify"> A circuit will be designed to simulate the lights of a traffic light based on a 4040 frequency divider, an And gate that will serve to reset the system, an Eprom memory that will be programmed in HxD so that it can work correctly, three LEDs that represent the status of the traffic light and finally a seven-segment BCD encoder with a seven-segment common anode display to show the remaining seconds of the status. </div> 
<br>
# SYSTEM CONSTRUCTION
## Power Supply
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <style>
    /* Estilo para el contenedor principal */
    .contenedor {
      display: flex; /* Usa flexbox para organizar los elementos en fila */
      align-items: center; /* Centra verticalmente los elementos */
    }
  </style>
</head>
  
<body>
<!-- Contenedor principal -->
<div class="contenedor">
  <!-- Área del texto (parte izquierda) -->
  <div class="texto">
    <p> <div style="text-align:justify"> We put a power supply for the operation of the system by putting an AC signal generator at a frequency of 3Hz. All this to be able to see the operation of our system. The necessary changes are made to convert the AC signal into a pulse signal and its correct operation can be checked. Next, we put a frequency divider that will be connected to our Eprom memory. We have put 5 volts to the pulse signal so that our system works correctly. In this case only the outputs of the frequency divider from Q0 to Q4 will be used. </div> </p>
  </div>
  <!-- Área de la imagen (parte derecha) -->
  <div class="imagen">
    <img src="https://javiersainzvillalba.github.io/images/EPROM1.png" alt="ddd" height="2651" width="2442">
  </div>
</div>
</body>
<br>

# Frequency divider 4040
<div style="text-align:justify"> In this frequency divider the outputs of Q0 to Q4 will be put to the inputs A0 to A4 of the Eprom memory, all this so that it receives with different frequencies the pulse signal of our system. Slower the signal of A0 and faster the signal of A4. Giving as a result that these outputs will count from 0 to 8. </div> 
<br>
# AND Logic Gate
<div style="text-align:justify"> A gate and will be set so that when the Eprom memory inputs A1, A2 and A4 are set to one the system starts over again. And these are these outputs because it is when the system reaches 21 that the system starts again. If you wanted to start again from 12 you would only have to set the outputs A2 and A3 and so on. </div>
<br>
# LEDS
<div style="text-align:justify"> We will connect to the output of the Eprom memory three leds in the outputs D4, D5 and D6. The outputs are red, yellow and green respectively. When programming the Eprom memory we will be able to visualize how these memory outputs are only activated in very specific occasions. </div>
<br> 
# Counter Display
<div style="text-align:justify"> Finally we put a display with its respective encoder. In this case it is a seven-segment common anode type display with a 7447 decoder. Power is supplied to the display and it will receive the BCD numbers through the decoder outputs. Previously the decoder receives the information from the Eprom memory from which it will take the values. Later it is explained in a table how this implementation has been made. </div>
<br> 
# Eprom Memory
<div style="text-align:justify"> This is the most important part of the proyect and the one that will allow it to work correctly. The different frequencies received from the frequency divider will be connected to the inputs of the Eprom memory and the memory will produce some outputs that will activate the decoder as well as the display. This memory will be programmed in the Eproms editor program called HxD. There from the tables that we have created according to the inputs we will begin to assign numbers that we will explain below. </div>
<br> 
# Showcase Video


