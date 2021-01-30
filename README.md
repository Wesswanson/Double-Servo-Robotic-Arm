# Double-Servo-Robotic-Arm

This is how we built a robotic arm with two servos and four buttons!

### Description

The goals of this project are to:
* Create a double servo robotic arm that can be moved to many different locations with four buttons
* Draw a picture with a pen attached to the end of the robotic arm
* Launch a ball off of an attachment at the end of the robotic arm (possibly controlled with a 5th button)

Though right now there isn't much here, you can view the CAD design in Onshape with [this link](https://cvilleschools.onshape.com/documents/ab6067fb057e1bdd1e35c96a/w/9bd70a3afb36c59bc0399ed6/e/649546acbd99fbd2c4fc84f4)!

## Week 1

### Images and Code

Below is the sketch design we are working off of right now. The first arm will be attached to a continuous servo, which is attached to a base with a battery and arduino. The other end of the first arm will have another continuous servo attached to the bottom of it, which is holding a second arm that is short enough to make a continuous rotation without hitting the base. the end of that arm can have a ball launching or pen attachment.

![Sketch of Robotic Arm Design](https://github.com/Wesswanson/Double-Servo-Robotic-Arm/blob/main/Screenshot%202021-01-29%20at%201.50.32%20PM.png?raw=true)

This is an outline with what the code will do (written out as Pseudo code instead of the completed, working code):

```c++
/*
This code will control one continuous servo with two buttons and another continuous servo with two
other buttons. This will allow a robotic arm to operate when the buttons are pushed.
*/

Variables:
button1
button2
button3
button4

void setup() {
    attach both servos here
}

void loop() {
  button1 = the current value of button 1
  button2 = the current value of button 2
  button3 = the current value of button 3
  button4 = the current value of button 4
    if button1 is high, move servo1 left
    if button2 is high, move servo1 right
    if button3 is high, move servo2 left
    if button4 is high, move servo2 right
}
```

### Analysis: How the design/building process is going

---
