
Hongshang Worklog
=========


02/08/23 - Initial Design
---------	
We made an initial design for our block diagram to encompass the vision we have for our project: 

![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/main/notebook/0.bmp)


We also talked to the Machine Shop about our plan and asked if they could build a chassis for us. We will look into online options for a chassis and a light component. If we cannot find one, they will build a chassis for us.

02/28/2023 - Design Review Occured & Feedback was Given
---------	
From Raman: 
Based on Prof. Mironenko's suggestions, please consider making a few modifications in your high-level requirements. 

For e.g., fixing on a plant, reduce the content of your points etc. 
In point 1, you can just mention that you are planning to track the room and find the points with max and min luminosity/heat within the limits of your sensor. 
Modify point 2 demonstrate it a testable criterion, like, the chassis should be able to move to the location (X & Y coordinate) with most light in the room (for a certain time of the day) with at most 1.2 mph (have some accuracy component attached to it). Please modify this example point as per the scope of your project.
Modify point 3 to have an LED alarm instead of a speaker alarm, if you intend to change your notification subsystem.
Your block diagram needs modifications. Please refer to my design review feedback mail.
Please provide more details in your subsystem overview like details regarding the type of battery, microcontroller etc.
Please finalize the type of plant, it will help you define components like dryness, pot size etc. as those requirements are still vague.
Changing directions would induce acceleration, the constant speed is only good if you are moving in a straight line.
How do you plan to verify that the light sensor data is correct? Please put that in the verification section.
Please make necessary changes if you plan to change the notification subsystem from speaker to LED.
Please do not provide manufacturer guaranteed characteristics as your subsystem requirements. When you check the voltage with the multimeter, is it with the pot or without? The weight of the plant will be different before and after watering it.
It looks like you guys are doing experimental testing for your tolerance analysis. Could you provide some mathematical or simulations for the testing you are planning to do?
Please label the tables properly and keep the units consistent (3.3 V instead of 3.3 v).
Are your battery or any other components at risk as they are very close to moisture/soil? Please mention that in your safety.


03/06/2023 - Design Document Revisions were made to Update High-Level Requirements
---------	


In order to successfully obtain a fully working product by the end of this course, we plan to reach the following goals. 

The robot must be able to carry a plant and pot of total size of [weight: 15-20 pounds, diameter 10-20 cm ]
When placed indoors on a window sill, in front of a window, or in a balcony, without objects obstructing its path, the plant must “follow the light” by moving horizontally or vertically (on an X/Y axis) and must find optimal sunlight within 1 hour.
Robot must detect when moisture is less in the plant and must alert the user (LED must blink)


03/07/2023 - Meeting with Raman, Light Sensor & Voltage Regulator were gathered from ECE storage cabinet
---------	

TA Meeting Meeting Minutes
Do high-level requirements look good? - YES
How exactly do we connect the wheels (chassis) to the plant
Do we need a breadboard/circuit that we make connecting the wires on the chassis to the breadboard?
Do we directly connect to the PCB which then connects to the light sensor/
How to order parts: Help Maya w the specific tab portion on myECE
Will our moisture & light sensor found work on our PCB?
Chassis: The one we found connects with wires, should we find one that connects to PCB directly/in a dif way?
How do we design PCB board?
Which components are necessary?
What components are we missing?
Do we need to create an example schematic using a specific software?
Do we order the PCB or are the already ordered and we pick it up & add our components?
We create a design of our PCB through Gerber files, then upload it to MyPCB, and it will be approved then the physical model will be printed and given to us within 2-3 weeks after the AUDIT deadline
Ordering battery?
Get battery over motor specification
5V battery and using a voltage regulator→ adjust voltage regulator
Consider watering plant as part of weight
For connecting chassis wires to PCB
Attach wire to 2-pin connector
Parts: Octo part
https://octopart.com/ 
https://www.ultralibrarian.com/ 


Light sensor:
Datasheet: http://www.adafruit.com/datasheets/Si1145-46-47.pdf 

![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/main/notebook/1.bmp)

Voltage Regulator (Not Used in final project): 

