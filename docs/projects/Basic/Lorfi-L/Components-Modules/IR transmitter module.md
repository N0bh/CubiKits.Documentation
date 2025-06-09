## **Sample Code**
```c
#define led PB5
void setup() {                
   pinMode(led, OUTPUT);     
}
void loop() {
  digitalWrite(led, HIGH);  

  delay(1000);               
  digitalWrite(led, LOW);   
  delay(1000); }
```

## **Sample Code**
```c
#include <IRremote.h>
 #define RECV_PIN PB5
 IRrecv irrecv(RECV_PIN);
 decode_results results;
 void setup()
{
  Serial.begin(9600);
  irrecv.enableIRIn(); // Start the receiver
}
 void loop() {
  if (irrecv.decode(&results)) {
    Serial.println(results.value, HEX);
    irrecv.resume(); // Receive the next value
  }
}
```