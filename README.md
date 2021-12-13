#include <SoftwareSerial.h>
SoftwareSerial bt(2,3);

int LED_R=7;
int message;

void setup() {

  Serial.begin(9600);
  bt.begin(9600);
  pinMode(LED_R,OUTPUT);
}

void loop() {

  if(bt.available()>0){
    message=bt.read();
    Serial.println(message);

    switch(message){
      case 1: digitalWrite(LED_R,HIGH); break;
      case 2: digitalWrite(LED_R,LOW);  break;
    }
  }
}
