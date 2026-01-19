/*------ Arduino Fire Fighting Robot ver 2.0 Code ---- */
   
boolean fire = false;


//#define Left 4          // left sensor
//#define Right 5         // right sensor
#define Forward 6      //front sensor

#define LM1 8           // left motor
#define LM2 9           // left motor
#define RM1 11          // right motor
#define RM2 10          // right motor
#define pump 12         //water pumb



void setup()
{
   

  
  //pinMode(Left, INPUT);
  //pinMode(Right, INPUT);
  pinMode(Forward, INPUT);
 
  pinMode(LM1, OUTPUT);
  pinMode(LM2, OUTPUT);
  pinMode(RM1, OUTPUT);
  pinMode(RM2, OUTPUT);
  pinMode(pump, OUTPUT);
 

}
 
void put_off_fire()
{
  
 delay (500);
 
    digitalWrite(LM1, HIGH);
    digitalWrite(LM2, HIGH);
    digitalWrite(RM1, HIGH);
    digitalWrite(RM2, HIGH);
    digitalWrite(pump,HIGH);
    delay(500);
 
 

  digitalWrite(pump,LOW);
  
  fire=false;
}
 
void loop()
{

  

  
//  if (digitalRead(Left) ==1 && digitalRead(Right)==1 && digitalRead(Forward) ==1) 
    if (digitalRead(Forward) ==1)
    {
    
    digitalWrite(LM1, LOW);
    digitalWrite(LM2, LOW);
    digitalWrite(RM1, LOW);
    digitalWrite(RM2, LOW);
    }
    else if (digitalRead(Forward) ==1) 
    {
    digitalWrite(LM1,LOW);
    digitalWrite(LM2, HIGH);
    digitalWrite(RM1, HIGH);
    digitalWrite(RM2, HIGH);
    fire = true;
    
    }
    
  //  else if (digitalRead(Left) ==1)
  //  {
  //  digitalWrite(LM1, HIGH);
  //  digitalWrite(LM2, LOW);
  // digitalWrite(RM1,LOW);
  //  digitalWrite(RM2, HIGH);
  //  }
    
  //  else if (digitalRead(Right) ==1) 
  //  {
  //  digitalWrite(LM1, HIGH);
  //  digitalWrite(LM2, LOW);
  //  digitalWrite(RM1, HIGH);
  //  digitalWrite(RM2, HIGH);
  //  }
    delay(400);//change this value to change the distance
    
   
   
     while (fire == true)
     {
      put_off_fire();
      Serial.println("Fire Detected.");
     
     }}
   
