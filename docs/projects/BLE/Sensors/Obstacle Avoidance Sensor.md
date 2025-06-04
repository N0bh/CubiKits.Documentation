## **Sample Code**
```c
#define Sensor PB5
int sensorState = 0;  // variable for reading the sensor status

void setup() {
  pinMode(Sensor, INPUT);
  Serial.begin(9600);
}
void loop() {
  // read the state of the sensor value:
  sensorState = digitalRead(Sensor);
  // if it is, the sensorState is HIGH:
  if (sensorState == HIGH) {
    Serial.println("Obstacle Detected");
  } else {
    Serial.println("No Obstacle Detected!");
  }
  delay(100);
}
```ard