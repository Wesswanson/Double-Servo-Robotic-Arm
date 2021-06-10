# Double-Servo-Robotic-Arm

This is how we built a portable robotic arm with two servos and four buttons!

### Description

The original goals of this project were to:
* Create a double servo robotic arm that can be moved to many different locations with four buttons
* Draw a picture with a pen attached to the end of the robotic arm
* Launch a ball off of an attachment at the end of the robotic arm (possibly controlled with a 5th button)

We later motified the goals to just create a functioning robotic arm with two servos, an Arduino Uno with a prototyping shild and breadboard, a 9V battery, and 3D printed and lazercut pieces. This repository will show how the design, coding, and wiring evolved over the first few weeks of the project, and what the end product was.

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

* We have started designing the arms in onshape, and are working out how to attach the servo to the arms in order for it to function properly. We have started thinking about the basics of the code and we are finding the best way for it to function. We still need to figure out:
* The exact connection points of parts
* The wiring of the 4 buttons, and 2 servos
* how to finish the code

---

## Week 2
 
### Images and code

Here are some images of the almost finished design on Onshape. The link to view it on Onshape is below. It is still missing holes to connect servo attachments with the arms, as well as the attachment on the end, but the main design with dimensions is there.

![image](https://github.com/Wesswanson/Double-Servo-Robotic-Arm/blob/main/robotarm.png?raw=true)
![image](https://github.com/Wesswanson/Double-Servo-Robotic-Arm/blob/main/robotarm2.png?raw=true)

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

### Analysis: How the design/building process is going: 

We have the design fairly planned out in our heads we just need to finish the exact measurements. We need the measurments of the servo in order to create the holes big enough for them. We need to figure out how the wiring is going to play into the movement of the arm because of our two servos. Aside from these unknowns we have most of our code ready and our design ready. We did have to change the code and switch to using regular servos instead of continuous servos so the wires don't get tangled.

### Onshape

Here is a link to the onshape design: 
https://cvilleschools.onshape.com/documents/ab6067fb057e1bdd1e35c96a/w/9bd70a3afb36c59bc0399ed6/e/649546acbd99fbd2c4fc84f4

### Arduino

Here is a link to the code on the Arduino Editor: 
https://create.arduino.cc/editor/wswanso44/95b165dd-6eb1-45e6-b842-c0ea6bbc2cc4/preview

---

## Week 4

## Images and code
Here is the final CAD document on Onshape. In the past two weeks we created a new acrylic sheet to connect the first servo to the base, and then used screws to attach the acrylic to the 3D printed base. 


Link to code: [click here](https://create.arduino.cc/editor/wswanso44/95b165dd-6eb1-45e6-b842-c0ea6bbc2cc4/preview)

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
int pin1=3;
int pin2=4;
int pin3=5;
int pin4=6;

int servo1angle = 90;
int servo2angle = 90;

void setup() {
  // We need to attach the servo to the used pin number
  myServo1.attach(servoPin1);
  myServo2.attach(servoPin2);
  Serial.begin(9600);
  myServo1.write(servo1angle);
  myServo2.write(servo2angle);
  pinMode(pin1, INPUT);
  pinMode(pin2, INPUT);
  pinMode(pin3, INPUT);
  pinMode(pin4, INPUT);
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
  else if (button2 == HIGH & servo1angle > 0) {
    myServo1.write(servo1angle--);
    delay(10);
  }
  if (button3 == HIGH & servo2angle < 180) {
    myServo2.write(servo2angle++)
    delay(10);
  }
  else if (button4 == HIGH & servo2angle > 0 {
    myServo2.write(servo2angle--);
    delay(10);
  }
}
```
Here is the link to the design on Onshape: [link](https://cvilleschools.onshape.com/documents/ab6067fb057e1bdd1e35c96a/w/9bd70a3afb36c59bc0399ed6/e/4fe5c25cfc422637f83d71be)

This is the almost completed CAD design:
(note: not all the screws are the correct length for parts that we can actually use and will fit in this design. This will be fixed soon!)

![image](https://user-images.githubusercontent.com/71406916/109374690-18622200-7885-11eb-8f49-7b85eccd0509.png)

### Analysis: How the design/building process is going: 

The planning and design proccess is finished, now we have to actually build it. We had to design some more acrylic sheets in order to make the final project work as planned, but in the end, it all worked out. The code is finished and we changed it from the continuous servo to the regular servo, therefore creating some slight changes. We can always add an acrylic sheet to display the buttons on, or an attachment on the end, but for now we have the design for a (hopefully) functional robotic arm, so we're happy with how it turned out for now. This project was very fun.

## Final week before fabrication

### Description

This week we adjusted the location of the battery and arduino on the bace to make the wiring more realistic. We also shrunk the size of the bace to reduce the material needed. We added an acrylic sheet above the first servo to attach it to the bace, and corrected mistakes in attaching the second servo. We added panel mounted buttons, but still need to adjust the location of them to make it easier to use. I think this week we realized that there were a lot of complications in our design when we actually got close to the fabrication process. Hopefully after a few more adjustments it will be ready to build!

You can see the updated CAD design on [Onshape](https://cvilleschools.onshape.com/documents/ab6067fb057e1bdd1e35c96a/w/9bd70a3afb36c59bc0399ed6/e/4fe5c25cfc422637f83d71be)

### End of project Analysis:

We accomplished creating the double servo robotic arm before the deadline. We had to ask about small measurements and details in the CAD portion, but other than that we didn't hit too many bumps in this project. We finished and had a great time doing it! 

### Final steps of completion/ what is holding us back

As Mr. Hemlstetter suggested we decided to put our buttons on the acrylic so that the breadboard is more free and it really completes our project. The only setback is that the buttons are too tall to let the arm go over them. We need to create a different mate, or find another place for the buttons. After this our project will be ready for fabrication!

### Plan for after spring break

Lulu is going to be in school after spring break and Wes is staying virtual. We need to correct a small error to the servo platfrom hole, which we cannot do ourselves, and after that all we need to do is fabricate. We are moving at a good pace and are almost complete, this indicates that we are on time to be done soon. When we return from spring break the first thing we are going to do is print and assemble the project. 

---

## Final steps: Wiring, Fabrication & Completion

### Description

Between the begining of April and the end of school in June, we fabricated the robotic arm and completed the wiring and code until it mostly worked. We had some problems with it, mostly with the weight being too heavy on the first servo which caused it to get off balance at first, and once it was working, one of the servos had a stripped gear and would overcorrect itself so much that the entire arm began vibrating. We figured out the solutions to these problems, though we ran out of time to replace the servo and change the code. Here is the final CAD design, wiring diagram, and photos of the completed project, as well as a reflection on the project:

### Final CAD designs

![cad without arms final photo](https://raw.githubusercontent.com/Wesswanson/Double-Servo-Robotic-Arm/main/Screen%20Shot%202021-06-10%20at%202.34.13%20PM.png)

### Wiring diagram

[link to wiring diagram on Tinker CAD](https://www.tinkercad.com/dashboard)

### Colpleted project

### Reflection

The double servo arm was much harder than the single servo arm because we had to wire four buttons, and two servos. In the begginning of the fabrication process we realized that the weight balance of the arm was off. We had to lazer cut new holes in the middel of the first arm to counter balance the second servo and the second arm. Once we figured out the final wiring on Tinker CAD all that is left to do is plug in the code and then our project will be complete. As we started the final wiring we realized that we had changed a lot of the pin numbers for the buttons and the servos. Once the code was changed to match the correct pin numbers our double servo robot arm was complete and working. 

---
