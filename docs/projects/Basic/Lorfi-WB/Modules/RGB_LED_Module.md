## **Sample Code**
```c
#define RED 13   // used as digital input
#define GREEN 2  // used as digital input
#define BLUE 14  // used as digital input
int val;

void setup() {
  pinMode(RED, OUTPUT);
  pinMode(BLUE, OUTPUT);
  pinMode(GREEN, OUTPUT);
}
void loop() {
  for (val = 255; val > 0; val--) {
    analogWrite(11, val);
    analogWrite(10, 255 - val);
    analogWrite(9, 128 - val);
    delay(1);
  }
  for (val = 0; val < 255; val++) {
    analogWrite(11, val);
    analogWrite(10, 255 - val);
    analogWrite(9, 128 - val);
    delay(1);
  }
}
```