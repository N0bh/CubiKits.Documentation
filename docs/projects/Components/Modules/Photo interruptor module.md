## **Sample Code**
```c
#define Sensor PB5
int val;  // define numeric variables val

void setup() {
  pinMode(Sensor, INPUT);  // define the photo interrupter sensor output interface
}
void loop() {
  val = digitalRead(Sensor);
  if (val == HIGH) {  // When the light sensor detects a signal is interrupted, it prints alerts.
    Serial.print("Object interupts");
  } else {
    Serial.print("Space is clear");
  }
  delay(100);
}
```
