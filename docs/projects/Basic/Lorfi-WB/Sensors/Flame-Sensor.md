## **Sample Code**
```c
#define Sensor 2
int State = 0;  // variable for reading the pin status

void setup() {
  Serial.begin(9600);
  // initialize the pushbutton pin as an input:
  pinMode(Sensor, INPUT);
}
void loop() {
  // read the state of the value:
  State = digitalRead(Sensor);
  if (State == HIGH) {
    Serial.println("Fire detected!");
  } else if(State == LOW) {
    Serial.println("No Fire detected!");
  }
}
```