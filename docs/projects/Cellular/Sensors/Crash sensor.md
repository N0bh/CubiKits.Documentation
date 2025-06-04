## **Sample Code**
```c
#define Sensor PB5  // set pin for collision sensor

int sensorState;  // set digital variable val
void setup() {
  pinMode(Sensor, INPUT);  // set collision sensor as input
}
void loop() {
  sensorState = digitalRead(Sensor);
  if (sensorState == LOW)            // when collision sensor detects a signal, it prints its instance.
  {
    Serial.println("Shock Detected!");
    delay(500);
  } else {
    Serial.println("Shock Not Detected!");
    delay(500);
  }
}
```