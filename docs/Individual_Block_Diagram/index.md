---
title: Individual Block Diagram
---

## Block Diagram

### Overview
Below is the individual block diagram for my component of my team's project. My component is the HMI (Human Machine Interface). The block diagram includes 3 pushbuttons to allow for user input for quick actions, various LEDs to allow for debugging and to let the user know when a function is happening, a potentionmeter to allow a user to select through a range of values, and an OLED screen to display sensor values and allow the user to see what each button does while also providing short instructions on what the user can do next. The microcontroller choose is the PIC18F47Q10 programmed by the Microchip SNAP programmer. All of this is powered by a 3.3V switching power regulator and connects via UART to the rest of my team's PCBs. Each component is shown on the block diagram below along with their connections and type of connection with the number for pins that the component will use.

### Block Diagram

![Individual Block Diagram](EGR314-Team204-IndividualBlockDiagram-Jake.drawio.png)


### Decision Making Process

For the HMI subsystem I decided to use the PIC18F47Q10 microcontroller because I found it was easier to program and easier to select the type of inputs and pins that I would need to use. For the user input I choose 3 buttons and a potentiometer. I thought to use these specific inputs so that I could develop a menu system on the OLED screen where the user could use the potentiometer to scroll through the menu and use the different buttons to select the options in the menu. The buttons connection types are all digital inputs and the potentiometer is an ADC beccause it is an analog device, and the OLED screen communicates via I2C with a connection for both the clock and data lines into the PIC. I also have two LEDs that are used for debugging and to show when an action is that would not be visable otherwise, both are controlled via digital outputs. The upstream and downstream headers were added so that I can communicate with my teammates board's via UART as stated within the project requirements, with my Tx connected to downstream and my Rx connected from the upstream header. There is also the connection with the snap programmer connected via ICSP with three connections with bidirectional serial communication. Everything within the dotted box is powered by 3.3V volts which is given by the microchip LM2575 swithching voltage regulator.
