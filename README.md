# RM-TASK
# Introduction 
we were given a problem statement in which we have to come with a solution to monitor table on which two pots were placed.
we had to determine the angle of rotation and direction of rotation with a distance of 6000 units.
 
# Problem Statement
Two pots, 1 black & 1 white, are placed on a rectangular table as shown. Find out the angle and direction of rotation of the table.

POTS: dia= 300 units, height =500 units
TABLE: 1500X500 unit^2

The pots are symmetrically aligned on the table.
Observer is at a perpendicular distance of 6000 units from the geometric center of the table.

# 
# Solution
We used 2 ultrasonic senors to determine the angle of rotation and used a color sensor which works in sync with ultrasonic sensors to determine the direction of the rotation. 
# 

# Materails used
  1. 2 Ultrasonic Sensors
  2. Colour Sensor(TCS3200)
  3. Arduino Board
  4. Jumper Wires
  5. Bread Board
# 
# Hardware
we used the ultrasonic sensors placed in a line with observer as shown in figure below. The ultrasonic sensor will detect the movement of the ends of the table and distance from the sensor and end of table will determine the angle of rotations. 
In simple words, using the pythogoras thyrom and distance between the sensor and table will do the job.
 
For the direction of rotation we'll use color sensor and ultrasonic sensor together to the accurate result.
First the color sensor detects which pot is placed in front of it.
after succesfull identification of the pot, Ultrasonic sensors come into play by determining the which which side of table is coming closer to the observer and which side is going away(refer the figure below),
and using the algorithium (below in software section) we can accuratelly determine the direction of rotation.  

![image](https://user-images.githubusercontent.com/71347979/153729943-f752cd60-5f33-4067-b363-bbe38188562c.png)

# Software
![image](https://user-images.githubusercontent.com/71347979/153729930-09481bc2-5be0-448d-a6b1-eac0ada03f6b.png)
**To determine the direction of rotation...**

So the algorithium is desgined in such a manner that whenever the color sensor detects color of the pot.

*If white color is detected on the left side...*
 
It compares d1 and d2 by taking values from ultrasonic sensors. after comparing the values if it comes out to be d1>d2 then it outputs clockwise on serial monitor. and if d2>d1 then it outputs anticlockwise on the serial monitor.

*If white color isn't detected...*

It again compares d1 and d2 and after comparing if d1>d2 then it outputs anticlockwise direction but if it is d2>d1 then it outputs clockwise direction on the serial monitor.
#
**To determine the angle of rotation**

The Left ultrasonic(1) calculate the distance by the formula -> (duration X (0.034/2)). After succesfull determination of the distance we'll move to calulating the angle of the rotation.
we can use the formala-> a*tan*(l/base) *where* base= 750 and l= distance-5750.
we'll get the output as pi/2-angle.
#
![image](https://user-images.githubusercontent.com/71347979/153729933-3c7552d9-4c70-4e69-8da3-b1322f391693.png)
