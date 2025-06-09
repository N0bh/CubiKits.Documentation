## **Sample Code**
```c
#define Sensor PB5

void setup() {
  pinMode(Sensor, INPUT);      //Set touch sensor pin to input mode
  Serial.begin(9600);
}

void loop() {
  if (digitalRead(Sensor) == HIGH) {  //Read Touch sensor signal
    Serial.println("Sensor Touched!");    // if Touch sensor is HIGH, print "Sensor Touched!"
  } else{
    Serial.println("Sensor Untouched!");  // if Touch sensor is LOW, print "Sensor Untouched!"
  }
  delay(100);
}
```