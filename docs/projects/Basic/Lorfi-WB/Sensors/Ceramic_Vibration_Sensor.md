---
layout: project
title: Ceramic Vibration Sensor using Lorfi-WB
---

# Description

This vibration sensor operates using a piezoelectric ceramic chip that detects analog vibrations. It works on the principle that vibrations applied to the piezoelectric material generate electrical signals through an energy conversion process. When the ceramic chip is vibrated, the sensor’s output terminal produces a corresponding electrical signal. It can be easily connected to an Arduino through a dedicated sensor shield, allowing the analog input to detect even subtle vibrations. This makes it ideal for interactive vibration-based projects, such as an electronic drum.

# Specification

- Supply Voltage: 3.3V to 5V
- Working Current：<1mA
- Working Temperature Range：－10℃～＋70℃
- Output Signal：analog signal

## Hardware Setup

|     Sensor    |   Lorfi WB  |
|---------------|-------------|
| Signal        | A0          |
| VCC           | 5V          |
| GND           | GND         |

Connect the S pin of module to Analog A0 of Lorfi Board, connect the negative pin to GND port, NC pin to 5V port.

<p style="text-align: center;">
  <img src="\assets\Images\LORFI_Components\Lorfi-WB_Sensors\2.png" alt="Centered Image" width="900" />
</p>

#### Using directly Lorfi-WB

You can find complete <a href="/docs/Hardware_Guide.html">Lorfi-WB IO pinout here</a>.

*MIGHT NEED TO ADD NOTES ON POWER REQUIREMENTS, PIN CONSIDERATIONS, ETC.*

#### Using Lorfi Interface board

You can find complete guide for <a href="/docs/Hardware_Guide.html">Lorfi Interface here</a>.

*MIGHT NEED TO ADD NOTES ON POWER REQUIREMENTS, PIN CONSIDERATIONS, ETC.*

## Software Setup

Lorfi-WB is built around the ESP32 chipset and supports both Wi-Fi and Bluetooth Low Energy (BLE). This must be added to Arduino IDE.

Here's the guide on <a href="/docs/Software_Guide.html">how to add ESP32 board on your Arduino IDE</a>.

Once ESP32 board is added, you can now select it from the board selection.

<p style="text-align: center;">
  <img src="\assets\Images\LORFI_Components\Software-Guide_Images\Software_Guide4.png" alt="Centered Image" width="900" />
</p>

## **Sample Code**
```c
#define Sensor 2

void setup() {
  Serial.begin(9600);  //Open the serial to set the baud rate as 9600bps
}
void loop() {
  int val = analogRead(Sensor);  //Connect the sensor to analog interface A0
  Serial.print("Vibration is ");
  Serial.println(val, DEC);  //Print the analog value read on serial port
  delay(100);
}
```

## Expected Output

Once the code is succesfully uploaded you must see the following output or behavior.

*ADD HERE IMAGE OF SUCCESSFUL UPLOAD*

*ADD HERE IMAGE OF EXPECTED OUTPUT IN SERIAL IF ANY*

## FAQ
