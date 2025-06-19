## **Sample Code**
```c
#define Sensor 2

void setup() {
  pinMode(Sensor, OUTPUT);
}
void loop() {
  digitalWrite(Sensor, HIGH);

  delay(1000);
  digitalWrite(Sensor, LOW);
  delay(1000);
}
```

## **Sample Code**
```c
#include <IRremote.h>
IRsend irsend;
void setup() {}
void loop() {
  irsend.sendRC5(0x0, 8);  //send 0x0 code (8 bits)
  delay(200);
  irsend.sendRC5(0x1, 8);
  delay(200);
}
```