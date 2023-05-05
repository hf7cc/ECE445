
# Maya Kurup Worklog

## 02/08/23 - Initial Design (Team)
We made an initial design for our block diagram to encompass the vision we have for our project: 
![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/main/notebook/0.bmp)

We also talked to the Machine Shop about our plan and asked if they could build a chassis for us. We will look into online options for a chassis and a light component. If we cannot find one, they will build a chassis for us.

## 02/17/2023 - Chassis update and Design Document (Team)
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
  
  
Light Sensor [Part](https://learn.adafruit.com/adafruit-si1145-breakout-board-uv-ir-visible-sensor/downloads)

Light Sensor [Datasheet](http://www.adafruit.com/datasheets/Si1145-46-47.pdf)

![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/main/notebook/1.bmp)

*Could not find datasheet or any about VoltageRegulator, so was unused.

![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/main/notebook/2.bmp)

## 03/17/2023 - Chassis & Moisture Sensors were Bought through ECE Portal (Maya & Joshmita)

Moisture Sensor [Part](https://www.sparkfun.com/products/13322?_ga=2.48722852.34707985.1680741906-1735945614.1675881698)

Moisture Sensor [Git Data Files](https://github.com/sparkfun/Soil_Moisture_Sensor)

Moisture Sensor [Schematic](https://cdn.sparkfun.com/datasheets/Sensors/Biometric/SparkFun_Soil_Moisture_Sensor.pdf)

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

## 04/3/2023 → 04/5/2023 Another PCB & Circuit Schematic was created (Team)

We re-implemented our microcontroller in this new schematic, and fully implemented our motor driver and motion subsystems compared our first design,

## 04/6/2023 → 4/7/2023 - New PCB & Circuit Schematic was created (Team)

We implemented 2 motor drivers in this new and complete design.

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

Dimension of pot/plant to be used
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

## 04/20/2023 - Testing of Light Sensitivity using the Light Meter Began (Maya)

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

## 04/21/2023 - Meeting with Raman, Conducted subsystem verifications

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

## 04/22/2023 - Connection between breadboard & PCB was made (Maya & Joshmita)

The motor driver is implemented in the top left, and they are connected to the motors. The light sensor is the photocell in the diagram, which gives analog input to the arduino. To its right is our implementation of the notification subsystem LED, which will blink when the moisture sensor shown is below a particular threshold, in our case, 600. The switch shown will turn the robot on.
- Green Light indicates Power is on (on Arduino)
- Flashing blue light is used for troubleshooting purposes (on Arduino)

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

## 04/23/2023 - Fixed Issues; Robot moves in a straight path now (Team)
1. Made sure the chassis stops when optimal light is detected and the desired position is achieved. 
2. Back two motors move at the same time at the same speed (constant rate between 0.5 -1.2 mph)

## 04/24/2023 - Continued to resolve errors and issues; Notification subsystem is now fully implemented (Team)

Final code implementation:

const int PWMB = 8;
const int BIN2 = 9;
const int BIN1 = 10;
const int AIN1 = 11;
const int AIN2 = 12;
const int PWMA = 13;
const int SW_PIN = 7;     // Switch to turn the motors on and off
const int LIGHT_PIN = A0; // Photocell
const int LED_PIN = 2;
const int SOILPIN = A1;//Declare a variable for the soil moisture sensor
const int SOILPOWER = 5;//Variable for Soil moisture Power

  // Store light levels as array [left, center, right]
  int val = 0;
  int light_level;
  int count = 0;
  int max_light = 0;
  int max_count=0 ;
  int total_count=0;

// Constants
const int SEARCH_DRIVE_TIME = 200;  // Time to run one motor while searching
const int TURN_DRIVE_TIME = 200;    // Time to turn in a direction
const int MOVE_DRIVE_TIME = 300;   // Time to drive in a direction
const int STOP_DRIVE_TIME = 200;    // Time to stop after moving
const int NUM_LIGHT_LEVELS = 3;
const int DELAY_TIME = 1000;

void setup() {

  // Set switch pin
  pinMode(SW_PIN, INPUT_PULLUP);

  // Set the motor control pins as outputs
  pinMode(AIN1, OUTPUT);
  pinMode(AIN2, OUTPUT);
  pinMode(PWMA, OUTPUT);
  pinMode(BIN1, OUTPUT);
  pinMode(BIN2, OUTPUT);
  pinMode(PWMB, OUTPUT);
  pinMode(LED_PIN, OUTPUT);
  pinMode(SOILPOWER, OUTPUT);//Set D5 as an OUTPUT
  digitalWrite(SOILPOWER, LOW);
  // Initialize Serial comms
  Serial.begin(9600);
  Serial.println("Feed me photons!");
}

void loop() {
  // If switch is flipped, search for light
  if(digitalRead(SW_PIN) == LOW){
    if (count<11){
      light_level = analogRead(LIGHT_PIN);
        if (light_level>max_light){
          max_light=light_level;
          max_count=count;
        }
        drive(255, -255);
        delay(SEARCH_DRIVE_TIME);
        drive(0, 0);
        delay(STOP_DRIVE_TIME);
        count=count+1;
        }        
      total_count=22-max_count;
    if (count>10 && count <total_count){
        drive(-255, 255);
        delay(SEARCH_DRIVE_TIME);
        drive(0, 0);
       delay(STOP_DRIVE_TIME);
        count=count+1;
    }
    if (count>=total_count){
      digitalWrite(SOILPOWER, HIGH);//turn D5 "On"
      delay(10);//wait 10 milliseconds
      val = analogRead(SOILPIN);//Read the SIG value form sensor
      digitalWrite(SOILPOWER, LOW);//turn D5 "Off"
      if(val<850){
        digitalWrite(LED_PIN, HIGH);
        delay(DELAY_TIME);
        digitalWrite(LED_PIN, LOW);
        delay(DELAY_TIME);
      }
      else {
      digitalWrite(LED_PIN, LOW);
      delay(DELAY_TIME);
      }
    Serial.print("moisture: ");
    Serial.println(val);
      // drive(0, 0);
      // delay(999);
    }
   
    Serial.println();
    Serial.print("Max light: ");
    Serial.println(max_light);
    Serial.print("count: ");
    Serial.println(count);
    Serial.print("The Max count: ");
    Serial.println(max_count);
 
  }
}  

void rightMotor(int motorSpeed)                      
{
  // If speed is positive, run the motor forward
  if (motorSpeed > 0) {
    digitalWrite(AIN1, HIGH);
    digitalWrite(AIN2, LOW);
  // If it's negative, run the motor backward
  } else if (motorSpeed < 0) {
    digitalWrite(AIN1, LOW);
    digitalWrite(AIN2, HIGH);
  // If it's 0, brake the motor
  } else {
    digitalWrite(AIN1, LOW);
    digitalWrite(AIN2, LOW);
  }
  analogWrite(PWMA, abs(motorSpeed));
}

void leftMotor(int motorSpeed)
{
  // If speed is positive, run the motor forward
  if (motorSpeed > 0) {
    digitalWrite(BIN1, HIGH);
    digitalWrite(BIN2, LOW);
  // If it's negative, run the motor backward
  } else if (motorSpeed < 0) {
    digitalWrite(BIN1, LOW);
    digitalWrite(BIN2, HIGH);
  // If it's 0, brake the motor
  } else {
    digitalWrite(BIN1, LOW);
    digitalWrite(BIN2, LOW);
  }
  analogWrite(PWMB, abs(motorSpeed));
}
void drive(int leftSpeed, int rightSpeed) {
  leftMotor(leftSpeed);
  rightMotor(rightSpeed);
}

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
Final Product: 
![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/main/notebook/12.png)
