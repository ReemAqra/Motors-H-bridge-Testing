# Motors-H-bridge-Testing
int Echo1 = A5;//LEFT_SENSOR ECHO
int Trig1 = A4;//LEFT_SENSOR TRIG
int Echo2 = A3;//MID_SENSOR ECHO
int Trig2 = A2;//MID_SENSOR TRIG
int Echo3 = A1;//RIGHT_SENSOR ECHO
int Trig3 = A0;//RIGHT_SENSOR TRIG

int in1=9;
int in2=6;
int in3=10;
int in4=8;
int ENA=5;
int ENB=13;

int ABS=200;

int Left_Distance=0,Right_Distance=0,Middle_Distance=0;

void _mForward(){
  digitalWrite(in1,LOW);
  digitalWrite(in2,HIGH);
  digitalWrite(in3,LOW);
  digitalWrite(in4,HIGH);
  analogWrite(ENA,ABS);
  analogWrite(ENB,ABS);
  Serial.println("ROPOOT_MOVING_FORWARD");
}
void _mBack(){
  digitalWrite(in1,HIGH);
  digitalWrite(in2,LOW);
  digitalWrite(in3,HIGH);
  digitalWrite(in4,LOW);
  analogWrite(ENA,ABS);
  analogWrite(ENB,ABS);
  Serial.println("ROPOOT_MOVING_BACKWARD");  
}
void _mLeft(){
  digitalWrite(in1,LOW);
  digitalWrite(in2,HIGH);
  digitalWrite(in3,LOW);
  digitalWrite(in4,LOW);
  analogWrite(ENA,ABS);
  analogWrite(ENB,ABS);
  Serial.println("ROPOOT_MOVING_LEFT");  
}
void _mRight(){
  digitalWrite(in1,LOW);
  digitalWrite(in2,LOW);
  digitalWrite(in3,LOW);
  digitalWrite(in4,HIGH);
  analogWrite(ENA,ABS);
  analogWrite(ENB,ABS);
  Serial.println("ROPOOT_MOVING_RIGHT");  
}
void _mStop(){
  digitalWrite(in1,LOW);
  digitalWrite(in2,LOW);
  digitalWrite(in3,LOW);
  digitalWrite(in4,LOW);
  analogWrite(ENA,LOW);
  analogWrite(ENB,LOW);
  Serial.println("ROPOOT_STOP"); 
}
/*Ultrasonic distance measurement Sub function*/
int Left_Distance_test(){
  digitalWrite(Trig1,LOW);
  delayMicroseconds(2);
  digitalWrite(Trig1,HIGH);
  delayMicroseconds(20);
  digitalWrite(Trig1,LOW);
  float Fdistance=pulseIn(Echo1,HIGH);
  delay(10);

  Fdistance=Fdistance/29 /2;
  return(int)Fdistance;
  }

int Middle_Distance_test(){
  digitalWrite(Trig2,LOW);
  delayMicroseconds(2);
  digitalWrite(Trig2,HIGH);
  delayMicroseconds(20);
  digitalWrite(Trig2,LOW);
  float Fdistance=pulseIn(Echo2,HIGH);
  delay(10);

  Fdistance=Fdistance/29 /2;
  return(int)Fdistance;
  }

int Right_Distance_test(){
  digitalWrite(Trig3,LOW);
  delayMicroseconds(2);
  digitalWrite(Trig3,HIGH);
  delayMicroseconds(20);
  digitalWrite(Trig3,LOW);
  float Fdistance=pulseIn(Echo3,HIGH);
  delay(10);

  Fdistance=Fdistance/29 /2;
  return(int)Fdistance;
  }  

void setup() {
  pinMode(ENA,OUTPUT);
  pinMode(ENB,OUTPUT);
  
  pinMode(in1,OUTPUT);
  pinMode(in2,OUTPUT);
  pinMode(in3,OUTPUT);
  pinMode(in4,OUTPUT);
  
  digitalWrite(in1,HIGH);
  digitalWrite(in2,LOW);
  analogWrite(ENA,200);
  
  digitalWrite(in3,HIGH);
  digitalWrite(in4,LOW);
  analogWrite(ENB,200);
  
  delay(2000);
  
  digitalWrite(in1,LOW);
  digitalWrite(in2,LOW);
  digitalWrite(in3,LOW);
  digitalWrite(in4,LOW);
  delay(2000);
  
  digitalWrite(in1,LOW);
  digitalWrite(in2,HIGH);
  analogWrite(ENA,200);
  
  digitalWrite(in3,LOW);
  digitalWrite(in4,HIGH);
  analogWrite(ENB,200);
  
  delay(2000);
  
  digitalWrite(in1,LOW);
  digitalWrite(in2,LOW);
  digitalWrite(in3,LOW);
  digitalWrite(in4,LOW);
  delay(2000);
  
//  digitalWrite(in1,HIGH);
//  digitalWrite(in2,LOW);
//  analogWrite(ena,127);
//  
//  digitalWrite(in3,HIGH);
//  digitalWrite(in4,LOW);
//  analogWrite(ena1,127);
//  
//  delay(2000);
//  digitalWrite(in1,LOW);
//  digitalWrite(in2,LOW);
//  digitalWrite(in3,LOW);
//  digitalWrite(in4,LOW);
//  delay(2000);
//  
//  digitalWrite(in1,LOW);
//  digitalWrite(in2,HIGH);
//  analogWrite(ena,127);
//  digitalWrite(in3,LOW);
//  digitalWrite(in4,HIGH);
//  analogWrite(ena1,127);
//  delay(2000);
//  digitalWrite(in1,LOW);
//  digitalWrite(in2,LOW);
//  digitalWrite(in3,LOW);
//  digitalWrite(in4,LOW);
//  delay(2000);
  

}

void loop() {
  // put your main code here, to run repeatedly:

}
