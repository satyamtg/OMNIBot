#include"Ultrasonic.h"
#define triggerpin 7
#define echopin 4
Ultrasonic ultrasonic(triggerpin, echopin);
int leftInput=A0;
int rightInput=A3;
int leftMotor=9;
int rightMotor=12;
int leftValue = 0;
int rightValue = 0;
int dist=(ultrasonic.Ranging(CM));
void setup()
{ 
  Serial.begin(9600);
  pinMode (leftMotor, OUTPUT);
  pinMode (rightMotor, OUTPUT);
 
  }

 void loop()
 {int i=random(20);
  int ctr;
  ctr=0;
  Serial.println(i);
  float x= ultrasonic.Ranging(CM);
  Serial.println("Obstacle at");
  Serial.println(x);
  while(x<=30 && x>=16 &&i%2==0)
  {
    Serial.println("need to stop and find new path");
    digitalWrite(leftMotor, LOW);
    digitalWrite(rightMotor, LOW);
    Serial.println("Going Left");
    digitalWrite(leftMotor, HIGH);
    x= ultrasonic.Ranging(CM);
        
  }
   while(x<=30 && x>=16 &&i%2!=0)
  { Serial.println("need to stop and find new path");
    digitalWrite(leftMotor, LOW);
    digitalWrite(rightMotor, LOW);
    Serial.println("Going Right");
    digitalWrite(rightMotor, HIGH);
    x= ultrasonic.Ranging(CM);     
  }

      
  while(x<16 && x>10)
    
  {
       
    digitalWrite(leftMotor, LOW);
    digitalWrite(rightMotor, LOW);
    delay(1000);
    x= ultrasonic.Ranging(CM);
    ctr++;
    while(ctr==3 && i%2==0)
      {
        Serial.println("Going Left");
        digitalWrite(leftMotor, HIGH);
        delay(2000);
        ctr=0;
        x= ultrasonic.Ranging(CM);
        i=random(20);
        
      }
      while(ctr==3 && i%2!=0)
      {
        Serial.println("Going Right");
        digitalWrite(rightMotor, HIGH);
        delay(3000);
        ctr=0;
        x= ultrasonic.Ranging(CM);
        i=random(20);
      }
       
       
     
  }
  while(x>30)
  { 
    Serial.println("Going Forward");
    digitalWrite(leftMotor, HIGH);
    digitalWrite(rightMotor, HIGH);
    x= ultrasonic.Ranging(CM);
        
  }

    while(x<10)
  { 
    Serial.println("Object is too close...STOP");
    digitalWrite(leftMotor, LOW);
    digitalWrite(rightMotor, LOW);
    x= ultrasonic.Ranging(CM);
        
  }
 }//void loop cloised
