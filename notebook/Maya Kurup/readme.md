
# Maya Kurup Worklog

## 02/08/23 - Initial Design
We made an initial design for our block diagram to encompass the vision we have for our project: 
![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/main/notebook/0.bmp)

We also talked to the Machine Shop about our plan and asked if they could build a chassis for us. We will look into online options for a chassis and a light component. If we cannot find one, they will build a chassis for us.

## 02/17/2023 - Chassis update and Design Document
We have found a chassis online that we can order, and we have decided to use that instead of getting one built at the machine shop. We are currently working on our design document. 

## 02/28/2023 - Design Review Occured & Feedback was Given
From Raman: 
1. Based on Prof. Mironenko's suggestions, please consider making a few modifications in your high-level requirements. 
   - For e.g., fixing on a plant, reduce the content of your points etc. 
   - In point 1, you can just mention that you are planning to track the room and find the points with max and min luminosity/heat within the limits of your sensor. 
   - Modify point 2 demonstrate it a testable criterion, like, the chassis should be able to move to the location (X & Y coordinate) with most light in the room (for a certain time of the day) with at most 1.2 mph (have some accuracy component attached to it). Please modify this example point as per the scope of your project.
   - Modify point 3 to have an LED alarm instead of a speaker alarm, if you intend to change your notification subsystem.
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

## 03/07/2023 - Meeting with Raman, Light Sensor & Voltage Regulator were gathered from ECE storage cabinet

TA Meeting Meeting Minutes: 
- Do high-level requirements look good? - YES
- How exactly do we connect the wheels (chassis) to the plant
  - Do we need a breadboard/circuit that we make connecting the wires on the chassis to the breadboard?
  - Do we directly connect to the PCB which then connects to the light sensor/
- How to order parts: Help Maya w the specific tab portion on myECE
  - Will our moisture & light sensor found work on our PCB?
  - Chassis: The one we found connects with wires, should we find one that connects to PCB directly/in a dif way?
- How do we design PCB board?
  - Which components are necessary?
  - What components are we missing?
  - Do we need to create an example schematic using a specific software?
  - Do we order the PCB or are the already ordered and we pick it up & add our components?
  - We create a design of our PCB through Gerber files, then upload it to MyPCB, and it will be approved then the physical model will be printed and given to us within 2-3 weeks after the AUDIT deadline
- Ordering battery?
  - Get battery over motor specification
  - 5V battery and using a voltage regulator→ adjust voltage regulator
- Consider watering plant as part of weight
- For connecting chassis wires to PCB
- Attach wire to 2-pin connector
- Parts: Octo part
  - https://octopart.com/ 
  - https://www.ultralibrarian.com/ 
  
  
