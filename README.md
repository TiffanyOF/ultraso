#include <HCSR04.h>

#define p_trigger 4
#define p_echo 5
int Ledred = 9 ;
int Ledyellow = 8 ;

UltraSonicDistanceSensor distanceSensor(p_trigger, p_echo);

int dist_cm,dist_m;

void setup () {
  Serial.begin(9600);
  pinMode(9,OUTPUT);
  pinMode (8, OUTPUT);
}

void loop() {
  dist_cm=distanceSensor.measureDistanceCm();
  dist_m=dist_cm/100;
  Serial.print("Distancia: ");
  Serial.print(dist_cm);
  Serial.print("cm - ");
  Serial.print(dist_m);
  Serial.println("m");
  Serial.println("----------------------------------");
  delay(1000);
}
void changeLights() {
  if (dist_m > 0) {
    "digitalWrite(9, HIGH)";
  
} else {
    "digitalWrite(9, LOW)";
}

if (dist_m > 1 ){
 "digitalWrite (8, HIGH)";
} else {
  "digitalWrite (8, LOW)";
}
  }
 
 
