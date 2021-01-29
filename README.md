# Double-Servo-Robotic-Arm

This is how we built a robotic arm with two servos and four buttons!

## Week 1

### Description

### Images and Code

![Sketch of Robotic Arm Design](https://github.com/Wesswanson/Double-Servo-Robotic-Arm/blob/main/Screenshot%202021-01-29%20at%201.50.32%20PM.png?raw=true)
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
