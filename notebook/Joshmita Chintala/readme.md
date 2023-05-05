
# Joshmita Chintala Worklog

## 02/08/23 - Initial Design
We made an initial design for our block diagram to encompass the vision we have for our project: 

![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/55951d80819499f842d3ed250a3bbcac00cd2585/notebook/blockdiagram.jpg)


Flow Chart of Design:

![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/main/notebook/image18.png)

Initial Visual Aid:

![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/main/notebook/image1.png)

We also talked to the Machine Shop about our plan and asked if they could build a chassis for us. We will look into online options for a chassis and a light component. If we cannot find one, they will build a chassis for us.

## 02/17/2023 - Chassis update and Design Document
We have found a [chassis online](https://www.sparkfun.com/products/retired/12089) that we can order, and we have decided to use that instead of getting one built at the machine shop. We are currently working on our design document. 

![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/4144c61d7745133481f74377903ace64063f47f4/notebook/chassisj.png)
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
10. Please label the tables properly and keep the units consistent (3.3 V instead of 3.3 v).
11. Are your battery or any other components at risk as they are very close to moisture/soil? Please mention that in your safety.

## 03/06/2023 - Design Document Revisions were made to Update High-Level Requirements
After the design review, we made the following changes to the high-level requirements of our project:
1. The robot must be able to carry a plant and pot of total size of [weight: 15-20 pounds, diameter 10-20 cm ]
2. When placed indoors on a window sill, in front of a window, or in a balcony, without objects obstructing its path, the plant must “follow the light” by moving horizontally or vertically (on an X/Y axis) and must find optimal sunlight within 1 hour.
3. Robot must detect when moisture is less in the plant and must alert the user (LED must blink)

## 03/07/2023 - Meeting with Raman, Light Sensor & Voltage Regulator were gathered from ECE storage cabinet

TA Meeting Minutes: 
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
  
**Light sensor and voltage regulator obtained from lab:**

Light Sensor [Part](https://learn.adafruit.com/adafruit-si1145-breakout-board-uv-ir-visible-sensor/downloads)

Light Sensor [Datasheet](http://www.adafruit.com/datasheets/Si1145-46-47.pdf)

![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/main/notebook/1.bmp)

Voltage Regulator (Not Used in final project): 

![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/main/notebook/2.bmp)

## 03/17/2023 - Chassis & Moisture Sensors were Bought through ECE Portal

![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/2b26844f494a01373a35ec71cc3da90e9449bb1d/notebook/orders.png)

Moisture Sensor [Part](https://www.sparkfun.com/products/13322?_ga=2.48722852.34707985.1680741906-1735945614.1675881698)

Moisture Sensor [Git Data Files](https://github.com/sparkfun/Soil_Moisture_Sensor)

Moisture Sensor [Schematic](https://cdn.sparkfun.com/datasheets/Sensors/Biometric/SparkFun_Soil_Moisture_Sensor.pdf)

![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/main/notebook/4.bmp)

Chassis [Part](https://www.sparkfun.com/products/12089)

Chassis [Datasheet](http://cdn.sparkfun.com/datasheets/Robotics/DG02S.pdf)

![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/d32a480c1084e9ff1613d14dcd60962196466e96/notebook/chassisjj.jpg)


## 03/18/2023 - Moisture Level Research Conducted

For our moisture sensor, the level of moisture is denoted from ~0 to ~880 units (i.e., 0, for completely dry and 880 for soil levels completely saturated)

Data for ferns (the plant we plan on purchasing): 
Moisture Levels recommended to have 40-50 percent relative humidity levels
- Moisture levels (which will be implemented in the code)
  - 354-440 should be the range for an average moisture level
- 30% is the lowest level a fern can tolerate: 264
- 70% is the highest level a fern can tolerate: 616
- How to know when fern is overwatered: Wilting & yellow leaves, soil becomes “waterlogged” and releases unpleasant odor, tip of leaves turning dark brown

Citations:

https://learn.sparkfun.com/tutorials/soil-moisture-sensor-hookup-guide/calibration- 

https://www.bbg.org/news/caring_for_ferns_as_houseplants#:~:text=Home%20moisture%20levels%20can%20be,percent%20levels%20recommended%20for%20ferns 

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

1. We are now using a LED instead of a speaker as the alert for the moisture sensor since a speaker could be distracting to the user. Instead, we will be implementing an LED that blinks, which will indicate to the user to water their plant.

2. The voltage regulator which used to be in the power subsystem will now be in the PCB.

3. We updated our block diagram to have more clear voltage readings. Each subsystem but the motion subsystem will provide 3.3V.

4. After researching plants, we have specified the type of plant that we will use: an indoor, medium light plant with light intensity between 75-150 Foot Candles (FC - unit to measure plant light intensity). The pot will have about a 15cm diameter, and this will fit the chassis which has length 16.5cm and width 15.7cm.



## 03/31/2023 - Design Doc Revisions were made to Update the Subsystem Requirements

We mainly changed the requirements and verifications for each subsystem: 

**Sensor subsystem old R/V:**

| **Requirements**     | **Verification** |
| --------------- | ------------ |
| The moisture sensor must be able to detect dryness within 2 days, and never send an alarm when not dry.          | Verify the moisture sensor is working properly by taking moisture level measurements consistently throughout a week, and fact-check those levels with online resources and verifications of the plant itself.      |
| The light sensor should find the location with the most light within 15 cm of error. |   Continuously record the light sensor data over a weekly period, and make sure measurements being recorded are consistent and accurate with that daily sunlight emissions.    |

**Sensor subsystem new R/V:**


| **Requirements**     | **Verification** |
| --------------- | ------------ |
| The moisture sensor must be able to detect dryness within 2 days, and never send an alarm when not dry.           | Once we put the moisture sensor in our plant we will test the sensor by testing different amounts of moisture- that is, by gradually watering the plant and noticing the moisture levels that are read by the sensor. (The values provided by the sensor range from approximately 0 to 880, where 0 is for when the sensor is dry and 880 is for when the sensor is completely saturated with moisture.) Verify the moisture sensor is working properly by taking moisture level measurements consistently throughout a week, and fact-check those levels with online resources and verifications of the plant itself. |
| The light sensor should find the location with the most light within 15 cm of error. |   Have a light source such as a lamp, and move the light sensor further away from it, and see if the illuminance (lx) detected by it decreases. (We will test it by recording light sensor data over a week and will compare the results to daily sunlight emissions to see if light is properly being detected by the sensor.) Continuously record the light sensor data over a weekly period, and make sure measurements being recorded are consistent and accurate with that daily sunlight emissions. |
| The light sensor’s data must be correct | Test the light sensor with the phone's flashlight with different intensity, and see if the light sensor’s data can indicate which intensity is most bright.  |


**Motion subsytem old R/V:**
| **Requirements**     | **Verification** |
| --------------- | ------------ |
| The chassis must be able to move at a constant speed (constant rate between 0.5 -1.2 mph) to ensure the plant does not fall from an accelerated force. As well, measurements can be recorded at a constant rate.         | Record the speed at which the chassis moves using IO Lab or some sort of measurement tool that defines velocity and acceleration.      |
| The wheels should have an ideal amount of torque based on the size of the plant, in order for the plant to not fall.  |   Calculate the torque using the equation: Torque = rFsin(theta), and solve for Force using IO Lab.    |
| The platform should be large and durable enough to hold a small/regular sized potted plant.  | Platform carrying plant can be pre-determined, so make sure the plant being bought fits the size of this platform (diameter of potted-plant base should cover maximum 95% and minimum 45% of the surface area.) |

**Motion subsytem new R/V:**
| **Requirements**     | **Verification** |
| --------------- | ------------ |
| The chassis must be able to move at a constant speed (constant rate between 0.5 -1.2 mph, as it moves in a straight line) to ensure the plant does not fall. As well, so measurements can be recorded at a constant rate.          | Record the speed at which the chassis moves using IO Lab or some sort of measurement tool that defines velocity and acceleration.      |
| The wheels should have an ideal amount of torque based on the size of the plant, in order for the plant to not fall.  |   Calculate the torque using the equation: Torque = rFsin(theta), and solve for Force using IO Lab.    |
| The platform should be large and durable enough to hold a small/regular sized potted plant.  | Platform carrying plant can be pre-determined, so make sure the plant being bought fits the size of this platform (diameter of potted-plant base should cover maximum 95% and minimum 45% of the surface area.) Since our chassis has the dimensions of 16.5x15.7 cm, our pot/plant should have a diameter of about 15 cm.  |

**Notification subsytem old R/V:**
| **Requirements**     | **Verification** |
| --------------- | ------------ |
| Must be able to make some noise (audible to the user) when receiving a signal of dryness.  | Connect the speaker to the processor and let the processor send the signal. See if the speaker makes some noise. |

**Notification subsytem new R/V:**
| **Requirements**     | **Verification** |
| --------------- | ------------ |
| Must be able to blink when receiving a signal of dryness.  | Connect the LED (a small, colored or white LED that we will take from previous labs used in classes) to the processor and let the processor send the signal. See if the LED blink. |


**Power subsytem old R/V:**
| **Requirements**     | **Verification** |
| --------------- | ------------ |
| The system must provide over-current, over-voltage, under-voltage, and short-circuit protection.   | Connect the voltage regulator to various circuits with varying conditions, see if the regulator can shut down in time. |
| It must provide a stable 3.3 ± 0.1 V power source.  | Check voltage using a multimeter, and ensure that the proper amount of power is being supplied. |

**Power subsytem new R/V:**
| **Requirements**     | **Verification** |
| --------------- | ------------ |
| The system must provide over-current, over-voltage, under-voltage, and short-circuit protection.   | Connect the voltage regulator to various circuits with varying conditions, see if the regulator can shut down in time. |
| It must provide a stable 3.3 ± 0.1 V power source.  | Check voltage using a multimeter, and ensure that the proper amount of power is being supplied. All of the provided voltages will be tested in the lab, without water in the potted plant, or else testing issues (spilling or leakage of water) may occur.  |


**Microcontroller old R/V:**
| **Requirements**     | **Verification** |
| --------------- | ------------ |
| Able to store 10 sets of data gathered for each hour during initial setup.   | Check the memory space after an experimental initial setup.|
| Able to send signal of current desired location to chassis.   | Give the chassis a set of data and check whether it arries desired location according to data. |
| Able to analyze data from the moisture sensor and send a signal to the LED when indicated by the data.  | Put the moisture sensor into a pile of dry paper and check if the speaker will beep. |

**Microcontroller new R/V:**
| **Requirements**     | **Verification** |
| --------------- | ------------ |
| Able to store 10 sets of data gathered for each hour during initial setup.   | Check the memory space after an experimental initial setup.|
| Able to send signal of current desired location to chassis.   | Give the chassis a set of data and check whether it arrives at desired location according to data. |
| Able to analyze data from the moisture sensor and send a signal to the LED when indicated by the data.  | Put the moisture sensor into a pile of dry paper and check if the LED will blink. |

PCB and Circuit Schematic:

![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/96a6dceda2dcd06b51d90285615bb82f3050fe45/notebook/pcb_one.png)

## 04/3/2023 → 04/5/2023 Another PCB & Circuit Schematic was created

![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/96a6dceda2dcd06b51d90285615bb82f3050fe45/notebook/pcb_two.png)

We re-implemented our microcontroller in this new schematic, and fully implemented our motor driver and motion subsystems compared our first design,

## 04/6/2023 → 4/7/2023 - New PCB & Circuit Schematic was created

![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/96a6dceda2dcd06b51d90285615bb82f3050fe45/notebook/pcb_three.png)

We implemented 2 motor drivers in this new and complete design.

## 04/16/2023 - Plant was Bought from Home Depot

Dimension of pot/plant to be used:
- If square: 15.5L x 14.5W (cm)
-  circle: Diameter 15 (cm)
- Weight: 15-20 (lbs) or 6.8-9.1 (kg)
- Height: Does not matter, as long is it is not obstructing light sensor
- Luminosity Req. by plant: (LUX or FC-foot candles)
  - Low light plants: 25-75 FC
  - Medium light plants: 75-150 FC
  - High light plants: 150+ FC
  
![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/77d974c6e01321b8c5f292fbad31dabb68ad207f/notebook/plant.jpg)

  
Bought:
- 04” Foliage/Fern
- Grown From: Hampshire Farms
- Care: Medium Light (75-150 FC), Keep Moist
- Room Temp: 65-85 Degrees
- Mild Liquid Fertilizer
- Weight: About 2-3 lbs

## 4/17/2023 - Light Meter was Bought for Light Detection Verification

Different alternatives to test & verify light intensity: https://greeneryunlimited.co/blogs/plant-care/how-to-measure-light-for-plants

- App that measures light intensity in foot candles (2$): Did not buy, because there are not as many functionalities. 
- Light Meter ($15): Bought because it is able to detect light intensity in different units most accurately. 
   - Used 9V battery to power it; can be measured in FC (Foot Candles) or in LUX (luminous intensity)

![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/77d974c6e01321b8c5f292fbad31dabb68ad207f/notebook/one.jpg)

## 4/18/2023 - New Cost Analysis was created

Our original PCB didn’t work, due to soldering and connection issues, so we are making a new design with both a DevBoard and a breadboard. The total cost of our project is about $176.07


| Description     | Supplier     | Quantity | Price  |
| --------------- | ------------ | -------- | ------ | 
| Chassis         | Sparkfun     | 1        | $40.00 | 
| Moisture Sensor | Sparkfun     | 1        | $6.50  |
| Voltage Reg     | ECEB Lab     | 1        | $0.00  |
| Light Sensor    | ECEB Lab     | 1        | $9.95  |
| Foliage Plant   | Home Depot   | 1        | $6.52  |
| Jumper Wires    | ECEB Shop    | 20       | $7.40  |
| Photocell       | ECEB Shop    | 1        | $1.50  |
| SPDT Switch     | ECEB Shop    | 1        | $1.50  |
| Light Meter     | Amazon       | 1        | $14.99 |
| 9V Battery      | Walgreens   | 1        | $23.99 |
| AA Batteries    | Walgreens   | 8        | $14.99 |
| RedBoard PCB    | Sparkfun     | 1        | $25.66 |
| Motor Driver    | Sparkfun     | 1        | $23.49 |

## 04/19/2023 - Chassis was Built
Dimensions of [chassis](https://www.sparkfun.com/products/12089)
- Moves @0.5-1.2 mph
- Completed Kit Size - 165L x 157W x 65H (mm)
- Wheel Diameter - 65 mm

![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/77d974c6e01321b8c5f292fbad31dabb68ad207f/notebook/two.jpg)

## 04/20/2023 - Conducted Light and Moisture Sensor Verifications

One of my individual responsibilities in the group is to come up with testing methodologies for the light and moisture sensor data, track the data, and analyze the light and moisture sensor data over time.
First, I tested the light sensor. 
- **Goal:** Show that photocell light measurement decreases as distance increases from the light source
- **How:** Using a voltage divider circuit that produces a voltage dependent on the photocell’s resistance, as shown below: 

![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/4e0acb5fdd868d1a5ba58e3f7ea34f5d46e41ca6/notebook/three.png)

![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/4e0acb5fdd868d1a5ba58e3f7ea34f5d46e41ca6/notebook/four.png)

Voltage divider circuit implemented for testing photocell:

![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/4e0acb5fdd868d1a5ba58e3f7ea34f5d46e41ca6/notebook/five.jpg)

This circuit uses a 4.7kΩ resistor to divide the voltage with the photocell. As the surroundings get darker, resistance increases, and voltage decreases.

The first test was conducted holding a flashlight at a distance and coming closer and closer to the photocell, therefore gradually increasing light on the photocell. 

As can be seen below, the resistance values are decreasing gradually from 17410.28 Ω to 131.14 Ω, and the voltage values are increasing from 1.05 V to 4.84 V. This shows how the sensor is detecting that light on it is increasing.

![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/4e0acb5fdd868d1a5ba58e3f7ea34f5d46e41ca6/notebook/six.png)

This can be displayed in graphical format to show the clear correlation of the data: 

![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/4e0acb5fdd868d1a5ba58e3f7ea34f5d46e41ca6/notebook/seven.png)

![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/4e0acb5fdd868d1a5ba58e3f7ea34f5d46e41ca6/notebook/eight.png)

The above graphs show how as the flashlight is getting closer to the photocell, the voltage increases and the resistance decreases, showing how it’s detecting light. 

The next test conducted was with no light shining on the sensor and no darkness either - just with regular lighting of the room. 

&nbsp; &nbsp; &nbsp;  The resistance values were from ~5000Ω to ~8000Ω.

![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/4e0acb5fdd868d1a5ba58e3f7ea34f5d46e41ca6/notebook/nine.png)

The third test was conducted with all lights turned off.

&nbsp; &nbsp; The resistance values increased by a lot (to values between ~10000Ω to ~30000Ω), and the voltage decreased compared to the first test’s results, showing that the sensor is functioning well, and that the sensor detected the change in lighting to a darker environment. 

![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/4e0acb5fdd868d1a5ba58e3f7ea34f5d46e41ca6/notebook/ten.png)

**Conducted Moisture Sensor Verification:**

Next, I tested the moisture sensor.   

- **Goal:** Show that the moisture sensor detects varying levels of moisture - take measurement when soil is dry, and then take measurement after just watering the plant, and then take measurement after an hour or so to see the moisture level decrease again.
- **How:** By testing just the moisture sensor by using the circuit below: 

![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/4e0acb5fdd868d1a5ba58e3f7ea34f5d46e41ca6/notebook/eleven.png)

*note: all soil moisture sensor measurements are in units of the sensor itself

Tested moisture sensor with nothing touching it: **SOIL MOISTURE LEVEL 0**

![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/4e0acb5fdd868d1a5ba58e3f7ea34f5d46e41ca6/notebook/twelve.jpg)
![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/4e0acb5fdd868d1a5ba58e3f7ea34f5d46e41ca6/notebook/thirteen.png)

As can be seen above, the moisture sensor detects nothing, and that is what is expected.      

Tested moisture sensor in a cup of water: **SOIL MOISTURE LEVEL 899**

![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/4e0acb5fdd868d1a5ba58e3f7ea34f5d46e41ca6/notebook/fourteen.jpg)
![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/4e0acb5fdd868d1a5ba58e3f7ea34f5d46e41ca6/notebook/fifteen.png)

When fully moist, the moisture sensor is detecting a level of 899, so the sensor is working, and this can also be used to check the relative moisture level of the soil, once tested.      

Tested moisture sensor in dry soil of the plant: **SOIL MOISTURE LEVEL ~760** 

![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/4e0acb5fdd868d1a5ba58e3f7ea34f5d46e41ca6/notebook/sixteen.jpg)
![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/4e0acb5fdd868d1a5ba58e3f7ea34f5d46e41ca6/notebook/seventeen.png)

We watered the plant after this and took readings the next day:

Tested moisture sensor after one day of watering: **SOIL MOISTURE LEVEL 848**

![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/4e0acb5fdd868d1a5ba58e3f7ea34f5d46e41ca6/notebook/eighteen.png)

Tested moisture sensor after 5 minutes of watering: 8:48pm - 8:53pm: **SOIL MOISTURE LEVEL 893**

![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/4e0acb5fdd868d1a5ba58e3f7ea34f5d46e41ca6/notebook/nineteen.png)

After 20 minutes: Taken at 9:09pm: **SOIL MOISTURE LEVEL 888**

![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/4e0acb5fdd868d1a5ba58e3f7ea34f5d46e41ca6/notebook/twenty.png)

It can be seen how the soil moisture sensor is working since the moisture level is decreasing over time since the point the plant had been watered.
   
## 04/21/2023 - Meeting with Raman

TA Meeting Minutes: 
- Make sure to show all high-level requirements working during demo w/proof
  - Moisture sensor/Notification system: show that the LED can blink, even if moisture data collection is unable to be made
- Small box, 10by10, vehicle in one corner, robot is able to reach part with more light
  - MAKE a video demo and include in presentation
  - Mention there is lighting issue, here, so that’s why we did a video demo 
- Robot should be able to carry a plant
  - Just show that it moves the plant
  - Make sure plant doesn’t fall
  - Increase size of pot maybe to ensure it’s fixes on the chassis and doesn’t fall
- Don’t focus on entire room, focus just on a small area - like a box - since you didn’t mention size requirements
  - Can reach the light area within one hour (idea: sped up video/timelapse)
- For every requirement and verification
  - Have some kind of proof - video or photo proof
  - Tested out voltage for example, shows 5 V, if in case that day things don’t work
- Team knowledge
  - Everyone be familiar with everything about the project
  - Everyone present equally
- Prepare with questions & rebuttals

## 04/22/2023 - Connection between breadboard & PCB was made

We came up with the following new circuit diagram for our dev board and breadboard:

![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/main/notebook/image8.png)

The motor driver is implemented in the top left, and they are connected to the motors. The light sensor is the photocell in the diagram, which gives analog input to the arduino. To its right is our implementation of the notification subsystem LED, which will blink when the moisture sensor shown is below a particular threshold, in our case, 600. The switch shown will turn the robot on.

As shown below, we implemented our circuit diagram onto the dev board and the bread board and made the connection between them for the transfer of data and I/O.

Connection between Arduino & Breadboard:
![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/4e0acb5fdd868d1a5ba58e3f7ea34f5d46e41ca6/notebook/twentyone.jpg)

Close up of Arduino attachments:
![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/main/notebook/image15.jpg)

Close up of Breadboard attachments: 
![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/main/notebook/image34.jpg)

## 04/22/2023 - Breadboard & PCB were attached to Chassis

- Green Light indicates Power is on (on Arduino)
- Flashing blue light is used for troubleshooting purposes (on Arduino)

![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/main/notebook/11.png)

Very initial functionality of the robot:
The robot moves towards the brightest light by first checking left, right, and center. The robot is equipped with a photocell that measures the intensity of light in its surroundings. The code records the light value to the left, center, and right by turning the robot in each direction and then records the maximum value to determine the direction of the light source. Based on this information, the robot moves towards the light source by adjusting the motor speeds.

The code initializes the pins and constants at the beginning of the program in the setup() function. The loop() function is called continuously, where the switch state is checked. If the switch is on, the robot searches for the brightest light source by following a specific sequence of turns and movements. The rightMotor() and leftMotor() functions are used to control the speed and direction of each motor. The robot stops if the switch is off.

1st Test Run after programming Arduino: 
https://drive.google.com/file/d/1KsUBnA2oxzMBs3iuzBaZZFfjHGKUlKDg/view?usp=sharing

Our main goals after the 1st initial coding:

1. Get the robot to stop moving once it’s found optimal light
2. Implement moisture sensor/LED system (that is, if moisture below certain moisture level, blink LED)
3. Make the robot move more smoothly (shouldn’t jerk so much)
4. Trying to use all 4 wheels (not fully necessary since basic functionality is working with 2 wheels- but would be nice if we could implement)
5. Trying to get the robot to move in straight line motions only (could be tough)
6. Implementing UV/IR light sensor instead of photocell (reach goal/not really necessary)

## 04/23/2023 - Fixed Issues; Robot moves in a straight path now 

1. Made sure the chassis stops when optimal light is detected and the desired position is achieved. 
2. Back two motors move at the same time at the same speed (constant rate between 0.5 -1.2 mph)

Test run after programming new code:
https://drive.google.com/file/d/1SgUafawGtIVndmSit95KRBC469cD4H0G/view?usp=sharing 

Improvements: 
1. Robot moves in a straight path and moves smoothly
2. Robot finds light and stops moving 

## 04/24/2023 - Continued to resolve errors and issues; Notification subsystem is now fully implemented

Final circuitry after completion:

![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/4e0acb5fdd868d1a5ba58e3f7ea34f5d46e41ca6/notebook/26.jpg)

Final code implementation:

![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/2f6fc1a4ccf003c2c5b61dc0878a6d246f4c42a0/notebook/codeone.png)
![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/2f6fc1a4ccf003c2c5b61dc0878a6d246f4c42a0/notebook/codetwo.png)

![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/2f6fc1a4ccf003c2c5b61dc0878a6d246f4c42a0/notebook/codethree.png)
![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/2f6fc1a4ccf003c2c5b61dc0878a6d246f4c42a0/notebook/countfour.png)

![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/2f6fc1a4ccf003c2c5b61dc0878a6d246f4c42a0/notebook/codefive.png)
![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/2f6fc1a4ccf003c2c5b61dc0878a6d246f4c42a0/notebook/codesix.png)

![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/2f6fc1a4ccf003c2c5b61dc0878a6d246f4c42a0/notebook/codeseven.png)


## 04/25/2023 - Refined & made final updated product before demo; Tested motion and notification subsystems

As can be seen in the photo below, we got a platform added to our robot today, so that we can put the plant on it. 

![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/4e0acb5fdd868d1a5ba58e3f7ea34f5d46e41ca6/notebook/27.jpg)

We also got an axle added to the two front wheels to help ease the friction of the robot, and let it move more smoothly. 

Test runs after programming new and improved code:
[Test1](https://drive.google.com/file/d/1ll1fXHr4sRN81HbiVXr6RRDm_tSz6ifv/view?usp=share_link)
[Test2](https://drive.google.com/file/d/1Q-D20-2DiU9arXtrRh4zE6f_ZVPylme1/view?usp=share_link)
[Test3](https://drive.google.com/file/d/17TonJKVUUsrl7szgIKjqdDtgaA7itb_l/view?usp=sharing) 

Improvements: 
- Robot now blinks LED if moisture is below a certain level.
  - When moisture sensor was put in the water, the LED did not blink
  - When moisture sensor was put in paper, the LED blinked as the moisture level is low

So, the notification subsystem is working. 


Tested the motion subsystem:
- **Goal:** The chassis should be able to move so that the plant does not fall off of it, and the platform should be large and durable enough to hold an indoor, medium-light plant.
- **How:** Show that the robot can carry an object between 2-8 pounds. 

We tested the robot with our plant, which is about 2 pounds, and it was able to carry it. We then tested our robot with a phone which is about 8 pounds, and the robot was able to carry it as well. 
Test run showing that 8 pounds phone can be carried: 
https://drive.google.com/file/d/1RWG3hcP99LffHtEo-0AsZFF_D7hqmoEo/view?usp=sharing

## 04/26/2023 - Final Demo; Feedback received
Final Product: 

![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/main/notebook/12.png)

