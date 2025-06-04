## **Sample Code**
```c
#define sensor PB5

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