## **Sample Code**
```c
#define Sensor PB5
byte indicator = 13;

void setup()
{
  pinMode(Sensor,INPUT);
  pinMode(indicator,OUTPUT);
  Serial.begin(9600);
}
void loop()
{
  byte state = digitalRead(Sensor);
  digitalWrite(indicator,state);
  if(state == 1){
    Serial.println("Somebody is in this area!");
  }else if(state == 0){
    Serial.println("No one!");
    delay(500);
  }
}

```