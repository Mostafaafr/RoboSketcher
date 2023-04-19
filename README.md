# RoboSketcher
Use a robot arm to draw stuff for you!
![Joystick Plotter](https://user-images.githubusercontent.com/72535684/233198326-91c4b9e2-6188-4aaf-a9a3-0374db1f47c1.jpg)

There are two iterations of the sketcher. One can be controlled manually using two potentiometers, the other can be controlled entirely by code using an arduino and a closed loop feedback system.

This is the circuit for the manually controlled one:

![Sketcher Trimmer Circuit](https://user-images.githubusercontent.com/72535684/233199471-69633d15-e3de-422c-87ae-6af1b465bb88.jpg)

I used two servo motors mounted to a plotter that could move in the X and Y directions, and used a 3D printed spring-loaded case to hold the pen. The case had a screw mechanism that let me control when the pen was writing vs. when I wanted to reset its position. Essentially, the circuit uses two potentiometers with trimmers and a voltage divider to change the input to the opamps. We can then essentially read the voltage value we are sending to the opamp and use it as a way to drive the motors. This implementation is fairly simple once you have the Analog plotter working, the more interesting implementation is the closed feedback loop case.


To build our closed feedback loop, we essentially replace the trimmers with arduino pins, and we can control the voltage at these pins using a PWM signal to modulate our voltage. We do need to keep track of our position in this implementation, so we use a closed feedback loop.
![Analog Plotter Arduino Circuit](https://user-images.githubusercontent.com/72535684/233203960-67822504-147d-4b80-bef6-cb7d55655841.jpg)