![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/main/notebook/2.bmp)


03/17/2023 - Chassis & Moisture Sensors were Bought through ECE Portal
---------	

![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/main/notebook/3.bmp)


Moisture sensor: 
Hookup guide: https://learn.sparkfun.com/tutorials/soil-moisture-sensor-hookup-guide?_ga=2.13092599.1940704549.1680147698-1735945614.1675881698 
Schematic: https://cdn.sparkfun.com/datasheets/Sensors/Biometric/SparkFun_Soil_Moisture_Sensor.pdf 
Eagle Files: https://cdn.sparkfun.com/datasheets/Sensors/Biometric/SparkFun_Soil_Moisture_Sensor.zip 
Github: https://github.com/sparkfun/Soil_Moisture_Sensor 

![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/main/notebook/4.bmp)


Chassis:
Datasheet: http://cdn.sparkfun.com/datasheets/Robotics/DG02S.pdf 
Instruction Booklet: http://cdn.sparkfun.com/datasheets/Robotics/multi-chassis%204wd%20basic001.pdf 

![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/main/notebook/5.bmp)


## 03/22/2023 - PCB Schematic was submitted during 2nd Round of PCBway Orders
---------	

![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/main/notebook/7.png)


## 03/28/2023 - Meeting with Raman
---------	
TA Meeting Minutes
PCB will arrive around April 10 or quicker
Parts
Approved during spring break
Frequently check ECEB for parts
Design Doc: 11 points from email
Sign up for PCB demo to learn how to do it
Individual progress reports: due 3/29
Tell Hongshang
Lab Notebooks
Physical lab notebook or git-file: IPR
Git lab notebook - txt files
Not working with Machine Shop
Finalize plant, and restrictions of size based on Chassis


03/29/2023 - Individual Progress Report was Created
---------	
Updated Design Considerations: 
We changed the moisture sensor’s alert system from an audible noise provided by a speaker to a blinking LED. This is because the speaker notification system would get annoying to the user, especially if it goes off during unwanted times (sleep, important meetings/calls, etc). 
The voltage of each subsystem (except the moving robot - chassis) have been confirmed to provide 3.3V. This has been updated in our block diagram (Figure 2). 
Voltage regulator has now been updated to be part of the PCB.
Type of plant has been determined to be an indoor, medium light plant with a light intensity between 75-150 FC (Foot Candles - unit of measurement for light intensity on plants). Dimensions of the pot have been determined to have a diameter of about 15 cm, in order to fit in the chassis with a length of 16.5 cm and width of 15.7 cm. 

03/31/2023 - Design Doc Revisions were made to Update the Subsystem Requirements
---------	
Sensor subsystem
Sensor subsystem consists of a light sensor and moisture sensor. The light sensor will record comparative light intensity data during the initial setup and will continue to track results based on time of day, obstruction due to shadows, and seasonal changes. The moisture sensor will watch out for low moisture levels and will alert (Notification subsystem) the user when the plant needs to be watered. 

Requirements
Verification
The moisture sensor must be able to detect dryness within 2 days, and never send an alarm when not dry. 
Once we put the moisture sensor in our plant we will test the sensor by testing different amounts of moisture- that is, by gradually watering the plant and noticing the moisture levels that are read by the sensor
The values provided by the sensor range from approximately 0 to 880, where 0 is for when the sensor is dry and 880 is for when the sensor is completely saturated with moisture.

Verify the moisture sensor is working properly by taking moisture level measurements consistently throughout a week, and fact-check those levels with online resources and verifications of the plant itself. 
The light sensor should find the location with the most light within 15 cm of error.
Have a light source such as a lamp, and move the light sensor further away from it, and see if the illuminance (lx) detected by it decreases.
We will test it by recording light sensor data over a week and will compare the results to daily sunlight emissions to see if light is properly being detected by the sensor.

Continuously record the light sensor data over a weekly period, and make sure measurements being recorded are consistent and accurate with that daily sunlight emissions. 
The light sensor’s data must be correct
Test the light sensor with the phone's flashlight with different intensity, and see if the light sensor’s data can indicate which intensity is most bright. 


