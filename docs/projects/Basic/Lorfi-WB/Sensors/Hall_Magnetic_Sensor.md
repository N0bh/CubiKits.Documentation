---
layout: project
title: Hall Magnetic Sensor using Lorfi-WB
---

# Description

This magnetic induction sensor detects magnetic materials within a range of up to 3 cm. The detection distance increases proportionally with the strength of the magnetic field. It provides a digital on/off output signal and utilizes the SFE Reed Switch – Magnetic Field Sensor for its operation.

# Specification

- Sensing magnetic materials
- Detection range: up to 3cm
- Output: digital on/off
- Size: 30*20mm
- Weight: 3g

## Hardware Setup

|     Module    |   Lorfi WB  |
|---------------|-------------|
| Signal        | GPIO2       |
| VCC           | 5V          |
| GND           | GND         |

Connect the Signal pin of the sensor to the Digital Input GPIO2 on the Lorfi board, connect the GND pin to GND port, VCC pin to 5V port.

<p style="text-align: center;">
  <img src="\assets\Images\LORFI_Components\Lorfi-WB_Sensors\7.png" alt="Centered Image" width="900" />
</p>

#### Using directly Lorfi-WB

You can find complete <a href="/docs/Hardware_Guide.html">Lorfi-WB IO pinout here</a>.

#### Using Lorfi Interface board

You can find complete guide for <a href="/docs/Hardware_Guide.html">Lorfi Interface here</a>.

## Software Setup

Lorfi-WB is built around the ESP32 chipset and supports both Wi-Fi and Bluetooth Low Energy (BLE). This must be added to Arduino IDE.

Here's the guide on <a href="/docs/Software_Guide.html">how to add ESP32 board on your Arduino IDE</a>.

Once ESP32 board is added, you can now select it from the board selection.

<p style="text-align: center;">
  <img src="\assets\Images\LORFI_Components\Software-Guide_Images\Software_Guide4.png" alt="Centered Image" width="900" />
</p>

## Sample Code

```c
#define Sensor 2
int val = 0;  // variable for reading the pin status

void setup() {
  pinMode(Sensor, INPUT);  // declare as input
  Serial.begin(9600);
}

void loop() {
  val = digitalRead(Sensor);  // read input value
  if (val == HIGH) {          // check if the input is HIGH
    Serial.println("Magnetic Signal Detected!");
  } else {
    Serial.println("No Magnetic Signal Detected!");
  }
  delay(500);
}
```

## Expected Output

Once the code is succesfully uploaded you must see the following output or behavior.

*ADD HERE IMAGE OF SUCCESSFUL UPLOAD*

*ADD HERE IMAGE OF EXPECTED OUTPUT IN SERIAL IF ANY*

## FAQ

