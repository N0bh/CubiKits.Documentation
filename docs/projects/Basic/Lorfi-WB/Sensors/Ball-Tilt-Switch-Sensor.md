## **Sample Code**
```c
#define Sensor 2

void setup() {
  pinMode(Sensor, INPUT);  // Set digital pin 3 to input mode
  Serial.begin(9600);
}
void loop() {
  if (digitalRead(Sensor) == HIGH)  //Read sensor value
  {
    Serial.println("Sensor is tilted");  // Print "Sensor is tilted" when the sensor is tilted
  } else {
    Serial.println("Sensor is stable");  // Print "Sensor is stable" when the sensor is not triggered
  }
  delay(100);
}
```