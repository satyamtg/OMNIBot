#include <Ultrasonic.h>
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
{ Serial.begin(9600);
  pinMode (leftMotor, OUTPUT);
  pinMode (rightMotor, OUTPUT);
 }
void loop()
{
  dist=(ultrasonic.Ranging(CM));
  

if(dist>35)
{
  dist=(ultrasonic.Ranging(CM));
  leftValue = analogRead (leftInput);
  rightValue= analogRead (rightInput);
  Serial.println(leftValue);
  Serial.println("left value ^");
  Serial.println(rightValue);
  Serial.println("right value ^");
if ( leftValue < 600 && rightValue < 600 )
   {Serial.println("Stop");
     digitalWrite (leftMotor, LOW);
     digitalWrite (rightMotor, LOW);
   }
   else
{

     if
     ( leftValue > 600 && rightValue < 600 && dist > 25 )
    {
      Serial.println("Turn Right");
      if(dist>25){
      digitalWrite (leftMotor, LOW);
      digitalWrite (rightMotor, HIGH);
      dist=(ultrasonic.Ranging(CM));
      }
    }
 else{
   if (leftValue < 600 && rightValue > 600 && dist > 25  )
   {Serial.println("Turn Left");
   if(dist>25){
   digitalWrite (rightMotor, LOW);
   digitalWrite (leftMotor, HIGH);
   dist=(ultrasonic.Ranging(CM));
   }
   }
   else
   {
     if (leftValue > 600 && rightValue > 600 && dist > 25)
     {if(dist>25){
      Serial.println("Go Forward");
      digitalWrite (rightMotor, HIGH);
      digitalWrite (leftMotor, HIGH);
      dist=(ultrasonic.Ranging(CM));
     }
     }
   }
  }
 }

dist=(ultrasonic.Ranging(CM));}
else
{
  Serial.println("Stop by Ultrasonic");
  digitalWrite (leftMotor, LOW);
  digitalWrite (rightMotor, LOW);}
}
