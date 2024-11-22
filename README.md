#include <HCSR04.h>


#define p_trigger 4
#define p_echo 5
int Ledred = 9 ;
int Ledyellow = 8 ;
int Ledgreen =7 ;
int Ledbranco =6 ;

UltraSonicDistanceSensor distanceSensor(p_trigger, p_echo);

int dist_cm,dist_m;

void setup () {
  Serial.begin(9600);
  pinMode(9,OUTPUT);
  pinMode (8, OUTPUT);
  pinMode (7,OUTPUT);
  pinMode (6, OUTPUT);
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
  delay(100);

  if (dist_cm < 10 ){
  digitalWrite (6, HIGH);
} else {
  digitalWrite (6, LOW);
}

if ((if (dist_cm >20)(if (dist_cm <30)){
  digitalWrite (7, HIGH);
} else {
  digitalWrite (7, LOW);
}

  if (dist_cm > 30) {
   digitalWrite(9, HIGH);
  
} else {
    digitalWrite(9, LOW);
}
if (dist_cm  >30 ){
  digitalWrite (8, HIGH);
} else {
  digitalWrite (8, LOW);
}

}



 
 
