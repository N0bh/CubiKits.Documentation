## **Sample Code**
```c
#define Sensor PB3
int val;
int dat;

void setup() {
  Serial.begin(9600);  //Set Baud Rate to 9600 bps
}
void loop() {
  val = analogRead(Sensor);  //Connect LM35 on Analog 0
  dat = (500 * val) / 1024;
  Serial.print("Temp:");  //Display the temperature on Serial monitor
  Serial.print(dat);
  Serial.println("C");
  delay(500);
}
```