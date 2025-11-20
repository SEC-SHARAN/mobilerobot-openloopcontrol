# MobileRobot-Openloopcontrol
# NAME: SHARAN S
# DEPT: B.E/CSE
# REG NO: 212224040309
## Aim:

To develop a python control code to move the mobilerobot along the predefined path.

## Equipments Required:
1. RoboMaster EP core
2. Python 3.7

## Procedure

Step1:
Initiate the MobileRobot.

Step2:
Connect your PC with the MobileRobot through Wi-Fi.

Step3:
Open batter_level.py file and check the battery.

Step4:
Open the other Python files and Program the movements of the robot using python.

Step5:
Execute the python program and record the movements.

## Program
```
from robomaster import robot
from robomaster import camera
import time

if _name_ == '_main_':
    # Initialize robot connection
    ep_robot = robot.Robot()
    ep_robot.initialize(conn_type="ap")

    # Get robot modules
    ep_chassis = ep_robot.chassis
    ep_led = ep_robot.led
    ep_camera = ep_robot.camera

    print("Video streaming started...")
    ep_camera.start_video_stream(display=True, resolution=camera.STREAM_360P)

    # Movement and LED sequence
    sequence = [
        (0.7, 0, 0),
        (0, 0, 30),
        (0.5, 0, 0),
        (0, 0, 30),
        (0.3, 0, 0),
        (0, 0, 15),
        (0.3, 0, 0),
        (0, 0, 12),
        (0.8, 0, 0),
        (0, 0, 12),
        (0.2, 0, -10),
        (0,0,-30),
        (1.4,0,0),
        (0,0,35),
        (0.6,0,0),
        (0, 0, 35),
        (0.8,0,0),
        (0,0,5),
        (0.9,0,0),
        (0,0,10),
        (0.7,0,0),
        (0,0,20),
        (0.8,0,0),
        (0,0,10),
        (0.8,0,0),
        (0,0,45),
        (0.5,0,0),
        (0,0,30),
        (0.6,0,0),
        (0,0,28),
        (1.1,0,0),
        (0,0,25),
        (0.5,0,0),
        (0,0,20),
        (0.8,0,0),
        (0,0,-25),
        (0.4,0,0),
        (0,0,-30),
        (0.6,0,0),
        (0,0,-20),

        (0.7,0,0),

        (0,0,30),
        (0.4,0,0),
        (0,0,40),
        (0.4,0,0),
        (0,0,10),
        (0.4,0,0),




    ]

    for (x, y, z) in sequence:
        ep_chassis.move(x=x, y=y, z=z, xy_speed=1.1).wait_for_completed()
        ep_led.set_led(comp="all", r=255, g=100, b=0, effect="on")

    # Stop camera and close connection
    time.sleep(4)
    ep_camera.stop_video_stream()
    print("Stopped video streaming...")

    ep_robot.close()
```

## MobileRobot Movement Image:

![robo](./img/robomaster.png)

![new](https://github.com/user-attachments/assets/05eb2416-287a-49a3-be60-cbe3271a262e)



<br/>
<br/>
<br/>
<br/>

## MobileRobot Movement Video:

https://youtu.be/Y1nH6TTyQHE

<br/>
<br/>
<br/>
<br/>

## Result:
Thus the python program code is developed to move the mobilerobot in the predefined path.


<br/>
<br/>

```
Mobile Robotics Laboratory
Department of Artificial Intelligence and Data Science/ Machine Learning
Saveetha Engineering College
```
