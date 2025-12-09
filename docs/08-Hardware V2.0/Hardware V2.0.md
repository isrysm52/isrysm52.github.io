---
title: Hardware V2.0
tags:
- tag1
- tag2
---

## Overview

This is a section of what I did wrong and the futrue improvements I would implement to my Motor Subsystem. There are 3 main places I would like to focus on. 1: the software and future changes/designs, 2: the PCB and footnotes, and 3: the components and motor power. I will be referencing both the PCB and the schematic in these changes and have included the pictures from previous pages right below. 

**Figure 1:** Here is the motor schematic.

![schematic](Motor_Subsystem_PNG.png)

**Figure 2:** Here is the motor PCB.

![schematic](PCB_Front.png)

### 1: Software and Future Changes/Designs

In the schematic there is a potentiometer installed into the microcontroller. Due to time constraints and the need to stop adding extra features, the potentiometer was not used becuse the testing and programming was not completed. The reason behind the potentiometer was for the user to have the ability to change the speed of the motor. This was in part a safety program because the motor and sensors would have more time to interact in case of an obstruction as well as a customer preference. The addition of using this potentiometer would mean that the software would need to use PWM, or pulse width modulation, in the program. There are comments in the code with the beginning of this, but it was never fine tuned to work with the potentiometer. 

Another addition would be an additional code for specific errors. In the code, if the motor subsystem was not reading a collection of correct digital inputs, the door would shine both red and greed LEDs and stop moving. Though this solves the main issue of having the door try to close on obstructions, it does not help the user in identifying what the obstruction may be. In the future, I would program the red and green LEDs to have a series of light patterns that the user would then be able to interpret instead of one single error. This could include a red pulse, red pulse, green pulse, then repeat for if the flex sensor is flexing too hard meaning there is a strain in the door hinges. Similarly, another example could be a pulsing red light for if the front or back sensor is detecting an object in the way of it opening, meaning something will be hit if the motor continues to move. BOth of these could be fine tuned for different senarios and light patterns which would also use the PWM system that the potentiomer would use. 

### 2: PCB and Footnotes

There is a slight difference between the schematic in figure 1 and the PCB in figure 2. The PCB footnote for the PCB Microcontroller has 1 additonal row. This threw off the whole system and caused my program, though correct, an additonal task to reprogram which pins held the H-bridge code. This was okay, but on bigger PCBs not a mistake to be taken lightly. Going forward, there will be an additional caution when creating and saving PCB footprints. This will also include a simple check on the corner pins, where I will put one push buttom or LED to help make sure my footnote has that pin in the right corner. 

I would also add more writing in my PCB footnotes. I would keep this on the outside so that it would not affect the holes and wiring, but I found that the more writing and direction I gave myself in the PCB footnotes, the easier it was to attatch femail headers and know which component would go with which box. I think that this will hold a huge future advantage when I need to use multiple microcontrollers on one PCB and I would be able to have the habit of labeliong which one will go where so that there is no confusion even if I am not the one putting the PCB and compnents together. 

### 3: Components and Motor Power

The motor was a motor that fit the budget of this class. If I was finalizing this project into a working and sellable project, I would first increase the motor power and torque. This motor could open a door, but would heavily struggle and be close to overheating. If we got a higher grade, power, and torque motor that would help imensly in the heat and speed of the door opening. 

Additionally, I would add more LED lights and a speaker to the subsystem. This would be helpful to let others know that the motor is on and moving the door so others could get out of the way. The extra lights is an addition to a previous comment about code and signals. Using a few more lights could help communicate to the user is there is a problem. A great example would be a yellow light for if the motor is not getting enough power and that is the reason it is wither moving slower than anticipated or not moving at all. 

## Conclusion

Thank you for sticking with this subsystem and the main project while it is getting developed. There are many future ideas and projects within this subsystem to improve the useability and ease of access for the user. There are many parts of the programming that, while not neccessary, could improve the quality of this subsystem. There are many components that could be improved and other components that could be added for a similar reason. And the most important is the lesson on not only double checking, but triple checking work and programs to ensure that there are as little problems as possible after production and PCB creation. Overall, this has been a great imrovement in my skills and the imrovement of this hardware will continue to be developed as well in the future 2.0 Hardware.