## **Sample Code**
```c
#define Sensor 2
int val = 0;  // variable for reading the pin status

void setup() {
  pinMode(Sensor, INPUT);  // declare as input
  Serial.begin(9600);
}

void loop() {
  val = digitalRead(Sensor);  // read input value
  if (val == HIGH) {          // check if the input is HIGH
    Serial.println("Magnetic Signal Detected!");
  } else {
    Serial.println("No Magnetic Signal Detected!");
  }
  delay(500);
}
```