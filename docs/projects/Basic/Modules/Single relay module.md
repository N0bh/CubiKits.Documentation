## **Sample Code**
```c
#define Relay PB5

void setup() {
  pinMode(Relay, OUTPUT);  //Set Pin3 as output
}
void loop() {
  digitalWrite(Relay, HIGH);    //Turn off relay
  Serial.println("Relay ON!");  //Print that relay is ON!
  delay(2000);
  digitalWrite(Relay, LOW);     //Turn on relay
  Serial.println("Relay OFF!");  //Print that relay is OFF!
  delay(2000);
}
```