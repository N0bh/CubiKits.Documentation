## **Sample Code**
```c
#define Sensor 2  // PB5 corresponds to a pin number (depends on the board, e.g. D11 on Uno)

// State variable to detect knock
volatile bool knockDetected = false;

void setup() {
  pinMode(Sensor, INPUT);
  attachInterrupt(digitalPinToInterrupt(Sensor), blink, FALLING);  // Use digitalPinToInterrupt
  Serial.begin(9600);
}

void loop() {
  if (knockDetected) {
    knockDetected = true;
    Serial.println("Knock Detected!");
    delay(1000);  // Debounce delay
  } else {
    knockDetected = false;
    Serial.println("Knock Not Detected!");
    delay(1000);
  }
}

void blink() {
  knockDetected = true;
}
```