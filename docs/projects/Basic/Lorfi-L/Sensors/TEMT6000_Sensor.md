---
layout: project
---

# Ambient Light Sensor using Lorfi-L

# Description

Eventually, you may need to measure ambient light with greater accuracy than a basic photoresistor can provide—without adding much complexity to your setup. When that time comes, the TEMT6000 ambient light sensor is a great option.

Designed to match the sensitivity of the human eye, the TEMT6000 performs best across a wide range of brightness levels, responding well to even small changes. However, it tends to underperform in low-light environments. Since it’s calibrated to human vision, it’s not responsive to infrared or ultraviolet light—something to keep in mind when planning your project.

# Specification

- Supply Voltage: +5VDC 50mA
- Size: 36.5*16mm
- Weight: 4g

## Hardware Setup

|     Module    |   Lorfi L   |
|---------------|-------------|
| Signal        | PB5         |
| VCC           | 5V          |
| GND           | GND         |

Connect the Signal pin of the sensor to the Digital Input PB5 on the Lorfi board, connect the GND pin to GND port, VCC pin to 5V port.

![Ambient Light Sensor](\assets\Images\LORFI_Components\Lorfi-L_Sensors\21.png)

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

![Software Guide 4](\assets\Images\LORFI_Components\Software-Guide_Images\Software_Guide4.png)

If failing, test the UART connection by checking the version. Use `AT+VER=?` command with baud rate of 115200. In case of MCU brick, revive the RAK3172 by following this [guide from RAKwireless](https://learn.rakwireless.com/hc/en-us/articles/26687606549911-How-To-Guide-STM32CubeProgrammer-for-RAK-Modules).

## **Sample Code**
```c
///Arduino Sample Code
#define Sensor PB5

void setup() {
  Serial.begin(9600);
}
void loop() {
  int value = analogRead(temt6000Pin);
  Serial.println(value);
  delay(100); //only here to slow down the output so it is easier to read
}
```

## Expected Output

Once the code is succesfully uploaded you must see the following output or behavior.

*ADD HERE IMAGE OF SUCCESSFUL UPLOAD*

*ADD HERE IMAGE OF EXPECTED OUTPUT IN SERIAL IF ANY*

## FAQ