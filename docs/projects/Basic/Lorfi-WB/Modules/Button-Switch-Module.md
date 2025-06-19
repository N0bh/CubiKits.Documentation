## **Sample Code**
```c
#define LED 2

void setup()
{
  pinMode(LED, OUTPUT);     //Set Pin7 as output
}
void loop()
{    digitalWrite(LED, HIGH);   //Turn off led
     delay(1000);
     digitalWrite(LED, LOW);    //Turn on led
     delay(1000);
}
```
