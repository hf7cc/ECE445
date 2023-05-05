
# Maya Kurup Worklog

## 02/08/23 - Initial Design (Team)
We made an initial design through a visual aid for what our project should base off: 

![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/main/notebook/image1.png)

We made an initial design for our block diagram to encompass the vision we have for our project: 
![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/main/notebook/blockdiagram.jpg)

We also talked to the Machine Shop about our plan and asked if they could build a chassis for us. We will look into online options for a chassis and a light component. If we cannot find one, they will build a chassis for us.

## 02/17/2023 - Chassis update and Design Document (Team)
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
Please label the tables properly and keep the units consistent (3.3 V instead of 3.3 v).
Are your battery or any other components at risk as they are very close to moisture/soil? Please mention that in your safety.

## 03/06/2023 - Design Document Revisions were made to Update High-Level Requirements (Team)
In order to successfully obtain a fully working product by the end of this course, we plan to reach the following goals. 
1. The robot must be able to carry a plant and pot of total size of [weight: 15-20 pounds, diameter 10-20 cm ]
2. When placed indoors on a window sill, in front of a window, or in a balcony, without objects obstructing its path, the plant must “follow the light” by moving horizontally or vertically (on an X/Y axis) and must find optimal sunlight within 1 hour.
3. Robot must detect when moisture is less in the plant and must alert the user (LED must blink)

## 03/07/2023 - Meeting with Raman, Light Sensor & Voltage Regulator were gathered from ECE storage cabinet (Team)

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
  
