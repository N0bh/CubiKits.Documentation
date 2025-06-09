## **Sample Code**
```c
#define Sensor A0
void setup()
{
  Serial.begin(9600);
  pinMode(Sensor,INPUT);

}

void loop() 
{
  Serial.println(analogRead(Sensor));
  delay(500);
}
```