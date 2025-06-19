## **Sample Code**
```c
#define sensor 2

void setup()
{
  pinMode(sensor, OUTPUT);
  Serial.begin(9600);
}
void loop()
{
  Serial.println(digitalRead(sensor)); 
  delay(500);
}
```