Parts: 
- Light Sensor [Part](https://learn.adafruit.com/adafruit-si1145-breakout-board-uv-ir-visible-sensor/downloads)
- Light Sensor [Datasheet](http://www.adafruit.com/datasheets/Si1145-46-47.pdf)

![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/main/notebook/1.bmp)
- Could not find datasheet or any about Voltage Regulator,so was unused

![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/main/notebook/2.bmp)

## 03/17/2023 - Chassis & Moisture Sensors were Bought through ECE Portal (Maya & Joshmita)
Parts: 
- Moisture Sensor [Part](https://www.sparkfun.com/products/13322?_ga=2.48722852.34707985.1680741906-1735945614.1675881698)
- Moisture Sensor [Git Data Files](https://github.com/sparkfun/Soil_Moisture_Sensor)
- Moisture Sensor [Schematic](https://cdn.sparkfun.com/datasheets/Sensors/Biometric/SparkFun_Soil_Moisture_Sensor.pdf)

![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/main/notebook/4.bmp)

Chassis [Part](https://www.sparkfun.com/products/12089)

Chassis [Datasheet](http://cdn.sparkfun.com/datasheets/Robotics/DG02S.pdf)

## 03/18/2023 - Moisture Level Research Conducted (Maya & Joshmita)

For our moisture sensor, the level of moisture is denoted from ~0 to ~880 units (i.e., 0, for completely dry and 880 for soil levels completely saturated)

Data for ferns (the plant we plan on purchasing): 
Moisture Levels recommended to have 40-50 percent relative humidity levels
- Moisture levels (which will be implemented in the code)
  - 354-440 should be the range for an average moisture level
- 30% is the lowest level a fern can tolerate: 264
- 70% is the highest level a fern can tolerate: 616
- How to know when fern is overwatered: Wilting & yellow leaves, soil becomes “waterlogged” and releases unpleasant odor, tip of leaves turning dark brown

## 03/22/2023 - PCB Schematic was submitted during 2nd Round of PCBway Orders (Hongshang & Team)

In our original PCB schematic we incorporated all of our necessary components like the microcontroller, the light and moisture sensors, the voltage regulator, and LED notification system. The main component we did not have originally was the motor driver. As well, we did not have a proper integration of the microcontroller. 

Design Schematic of PCB: 

![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/main/notebook/image41.png)

Image from PCB Ways:

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

## 03/29/2023 - Individual Progress Report was Created (Team)

Updated Design Considerations: 
- We changed the moisture sensor’s alert system from an audible noise provided by a speaker to a blinking LED. This is because the speaker notification system would get annoying to the user, especially if it goes off during unwanted times (sleep, important meetings/calls, etc). 
- The voltage of each subsystem (except the moving robot - chassis) have been confirmed to provide 5V. This has been updated in our block diagram (Figure 2). 
- Voltage regulator has now been updated to be part of the PCB.
- Type of plant has been determined to be an indoor, medium light plant with a light intensity between 75-150 FC (Foot Candles - unit of measurement for light intensity on plants). Dimensions of the pot have been determined to have a diameter of about 15 cm, in order to fit in the chassis with a length of 16.5 cm and width of 15.7 cm. 


## 03/31/2023 - Design Doc Revisions were made to Update the Subsystem Requirements (Team)

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



## 04/3/2023 → 04/5/2023 Second PCB & Circuit Schematic was created (Team)

In our second PCB schematic we incorporated the same components as before, however we re-implemented our microcontroller, as our first one was not resulting in a proper function. As well, we did not fully implement our motor driver/motion subsystem. 

![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/main/notebook/image35.png)

## 04/6/2023 → 4/7/2023 - New PCB & Circuit Schematic was created (Team)

In our third and last PCB schematic, we had all components needed for the final product design, however we implemented 2 motor drivers, and ended up using 1. All in all, the functionality of our final design would have been able to work, if it wasn’t for issues when soldering and making those specific connections. 

![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/main/notebook/image16.png)

## 4/15/2023 - Plant Research was Conducted (Maya)

Tips & Advice: 
1. [10 best indoor plants for your health - Boosting Oxygen levels & purifying the air](https://www.goodhousekeeping.com/home/gardening/g40742429/best-indoor-plants-for-health/)
   - Spider Plant, Peace Lily, Rubber Plants (Ficus Elastica), Elephant Ear Planrs, Snake Plants, Ferns, Pothos, English Ivy, Succulents and Cacti, Herbs
2. [30 Indoor plants that like direct sunlight](https://www.thespruce.com/best-houseplants-for-sun-4147670)
3. [23 of the best medium-light houseplants](https://gardenerspath.com/plants/houseplants/medium-light/)
   - Boston ferns (Nephrolepis exaltata), aka sword ferns – not to be confused with Western sword ferns (Polystichum munitum) – have been a mainstay in homes for years. They’re tolerant of shade, but put them in moderate light and watch them explode with green goodness. 
4. [30 Indoor plants for low light](https://www.hgtv.com/outdoors/flowers-and-plants/houseplants/14-indoor-plants-for-low-light-pictures)
   - Maidenhair Fern: Many ferns, including button, Autumn, rabbit's foot, maidenhair and more, are good options for low-light situations. Give them consistently moist soil and low to medium light.

## 04/16/2023 - Plant was Bought from Home Depot (Maya)

Dimension of pot/plant to be used:
- If square: 15.5L x 14.5W (cm)
-  circle: Diameter 15 (cm)
- Weight: 15-20 (lbs) or 6.8-9.1 (kg)
- Height: Does not matter, as long is it is not obstructing light sensor
- Luminosity Req. by plant: (LUX or FC-foot candles)
  - Low light plants: 25-75 FC
  - Medium light plants: 75-150 FC
  - High light plants: 150+ FC
  
Bought:
- 04” Foliage/Fern
- Grown From: Hampshire Farms
- Care: Medium Light (75-150 FC), Keep Moist
- Room Temp: 65-85 Degrees
- Mild Liquid Fertilizer
- Weight: About 2-3 lbs

Fern that was bought: 
![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/main/notebook/image17.jpg)

## 04/17/2023 - Light Meter was Bought for Light Detection Verification (Maya)
- Dif alternatives to test & verify light [intensity](https://greeneryunlimited.co/blogs/plant-care/how-to-measure-light-for-plants)
  - App that measures light intensity in foot candles(2$): Did not buy, because there are not as many functionalities. 
  - Light Meter($15): Bought because it is able to detect light intensity in different units most accurately. 
    - Used 9V battery to power it; can be measured in FC (Foot Candles) or in LUX (luminous intensity)

## 4/18/2023 - New Cost Analysis was created (Maya)

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
| 9V Battery      | Wallgreens   | 1        | $23.99 |
| AA Batteries    | Wallgreens   | 8        | $14.99 |
| RedBoard PCB    | Sparkfun     | 1        | $25.66 |
| Motor Driver    | Sparkfun     | 1        | $23.49 |

## 04/19/2023 - Chassis was Built (Maya)
Dimensions of [chassis](https://www.sparkfun.com/products/12089)
- Moves @0.5-1.2 mph
- Completed Kit Size - 165L x 157W x 65H (mm)
- Wheel Diameter - 65 mm


![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/main/notebook/image12.jpg)

Bottom of Chassis (Power Subsystem)
![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/main/notebook/image20.jpg)

## 04/20/2023 - Light Sensor Verification using Light Meter (Maya)

*Note that Sun sets East to West: Right→Left of Window/Room from morning→night)

First day of Testing Light with Light Meter (in both FC & LUX)
- 6:53pm on Saturday, April 22, an hour before sunset
- UV Index: 0, and fairly low bc cloudy

| Testing Location | Dist. from right of room | Light Intensity(LUX)| Light Intensity(FC)|
| ---------------- | ------------------------ | ------------------- | ------------------ | 
| Right of Room    | 0.59 meters              | 238                 | 26.1               |  
| 2nd Most Right   | 1.65 meters              | 240                 | 26.1               |
| 3rd Most Right   | 2.74 meters              | 261                 | 26.1               |
| Left  of Room    | 3.66 meters              | 286                 | 26.2               |

Second day of Testing Light with Light Meter (in both FC & LUX)
- 11:49AM on Sunday, April 23
- UV Index: 4, so some sunlight, but still a bit cloudy

| Testing Location | Dist. from right of room | Light Intensity(LUX)| Light Intensity(FC)|
| ---------------- | ------------------------ | ------------------- | ------------------ | 
| Right of Room    | 0.59 meters              | 2550                | 256                |  
| 2nd Most Right   | 1.65 meters              | 2470                | 238                |
| 3rd Most Right   | 2.74 meters              | 2480                | 228                |
| Left  of Room    | 3.66 meters              | 2770                | 267                |

In conclusion, the testing of this data was to show where the maximum amount of light is, using a separate verification system (Light Meter). As a result, DIY Plantify did end up in the correct position in front of the window, where we tested the maximum amount of light was detected. 1st Day: Closest to Left Window (Due to sunset on Left/West Side) ; 2nd Day: Also closest to Left Window (Sun was directly beaming into all windows, least obstruction on left window).

**Further Light Sensitivity Verfications were conducted by Joshmita**

Graph showing Light Detection by Light Sensor vs. Position from source: 
![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/main/notebook/image30.png)

## 04/21/2023 - Meeting with Raman & Design was Discussed

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

Flow Chart of Design (for programming purposes):
![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/main/notebook/image18.png)

## 04/22/2023 - Connection between breadboard & PCB was made (Maya & Joshmita)

Connection between Arduino & Breadboard:
![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/main/notebook/image13.jpg)

Close up of Arduino attachments:
![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/main/notebook/image15.jpg)

Close up of Breadboard attachments: 
![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/main/notebook/image34.jpg)

Indication of Green Light --> Power Subsystem is ON:
Indication of blinking Blue Light --> Troubleshooting Purposes:
![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/main/notebook/11.png)

Schematic of Light Sensor Connection: 
![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/main/notebook/image16.png)

Final Full Schematic (TinkerCad):

![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/main/notebook/image8.png)

In our final design, we ended up implementing a breadboard with a bought dev board. This is due to the fact that we were having issues getting our PCB to work, so we opted to use a combination of a breadboard and dev board. Within this design schematic we have implemented our motor driver in the top left, which is able to connect and drive our 2 motors located in the back of the chassis. Next, we have our light sensor subsystem to the right of the motor driver, which is connected using a photocell and resistor to create a voltage division circuit. To the right of the light sensor subsystem, we have our LED notification system which incorporates a blinking LED and resistor in series. Connected to our arduino directly, we have our moisture subsystem which uses a moisture sensor, testing and collecting data of moisture levels based on what the metal prongs are connected to. One last implementation we added was a switch, which is able to turn on the system and move the chassis where maximum light is. As well, this button will turn on the moisture sensor to detect low moisture levels, and flash the blinking LED when below the threshold. 



## 04/22/2023 - Initial Code was designed & implemented (Joshmita & Hongshang)

Very initial functionality of the robot:
The robot moves towards the brightest light by first checking left, right, and center. The robot is equipped with a photocell that measures the intensity of light in its surroundings. The code records the light value to the left, center, and right by turning the robot in each direction and then records the maximum value to determine the direction of the light source. Based on this information, the robot moves towards the light source by adjusting the motor speeds.

The code initializes the pins and constants at the beginning of the program in the setup() function. The loop() function is called continuously, where the switch state is checked. If the switch is on, the robot searches for the brightest light source by following a specific sequence of turns and movements. The rightMotor() and leftMotor() functions are used to control the speed and direction of each motor. The robot stops if the switch is off.

Our main goals after the 1st initial coding:
1. Get the robot to stop moving once it’s found optimal light
2. Implement moisture sensor/LED system (that is, if moisture below certain moisture level, blink LED)
3. Make the robot move more smoothly (shouldn’t jerk so much)
4. Trying to use all 4 wheels (not fully necessary since basic functionality is working with 2 wheels- but would be nice if we could implement)
5. Trying to get the robot to move in straight line motions only (could be tough)
6. Implementing UV/IR light sensor instead of photocell (reach goal/not really necessary)

## 04/23/2023 - Fixed Issues & Made Moisture Implemented (Team)
1. Made sure the chassis stops when optimal light is detected and the desired position is achieved. 
2. Back two motors move at the same time at the same speed (constant rate between 0.5 -1.2 mph)

Moisture Sensor is connected by 3 pins to Arduino:

![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/main/notebook/image10.png)

## 04/24/2023 - Continued to resolve errors and issues; Notification subsystem is now fully implemented (Team)

*Code implemented by Joshmita

## 04/25/2023 - Refined & made final updated product before demo; Tested motion and notification subsystems (Team)

- Glass platform was added to our robot today by the machine shop so that we can put the plant on it. 
- Axle was added to the two front wheels to help ease the friction of the robot, and let it move more smoothly.

Test runs after programming new and improved code:
[Test1](https://drive.google.com/file/d/1ll1fXHr4sRN81HbiVXr6RRDm_tSz6ifv/view?usp=share_link)
[Test2](https://drive.google.com/file/d/1Q-D20-2DiU9arXtrRh4zE6f_ZVPylme1/view?usp=share_link)
[Test3](https://drive.google.com/file/d/17TonJKVUUsrl7szgIKjqdDtgaA7itb_l/view?usp=sharing) 

Improvements: 
- Robot now blinks LED if moisture is below a certain level.
  - When moisture sensor was put in the water, the LED did not blink
  - When moisture sensor was put in paper, the LED blinked as the moisture level is low

Tested the motion subsystem:
- Goal: The chassis should be able to move so that the plant does not fall off of it, and the platform should be large and durable enough to hold an indoor, medium-light plant.
- How: Show that the robot can carry an object between 2-8 pounds. 
- [Test Video](https://drive.google.com/file/d/1RWG3hcP99LffHtEo-0AsZFF_D7hqmoEo/view?usp=sharing)

## 04/26/2023 - Final Demo;Feedback received
Final Product with Plant on Platform: 
![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/main/notebook/image21.jpg)

Final Close-up of connections Made: 
![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/main/notebook/image23.jpg)

## 04/28/2023 - Further Tests were made using Moisture Sensor

Moisture Sensor on its own (air) - Shows a level of 0
![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/main/notebook/image48.jpg)

Moisture Sensor in Soil(Not watered in 4 days) - Shows a level of about 760 
![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/main/notebook/image44.jpg)

Moisture Sensor in Water - Shows a level of 899
![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/main/notebook/image22.jpg)
