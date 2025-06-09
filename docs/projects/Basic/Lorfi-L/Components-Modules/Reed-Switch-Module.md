## **Sample Code**
```c
#define Sensor PB5
int val;  //define digital variable val

void setup() {
  pinMode(Sensor, INPUT);  //define magnetic ring sensor as output interface
  Serial.begin(9600);
}
void loop() {
  val = digitalRead(Sensor);  // read and assign the value of digital interface 3 to val
  if (val == HIGH) {          //When a signal is detected by magnetic ring sensor, LED will flash
    Serial.println("Signal Detected!");
  } else {
    Serial.println("No Signal Detected!");
  }
  delay(100);
}
```