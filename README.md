CECS 347 – Project 2: A Following Robot

Project2Part3 Template

Preparation



You will need:



A LaunchPad



A robot car with the following components:



Two wheels and two DC motors



One motor driver with power supply circuit



A battery case with 6 to 8 batteries



Three Sharp IR distance sensors



Project Goals



Understand basic microcontroller hardware components:

GPIO, interrupts, ADC, and hardware PWM



Build an embedded control system that interfaces with switches, LEDs, DC motors, and sensors



Starter Files

Type	Name / Example

Starter Project	Project 2 Part 1 or Romi\_Car\_Test

Starter Main File	FollowingRobot.c

Reference Projects	Romi\_Car\_Test, ADCOneSample, WallFollower, FollowMe.c

Reference Descriptions



Romi\_Car\_Test – example for DC motors



ADCOneSample – single sample using ADC0 Sample Sequencer 3



WallFollower – three samples using ADC0 Sample Sequencer 2



FollowMe.c – main code for object following with one sensor on ADC SS3



Project Description



You will build a robot car that works in two modes:



Mode 1 – Object Follower



Mode 2 – Wall Follower



Switch Control



SW1 (PF4) – Toggle Activate / Deactivate the robot



SW2 (PF0) – Toggle Mode 1 ↔ Mode 2 (only when active)



The robot starts inactive.

After activation, it defaults to Mode 1.



When a mode is activated, the sensors perform 10 readings, then the robot executes the functions for that mode.



Mode 1 – Object Follower



The robot follows an object 20 cm ahead.



Object Movement	Robot Action

Forward	Moves forward (maintains 20 cm distance)

Backward	Moves backward (maintains 20 cm distance)

Turn Left / Right	Turns to follow object while maintaining distance

Stops	Robot stops

Out of Range	Robot stops

Object < 10 cm	Robot stops and enters inactive state

Mode 2 – Wall Follower



Detects and follows the closest wall (left or right).



The robot must not touch the wall or any obstacles.



(Optional) To stop the car: place an object < 10 cm in front → inactive state.



LED Color Indication

LED Color	Meaning

RED	Inactive

BLUE	Mode 1 – Object Follower

GREEN	Mode 2 – Wall Follower

Development Steps



Start from Project 2 Part 1 → rename to Following\_Robot.



Add module ADC0SS3.c/h (from ADCOneSample).



Test Follow\_Me.c for single-sensor following.



Replace Follow\_Me.c with Following\_Robot.c.



Replace ADC0SS3 with ADC1SS1 (for three sensors).



Example: see WallFollower/ADCSWTrigger.c.



Add two more sensors and implement object\_follower() in Following\_Robot.c.



Use follow\_me() from Follow\_Me.c as a starting point.



Implement wall\_follower() for Mode 2.



Hardware Specifications

Component	Requirement

System Clock	16 MHz PLL using external clock

PWM	Hardware PWM for DC motors

ADC	Module 1 Sample Sequencer 1

Sensors	3 IR sensors for object/wall detection

GPIO Pin Assignments

Pin	Device

PE1	Left IR sensor output

PE0	Front IR sensor output

PE2	Right IR sensor output

PB4	PWM – Left motor

PB5	PWM – Right motor

PB3 \& PB2	Direction – Left motor

PB7 \& PB6	Direction – Right motor

PF1 PF2 PF3	Onboard LEDs

PF0	Switch 2

PF4	Switch 1

Extra Challenges (Bonus Points)



Mode 2 Performance (3 pts max)



1st place – 3 pts | 2nd – 2 pts | 3rd – 1 pt



Hardware Design (2 pts) – Stable, well-wired system



⚠️ Note: When downloading or debugging code, disconnect power supply from the LaunchPad VBUS pin.



Deliverables

1\. Project Report



Include all required sections from the course template.

Special requirements:



Software Design:



Provide a flowchart illustrating your software solution.



Hardware Design:



Include a schematic and a photo of your robot car.



Operation:



Upload a video file or a YouTube link showing your robot demonstration.



If using a link, include it in the Operation section of your report.



2\. Source Code Submission



Submit all source files (.c and .h) to GitHub Classroom.



Commit each feature or major change separately with clear descriptions.



Ensure your commits show the team’s development process, not just the final soluti

