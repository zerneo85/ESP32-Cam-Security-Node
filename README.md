# ESP32-Cam-Security-Node Project
ESP32-Cam Security Node managed bij Home Assistant with ESPHome

# Introduction
As with many of the projects we start, this one started simple and with a single purpose but quickly grew to what it is today. Current day, it’s one of the many devices i have build and configured in Home Assistant that has a crucial role in the area of security. It is build on ESP32-Cam combined with 2 motion detection sensors, 1 temperature sensor and a buzzer for audio notifications.

Besides the use of security (Cam & Motion detection) it also services roles in light control and doorbel control. I have created a couple of security display nodes (Security- Clock, Security-Cat) that show by using RGB Led and audio notification triggers of the security nodes. If there is enough intrest, i will document these projects as well.

# Continuous improvement
As my partner often points out i have a issue with trying to improve everything.
So if you have any suggestions or improvements i would be very happy to implement them! While writing this i realizes i could add a RGB Led and i will try to implement this short term. I would be very happy if someone could help with the RCWL-0516 because it is still giving false triggers……

If you like to help or give suggestions use the form below.


# Sensors & Components
I have used the sensors below in the project. I don’t have positive experience with the HC-SR501 and was unable to fix all the false triggers it gives.
The STL files allow use of DHT11 or ds18b20, i think the DHT11 has better accuracy.
- ESP32Cam -Microcontroller
- AM312 – PIR Sensor
- * HC-SR501 -PIR Sensor (I was not able to fix the huge amount of false triggers)
- Micro USB 5V DIP Adapter board – Power
- Passive piezo buzzer
- Dallas ds18b20 – Temperature Sensor
- Resistor R4,7K
- DHT11 – Temperature Sensor
- RCWL-0516 – Doppler Sensor

# PCB Design
The PCB i used is a PCB Board Hole Grid Board from 7cm x 3cm that i soldered the sensors on. All the sensors (ESP32 Cam & PIR) that are on the front of the PCB are detachable, to achieve this i soldered 2 rows of 8 female pins en for the PIR sensor a 3 row female pin.

For power & ground i sewed a wire on row 3 & 8 over the lengt of the PCB.
The micro USB DIP i soldered on A4 for ground (i connected it to row 3) and A8 for 5v power.

## PCB Front
(https://github.com/zerneo85/ESP32-Cam-Security-Node/blob/main/Images/Security-Node%20PCB%20Front.png)

## PCB Back
(https://github.com/zerneo85/ESP32-Cam-Security-Node/blob/main/Images/Security-Node%20PCB%20Back.png)



# ESP Home YAML file for Home Assistant
In the directory [Code](https://github.com/zerneo85/ESP32-Cam-Security-Node/tree/main/Code) you can find the YAML file that i made and use in ESP Home in Home Assistant. Some important points are:

- I use the secrets file in ESP Home for all sensitive or device related data.
- The file makes use of the ds18b20 temperature sensor and not the DHT11 sensor.
- The ds18b20 has a disadvance in accuracy and requires a offset in temperature.
- To fix false alarms of the PIR & Doppler sensor i use a delayed_on value, for the PIR sensor it solves the false alarms.
- The Doppler sensor still requires some troubleshooting to get more stable.


# 3D Print STL files
I published the project on Thingiverse, https://www.thingiverse.com/thing:5064859

But the STL files can also be downloaded from the directory [Designs](https://github.com/zerneo85/ESP32-Cam-Security-Node/tree/main/Designs).
