## **Sample Code**
```c
#define Sensor 2

void setup()
{
  pinMode(Sensor,INPUT);
  Serial.begin(9600);
}
void loop()
{
  byte state = digitalRead(Sensor);
  if(state == 1){
    Serial.println("Somebody is in this area!");
  }else if(state == 0){
    Serial.println("No one!");
    delay(500);
  }
}

```