---
layout: project
title: MQ2 Gas Sensor using Lorfi-L
---

# Description

The MQ2 analog gas sensor is commonly used in gas leak detection systems for both consumer and industrial applications. It is capable of sensing a wide range of gases, including LPG, isobutane, propane, methane, alcohol, hydrogen, and smoke. The sensor features a broad detection range, high sensitivity, and fast response time. Additionally, its sensitivity can be fine-tuned using the built-in potentiometer.

# Specification

- Power supply: 5V
- Interface type: Analog
- Simple drive circuit
- Stable and long lifespan

## Hardware Setup

|     Sensor    |   Lorfi L   |
|---------------|-------------|
| Signal        | PB3          |
| VCC           | 5V          |
| GND           | GND         |

Connect the A0 pin of module to Analog Signal of the Lorfi board, connect the GND pin to GND port, VCC pin to 5V port.

<p style="text-align: center;">
  <img src="\assets\Images\LORFI_Components\Lorfi-L_Sensors\15.png" alt="Centered Image" width="900" />
</p>

#### Using directly Lorfi-L

You can find complete <a href="/docs/Hardware_Guide.html">Lorfi-L IO pinout here</a>.

*MIGHT NEED TO ADD NOTES ON POWER REQUIREMENTS, PIN CONSIDERATIONS, ETC.*

#### Using Lorfi Interface board

You can find complete guide for <a href="/docs/Hardware_Guide.html">Lorfi Interface here</a>.

*MIGHT NEED TO ADD NOTES ON POWER REQUIREMENTS, PIN CONSIDERATIONS, ETC.*

## Software Setup

Lorfi-L is based on RAK3172 LoRaWAN module. This must be added to Arduino IDE.

Here's the guide on <a href="/docs/Software_Guide.html">how to add RAK3172 on your Arduino IDE</a>.

Once RAK3172 is added, you can now select it from the board selection.

<p style="text-align: center;">
  <img src="\assets\Images\LORFI_Components\Software-Guide_Images\Software_Guide4.png" alt="Centered Image" width="900" />
</p>

If failing, test the UART connection by checking the version. Use `AT+VER=?` command with baud rate of 115200. In case of MCU brick, revive the RAK3172 by following this [guide from RAKwireless](https://learn.rakwireless.com/hc/en-us/articles/26687606549911-How-To-Guide-STM32CubeProgrammer-for-RAK-Modules).

## Sample Code:
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
