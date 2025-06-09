## **Sample Code**
```c
#define Sensor A0 //Connect sensor pin to Analog Input

void setup() {
  Serial.begin(115200);
  pinMode(Sensor, INPUT);
}

void loop() {

  Serial.print("Moisture Sensor Value:");
  Serial.println(Sensor);
  delay(100);
}
```