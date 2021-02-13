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

week one:
* We have started designing the arms in onshape, and are working out how to attach the servo to the arms in order for it to function properly. We have started thinking about the basics of the code and we are finding the best way for it to function. We still need to figure out 
* exact connection points of parts
* wiring of 4 buttons, and 2 servos
* how to finish the code

### Onshape 

https://cvilleschools.onshape.com/documents/ab6067fb057e1bdd1e35c96a/w/9bd70a3afb36c59bc0399ed6/e/4fe5c25cfc422637f83d71be

### Arduino

https://create.arduino.cc/editor/ljennin23/eddf6cce-00a5-4108-b38d-024daafda403

---

## Week 2
 
### Images and code

Here are some images of the almost finished design on Onshape. The link to view it on Onshape is below. It is still missing holes to connect servo attachments with the arms, as well as the attachment on the end, but the main design with dimensions is there.

This is the code, only missing the button pins and some serial printing to check for any mistakes when we test it:

```c++
// Include the Servo library
#include <Servo.h>
// Declare the Servo pin
int servoPin1 = 3;
int servoPin2 = 9;
// Create a servo object
Servo myServo1;
Servo myServo2;
int button1;
int button2;
int button3;
int button4;
int pin1;
int pin2;
int pin3;
int pin4;

int servo1angle = 90;
int servo2angle = 90;

void setup() {
  // We need to attach the servo to the used pin number
  myServo1.attach(servoPin1);
  myServo2.attach(servoPin2);
  Serial.begin(9600);
  myServo1.write(servo1angle);
  myServo2.write(servo2angle);
}
void loop() {
  button1 = digitalread(pin1);
  button2 = digitalread(pin2);
  button3 = digitalread(pin3);
  button4 = digitalread(pin4);

  if (button1 == HIGH & servo1angle < 180) {
    myServo1.write(servo1angle++);
    delay(10);
  }
  if (button2 == HIGH & servo1angle > 0) {
    myServo1.write(servo1angle--);
    delay(10);
  }
  if (button3 == HIGH & servo2angle < 180) {
    myServo2.write(servo2angle++)
    delay(10);
  }
  if (button4 == HIGH & servo2angle > 0 {
    myServo2.write(servo2angle--);
    delay(10);
  }
}
```

### Analysis: How the design/building process is going : We have the design fairly planned out in our heads we just need to finish the exact measurements. We need the measurments of the servo in order to create the holes big enough for them. We need to figure out how the wiring is going to play into the movement of the arm, because of our two servos. Aside from these unknowns we have most of our code ready and our design ready. 

### design

![robotarm](images/robotarm.png)


![robotarm2](images/robotarm2.png)


### Onshape

Here is a link to the onshape design: 
https://cvilleschools.onshape.com/documents/ab6067fb057e1bdd1e35c96a/w/9bd70a3afb36c59bc0399ed6/e/649546acbd99fbd2c4fc84f4

### Arduino

Here is a link to the code on the Arduino Editor: 
https://create.arduino.cc/editor/wswanso44/95b165dd-6eb1-45e6-b842-c0ea6bbc2cc4/preview

---