Light Sensor [Part](https://learn.adafruit.com/adafruit-si1145-breakout-board-uv-ir-visible-sensor/downloads)

Light Sensor [Datasheet](http://www.adafruit.com/datasheets/Si1145-46-47.pdf)
![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/main/notebook/1.bmp)

*Could not find datasheet or any about VoltageRegulator, so was unused.
![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/main/notebook/2.bmp)

## 03/17/2023 - Chassis & Moisture Sensors were Bought through ECE Portal

Moisture Sensor [Part](https://www.sparkfun.com/products/13322?_ga=2.48722852.34707985.1680741906-1735945614.1675881698)

Moisture Sensor [Git Data Files](https://github.com/sparkfun/Soil_Moisture_Sensor)

Moisture Sensor [Schematic](https://cdn.sparkfun.com/datasheets/Sensors/Biometric/SparkFun_Soil_Moisture_Sensor.pdf)

![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/main/notebook/4.bmp)

Chassis [Part](https://www.sparkfun.com/products/12089)

Chassis [Datasheet](http://cdn.sparkfun.com/datasheets/Robotics/DG02S.pdf)

![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/main/notebook/5.bmp)

## 03/18/2023 - Moisture Level Research Conducted

For our moisture sensor, the level of moisture is denoted from ~0 to ~880 units (i.e., 0, for completely dry and 880 for soil levels completely saturated)

Data for ferns (the plant we plan on purchasing): 
Moisture Levels recommended to have 40-50 percent relative humidity levels
- Moisture levels (which will be implemented in the code)
  - 354-440 should be the range for an average moisture level
- 30% is the lowest level a fern can tolerate: 264
- 70% is the highest level a fern can tolerate: 616
- How to know when fern is overwatered: Wilting & yellow leaves, soil becomes “waterlogged” and releases unpleasant odor, tip of leaves turning dark brown

## 03/22/2023 - PCB Schematic was submitted during 2nd Round of PCBway Orders

![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/main/notebook/7.png)

## 03/28/2023 - Meeting with Raman
TA Meeting Minutes: 
- PCB will arrive around April 10 or quicker
- Parts
  - Approved during spring break
  - Frequently check ECEB for parts
- Design Doc: 11 points from email
- Sign up for PCB demo to learn how to do it
- Individual progress reports: due 3/29
- Lab Notebook
  - Physical lab notebook or git-file: IPR
  - Git lab notebook - txt files
- Not working with Machine Shop
- Finalize plant, and restrictions of size based on Chassis

## 03/29/2023 - Individual Progress Report was Created

Updated Design Considerations: 
- We changed the moisture sensor’s alert system from an audible noise provided by a speaker to a blinking LED. This is because the speaker notification system would get annoying to the user, especially if it goes off during unwanted times (sleep, important meetings/calls, etc). 
- The voltage of each subsystem (except the moving robot - chassis) have been confirmed to provide 5V. This has been updated in our block diagram (Figure 2). 
- Voltage regulator has now been updated to be part of the PCB.
- Type of plant has been determined to be an indoor, medium light plant with a light intensity between 75-150 FC (Foot Candles - unit of measurement for light intensity on plants). Dimensions of the pot have been determined to have a diameter of about 15 cm, in order to fit in the chassis with a length of 16.5 cm and width of 15.7 cm. 


## 03/31/2023 - Design Doc Revisions were made to Update the Subsystem Requirements

Final Subsystem Requirements & Verifications: 
### Sensor Subsystem
**Light Sensor Requirement:** The light sensor should collect light data correctly. To do this, show that the photocell light measurements decrease as distance from the light source increases. 
**Light Sensor Verification:** Test the light sensor with the phone's flashlight with different intensity, and see if the light sensor’s data can indicate which intensity is most bright. 

**Moisture Sensor Requirement:** The moisture sensor must be able to detect dryness within 2 days, and send an alarm when soil is dry (below a threshold). 
**Moisture Sensor Verification:** Test different levels of moisture by gradually watering the plant and notice the change in moisture levels read by the sensor. The values provided by the sensor range from approximately 0 to 880 (0 = dry; 880 = wet)

### Motion Subsystem
**Verfication:** The chassis should be able to move so that the plant does not fall off of it, and the platform should be large and durable enough to hold an indoor, medium-light plant.
**Requirement:** Platform & chassis system should be able to carry objects ranging in 2-6 pounds. As well, an object with a diameter between 10-15 cm. 

### Notification Subsystem
**Verfication:** Must be able indicate dryness to the user using a notification system (blinking LED).
**Requirement:** Set a minimum threshold of the moisture sensor in the program, and let the processor send a signal to an LED to blink. See if the LED blinks when below threshold.

### Power Subsystem
**Verfication:** The power system should provide a voltage, and be regulated throughout the entire system.
**Requirement:** Use the “ON” LED on the Dev board, making sure it lights up green, indicating power is on.

### Microcontroller
**Verfication1:** Able to send a signal of the desired location to the chassis, based on the light sensor.
**Requirement1:** Give the chassis a set of data and check whether it arrives at the desired location according to the data.

**Verfication2:** Able to analyze data from the moisture sensor, and send a signal to the LED when indicated by the data. 
**Requirement2:** Put the moisture sensor into a dry source (dry soil, paper, air), and check if the LED will blink.

## 04/3/2023 → 4/7/2023 - New PCB & Circuit Schematic was created

![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/main/notebook/8.png)









