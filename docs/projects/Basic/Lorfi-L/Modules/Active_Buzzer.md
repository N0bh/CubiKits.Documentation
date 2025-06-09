## **Sample Code**
```c

#define buzzPin PB5  //Connect Buzzer to a Digital Pin

void setup() {
  pinMode(buzzPin, OUTPUT);
}
void loop() {
  digitalWrite(buzzPin, HIGH);
  delay(1000);
  digitalWrite(buzzPin, LOW);
  delay(1000);
}
```