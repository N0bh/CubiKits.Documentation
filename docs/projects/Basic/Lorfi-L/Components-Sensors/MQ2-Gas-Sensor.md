# MQ2 Gas Sensor using Lorfi-W

# Description

The MQ2 analog gas sensor is commonly used in gas leak detection systems for both consumer and industrial applications. It is capable of sensing a wide range of gases, including LPG, isobutane, propane, methane, alcohol, hydrogen, and smoke. The sensor features a broad detection range, high sensitivity, and fast response time. Additionally, its sensitivity can be fine-tuned using the built-in potentiometer.

# Specification

- Power supply: 5V
- Interface type: Analog
- Simple drive circuit
- Stable and long lifespan

## Hardware Setup

Connect the A0 pin of module to Analog A0 of the Lorfi board, connect the GND pin to GND port, VCC pin to 5V port.

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
#define Sensor PB3

void setup() {
  Serial.begin(9600);  //Set serial baud rate to 9600 bps
}
void loop() {
  int val = analogRead(Sensor);       //Read Gas value from analog 0
  Serial.println(val, DEC);  //Print the value to serial port
  delay(100);
}
```

## Expected Output

Once the code is succesfully uploaded you must see the following output or behavior.

*ADD HERE IMAGE OF SUCCESSFUL UPLOAD*

*ADD HERE IMAGE OF EXPECTED OUTPUT IN SERIAL IF ANY*

## FAQ