Motion subsystem
The motion system is a chassis robot carrying the pot. Microcontroller will send commands to it to move the plant to the desired position.

Requirements
Verification
The chassis must be able to move at a constant speed (constant rate between 0.5 -1.2 mph, as it moves in a straight line) to ensure the plant does not fall. As well, so measurements can be recorded at a constant rate. 
Record the speed at which the chassis moves using IO Lab or some sort of measurement tool that defines velocity and acceleration. 
The wheels should have an ideal amount of torque based on the size of the plant, in order for the plant to not fall. 
Calculate the torque using the equation: Torque = rFsin(theta), and solve for Force using IO Lab. 
The platform should be large and durable enough to hold an indoor, medium-light plant.
Platform carrying plant can be pre-determined, so make sure the plant being bought fits the size of this platform (diameter of potted-plant base should cover maximum 95% and minimum 45% of the surface area.) Since our chassis has the dimensions of 16.5x15.7 cm, our pot/plant should have a diameter of about 15 cm. 


Notification subsystem
The notification subsystem will consist of a LED. The LED will blink when the moisture sensor thinks it’s too dry. 

Requirements
Verification
Must be able to blink when receiving a signal of dryness. 
Connect the LED (a small, colored or white LED that we will take from previous labs used in classes) to the processor and let the processor send the signal. See if the LED blink.


Power subsystem
Power subsystem consists of a 3.3V lithium battery and voltage regulator. It handles power regulating and powering other subsystems.

Requirements
Verification
The system must provide over-current, over-voltage, under-voltage, and short-circuit protection. 
Connect the voltage regulator to various circuits with varying conditions, see if the regulator can shut down in time.
It must provide a stable 3.3 ± 0.1 V power source. 
Check voltage using a multimeter, and ensure that the proper amount of power is being supplied. All of the provided voltages will be tested in the lab, without water in the potted plant, or else testing issues (spilling or leakage of water) may occur. 


Microcontroller
The microcontroller (self-designed PCB board) will be able to control the chassis and both moisture and light sensors to send a signal of the desired location to the chassis. As well, the microcontroller will be able to analyze the data from the moisture sensor in order to send a signal to the LED to alert the user the plant needs to be watered. 

Requirements
Verification
Able to store 10 sets of data gathered for each hour during initial setup. 
Check the memory space after an experimental initial setup.
Able to send signal of current desired location to chassis. 
Give the chassis a set of data and check whether it arries desired location according to data.
Able to analyze data from the moisture sensor and send a signal to the LED when indicated by the data. 
Put the moisture sensor into a pile of dry paper and check if the LED will blink.







## 04/3/2023 → 4/7/2023 - New PCB & Circuit Schematic was created

![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/main/notebook/8.png)


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
| 9V Battery      | Wallgreens   | 1        | $23.99 |
| AA Batteries    | Wallgreens   | 8        | $14.99 |
| RedBoard PCB    | Sparkfun     | 1        | $25.66 |
| Motor Driver    | Sparkfun     | 1        | $23.49 |


04/21/2023 - Meeting with Raman, Conducted subsystem verifications
---------
TA Meeting Minutes: 
Make sure to show all high-level requirements working during demo w/proof
Moisture sensor/Notification system: show that the LED can blink, even if moisture data collection is unable to be made
Small box, 10by10, vehicle in one corner, robot is able to reach part with more light
MAKE a video demo and include in presentation
Mention there is lighting issue, here, so that’s why we did a video demo 
Robot should be able to carry a plant
Just show that it moves the plant
Make sure plant doesn’t fall
Increase size of pot maybe to ensure it’s fixes on the chassis and doesn’t fall
Don’t focus on entire room, focus just on a small area - like a box - since you didn’t mention size requirements
Can reach the light area within one hour (idea: sped up video/timelapse)
For every requirement and verification
Have some kind of proof - video or photo proof
Tested out voltage for example, shows 5 V, if in case that day things don’t work
Team knowledge
Everyone be familiar with everything about the project
Everyone present equally
Prepare with questions & rebuttals



