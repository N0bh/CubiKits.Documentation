# LM35 Temperature Sensor using Lorfi-W

# Description

The LM35 Linear Temperature Sensor is a semiconductor-based sensor designed to measure ambient air temperature. It operates within a range of 0°C to 100°C and has a sensitivity of 10mV per degree Celsius, with its output voltage directly proportional to the temperature. Widely used for temperature monitoring, the LM35 belongs to a broader category of sensors including thermocouples, platinum resistance, and thermal resistance types. While thermocouples are suitable for high-temperature applications, such as measuring up to 800°C, thermal and semiconductor sensors like the LM35 are ideal for temperatures below 200°C due to their simplicity, good linearity, and high sensitivity.

# Specification

- Sensitivity: 10mV per degree Celsius
- Functional range: 0 degree Celsius to 100 degree Celsius
- Size: 30*20mm
- Weight: 3g

## Hardware Setup

Connect the signal pin of sensor to A0 port of the Lorfi board, negative pin to GND port, positive pin to 5V port.

![LM35 Temperature Sensor](\assets\Images\LORFI Components\Lorfi-L_Sensors\13.png)

#### Using directly Lorfi-L

You can find complete [Lorfi-L IO pinout here].

*MIGHT NEED TO ADD NOTES ON POWER REQUIREMENTS, PIN CONSIDERATIONS, ETC.*

#### Using Lorfi Interface board

You can find complete guide for [Lorfi Interface here].

*MIGHT NEED TO ADD NOTES ON POWER REQUIREMENTS, PIN CONSIDERATIONS, ETC.*

## Software Setup

Lorfi-L is based on RAK3172 LoRaWAN module. This must be added to Arduino IDE.

Here's the guide [how to add RAK3172 on your Arduino IDE].

Once RAK3172 is added, you can now select it from the board selection.

*ADD HERE IMAGE OF RAK3172 ON BOARD SELECTION IN ARDUINO IDE.*

If failing, test the UART connection by checking the version. Use `AT+VER=?` command with baud rate of 115200. In case of MCU brick, revive the RAK3172 by following this [guide from RAKwireless](https://learn.rakwireless.com/hc/en-us/articles/26687606549911-How-To-Guide-STM32CubeProgrammer-for-RAK-Modules).

## **Sample Code**
```c
#define Sensor PB5
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

## Expected Output

Once the code is succesfully uploaded you must see the following output or behavior.

*ADD HERE IMAGE OF SUCCESSFUL UPLOAD*

*ADD HERE IMAGE OF EXPECTED OUTPUT IN SERIAL IF ANY*

## FAQ
