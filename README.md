# SIT-315-Task-M1-T1p-

// C++ code
//
int trigger = 13;
int echo = 12;
int led = 7;

long duration = 0;
int cm = 0;
int inch = 0;

void setup(){
  Serial.begin(9600);
  pinMode (trigger,OUTPUT);
  pinMode (echo,INPUT);
  pinMode (led,OUTPUT);
}


  void loop()
  {
  digitalWrite(trigger, LOW); 
  digitalWrite(trigger, HIGH); 
  digitalWrite(trigger, LOW);
  
  duration = pulseIn(echo, HIGH);
  cm = duration*0.034/2;
  inch = duration*0.0133/2;
  
  if (inch <50){
    digitalWrite(led, HIGH);
   }
   else{
    digitalWrite(led, LOW);
   }
  
  if (inch < 100)
  {
     Serial.print("Inches: ");
     Serial.println(inch);
     Serial.print("Cm: ");
     Serial.println(cm);
  }
  
  delay(500);
  
}