04/22/2023: basic code completed.
---------
I had to reverse the input of one of the wheels to let the robot go straight, there must be something wrong with either robot assembling or circuit wiring.



04/23/2023 - Fixed Issues
---------
Made sure Chassis stops when optimal light data is collected, and desired position is achieved. 
Back two motors move at the same time at the same speed (constant rate between 0.5 -1.2 mph)
Moisture Sensor integration

04/24/2023 - Continued to resolve errors and issues
---------
04/25/2023 - tried to implement the robot with a state machine to function like daily life, but failed because of frequent arduino uploading errors.
---------
```
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








    int val = 0;
    int light_level;
    int count = 0;
    int max_light = 0;
    int peak_step=0 ;
    int total_count=0;
    int hour=3;
    int best_loc[3];
    int prev_time;
    int steptogo;
    int step;
    int now_time;
    int setupyes;
    int night,dark,morning,light=0;




// Constants
const int SEARCH_DRIVE_TIME = 500;  // Time to run one motor while searching
const int DELAY_TIME = 1000;




const int MORNING_THRESH= 300;
const int NIGHT_THRESH= 200;
const int HOUR_TIME= 3333;












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
  pinMode(SOILPOWER, OUTPUT);//Set D7 as an OUTPUT
  digitalWrite(SOILPOWER, LOW);




    hour=3;
    best_loc[3]={0};
    prev_time=millis();
    setupyes=1;














  // Initialize Serial comms
  Serial.begin(9600);
  Serial.println("Feed me photons!");
}








void loop() {
    if(digitalRead(SW_PIN) == LOW){
















        now_time=millis();    




        if((now_time-prev_time)>HOUR_TIME){




            if (hour>2){
                if (night){
                    if ((analogRead(LIGHT_PIN))>MORNING_THRESH){
                        light++;
                        if(light>1){
                            //morning=1;
                            hour=0;
                        }
                        else{light=0;}
                            //night=0;
                    }
                }
                else if ((analogRead(LIGHT_PIN))<NIGHT_THRESH){
                        dark++;
                        if(dark>2){
                        night=1;
                        if(setupyes!=1){
                            goback(best_loc[2]);
                        }
                    }  
                    light=0;
                }
                else {
                    dark=0;
                }  
            }




        else {
            if(setupyes==1 ){
                if(hour!=0){
                    goback(best_loc[hour-1]);
                    // hour_return=0;
                }
                if (count<11){
                    light_level = analogRead(LIGHT_PIN);
                    if (light_level>max_light){
                        max_light=light_level;
                        peak_step=count;
                    }
                    goon(1);
                    count=count+1;
                }        
                if (count>10){
                    if (best_loc[hour]<200){
                        best_loc[hour]=peak_step;
                        setupyes=(hour!=2);




                    }  
                    goback(11-peak_step);
           
                }
            }




            else if (setupyes==0){
                step=best_loc[hour];
                if (hour>0){
                    step=step-best_loc[hour-1];




                }      
                if(step>0){
                    goon(step);
                }
                else if(step<0){
                    goback(-step);
                }
            }




        }
















            prev_time=now_time;
            hour=hour+1;
        }
























            else {
                digitalWrite(SOILPOWER, HIGH);//turn D7 "On"
                delay(10);//wait 10 milliseconds
                val = analogRead(SOILPIN);//Read the SIG value form sensor
                digitalWrite(SOILPOWER, LOW);//turn D7 "Off"
                if(val<600){
                    digitalWrite(LED_PIN, HIGH);
                    delay(DELAY_TIME);
                    digitalWrite(LED_PIN, LOW);
                    delay(DELAY_TIME);
                    }
                else {
                    digitalWrite(LED_PIN, LOW);
                    delay(DELAY_TIME);
                }
            }












    }
}
```








04/26/2023 - Final Demo, Feedback received
---------
Final Product: 

![Image](https://github.com/hf7cc/ECE445--DIY-Plantify/blob/main/notebook/12.png)


