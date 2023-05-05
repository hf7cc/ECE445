
# Maya Kurup Worklog

## 02/08/23 - Initial Design
We made an initial design for our block diagram to encompass the vision we have for our project: 
![Initial Block Diagram]

We also talked to the Machine Shop about our plan and asked if they could build a chassis for us. We will look into online options for a chassis and a light component. If we cannot find one, they will build a chassis for us.

## 02/17/2023 - Chassis update and Design Document
We have found a chassis online that we can order, and we have decided to use that instead of getting one built at the machine shop. We are currently working on our design document. 

## 02/28/2023 - Design Review Occured & Feedback was Given
From Raman: 
1. Based on Prof. Mironenko's suggestions, please consider making a few modifications in your high-level requirements. 
_For e.g., fixing on a plant, reduce the content of your points etc. 
_In point 1, you can just mention that you are planning to track the room and find the points with max and min luminosity/heat within the limits of your sensor. 
_Modify point 2 demonstrate it a testable criterion, like, the chassis should be able to move to the location (X & Y coordinate) with most light in the room (for a certain time of the day) with at most 1.2 mph (have some accuracy component attached to it). Please modify this example point as per the scope of your project.
_Modify point 3 to have an LED alarm instead of a speaker alarm, if you intend to change your notification subsystem.
2. Your block diagram needs modifications. Please refer to my design review feedback mail.
3. Please provide more details in your subsystem overview like details regarding the type of battery, microcontroller etc.
4. Please finalize the type of plant, it will help you define components like dryness, pot size etc. as those requirements are still vague.
5. Changing directions would induce acceleration, the constant speed is only good if you are moving in a straight line.
6. How do you plan to verify that the light sensor data is correct? Please put that in the verification section.
7. Please make necessary changes if you plan to change the notification subsystem from speaker to LED.
8. Please do not provide manufacturer guaranteed characteristics as your subsystem requirements. When you check the voltage with the multimeter, is it with the pot or without? The weight of the plant will be different before and after watering it.
9. It looks like you guys are doing experimental testing for your tolerance analysis. Could you provide some mathematical or simulations for the testing you are planning to do?
Please label the tables properly and keep the units consistent (3.3 V instead of 3.3 v).
Are your battery or any other components at risk as they are very close to moisture/soil? Please mention that in your safety.

## 03/06/2023 - Design Document Revisions were made to Update High-Level Requirements
In order to successfully obtain a fully working product by the end of this course, we plan to reach the following goals. 
1. The robot must be able to carry a plant and pot of total size of [weight: 15-20 pounds, diameter 10-20 cm ]
2. When placed indoors on a window sill, in front of a window, or in a balcony, without objects obstructing its path, the plant must “follow the light” by moving horizontally or vertically (on an X/Y axis) and must find optimal sunlight within 1 hour.
3. Robot must detect when moisture is less in the plant and must alert the user (LED must blink)

##03/07/2023 - Meeting with Raman, Light Sensor & Voltage Regulator were gathered from ECE storage cabinet

TA Meeting Meeting Minutes: 
- Do high-level requirements look good? - YES
- How exactly do we connect the wheels (chassis) to the plant
_Do we need a breadboard/circuit that we make connecting the wires on the chassis to the breadboard?
_Do we directly connect to the PCB which then connects to the light sensor/
- How to order parts: Help Maya w the specific tab portion on myECE
_Will our moisture & light sensor found work on our PCB?
_Chassis: The one we found connects with wires, should we find one that connects to PCB directly/in a dif way?
- How do we design PCB board?
_Which components are necessary?
_What components are we missing?
_Do we need to create an example schematic using a specific software?
_Do we order the PCB or are the already ordered and we pick it up & add our components?
_We create a design of our PCB through Gerber files, then upload it to MyPCB, and it will be approved then the physical model will be printed and given to us within 2-3 weeks after the AUDIT deadline
- Ordering battery?
_Get battery over motor specification
_5V battery and using a voltage regulator→ adjust voltage regulator
- Consider watering plant as part of weight
- For connecting chassis wires to PCB
- Attach wire to 2-pin connector
- Parts: Octo part
_https://octopart.com/ 
_https://www.ultralibrarian.com/ 
