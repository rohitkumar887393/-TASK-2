# -TASK-2

AIM
Aim of this project is to rotate a stepper motor clockwise or anti clock wise based on signal receive by  two IR sensor 

PROCEDURE:
1st we done connectivity using wire with Arduino, Both IR sensor, TB6600 Driver with Stepper motor,
After that wrote code for that arrangement on Arduino IDE from various sources and then upload this code to Arduino board using b-type connector ,
after that it's time to give power to tb6600 driver and simulate it 

RESOURCE:

Circuit connectivity Source is this :> https://curiousscientist.tech/blog/arduino-tb6600-wiring-stepper-motor
IR sensor connectivity is by myself
code source for this project is from here > https://www.makerguides.com/tb6600-stepper-motor-driver-arduino-tutorial/

Thoughtprocess:

Actually I watched many video on youtube related to these type of project like about Arduino,stepper motor IR sensor,So i didn't find more difficulties while doing this and also i leant how to connect these device
and also with the help with some website, so connectivity was bit easy ,there was not need to thought on that but while coding ,this was bit tough but however i had manage to code with the help of many website one of them i mentioned above .

What we learn:
I learn many things about these hardware ,this is my first time to work with physical Electronics component and explore about TB6600 driver not much just intro and Arduino,IR sensor ,Working Principle of Stepper Motor and Why and Where do we use this .


THIS is code for this Project

//define pins for IR sensor and Motor
const int irPinclock = 4; 
const int irPinanticlk = 3; 
#define dirPin 8
#define stepPin 9

 int stepsPerRevolution =5000;
void setup() {

  pinMode(irPinclock, INPUT); 
  pinMode(irPinanticlk, INPUT); 
  pinMode(dirPin, OUTPUT); 
  pinMode(stepPin, OUTPUT);
}

void loop() {
 
//read ir sensor
int irValueclock=digitalRead(irPinclock);
int irValueanticlk=digitalRead(irPinanticlk);


  // If only clock IR sensor detects an object, rotate clock wise
  if (irValueclock == LOW) { 
    digitalWrite(dirPin, LOW); 
    for(int i=0;i<stepsPerRevolution;i++){
     digitalWrite(stepPin, HIGH);
     delayMicroseconds(500);
     digitalWrite(stepPin, LOW);
     delayMicroseconds(500);
  }
  }  


  #Thankyou
