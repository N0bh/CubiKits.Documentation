---
layout: project
---

# Analog Rotation Sensor using Lorfi-WB

# Description

This analog rotation sensor is compatible with Arduino and is built around a potentiometer. It provides a voltage output that can be divided into 1024 steps, making it easy to connect to an Arduino using a sensor shield. By reading the analog values through an IO port, it can be combined with other sensors to create a variety of interactive projects.

# Specification

- Supply Voltage: 3.3V to 5V
- Interface: Analog
- Size: 30*20mm
- Weight: 8g

## Hardware Setup

|     Sensor    |   Lorfi WB  |
|---------------|-------------|
| Signal        | A0          |
| VCC           | 5V          |
| GND           | GND         |

Connect the S pin of module to Analog A0 of the Lorfi board, connect the negative pin to GND port, positive pin to 5V port.

![Analog Rotation Sensor](\assets\Images\LORFI_Components\Lorfi-WB_Sensors\18.png)

#### Using directly Lorfi-WB

You can find complete <a href="/docs/Hardware_Guide.html">Lorfi-WB IO pinout here</a>.

#### Using Lorfi Interface board

You can find complete guide for <a href="/docs/Hardware_Guide.html">Lorfi Interface here</a>.

## Software Setup

Lorfi-WB is built around the ESP32 chipset and supports both Wi-Fi and Bluetooth Low Energy (BLE). This must be added to Arduino IDE.

Here's the guide on <a href="/docs/Software_Guide.html">how to add ESP32 board on your Arduino IDE</a>.

Once ESP32 board is added, you can now select it from the board selection.

![Software Guide 4](\assets\Images\LORFI_Components\Software-Guide_Images\Software_Guide4.png)

## **Sample Code**
```c
#define Sensor A0 //Connect sensor pin to Analog Input

void setup() {
  Serial.begin(115200);
  pinMode(Sensor, INPUT);
}

void loop() {

  Serial.print("Moisture Sensor Value:");
  Serial.println(Sensor);
  delay(100);
}
```

## Expected Output

Once the code is succesfully uploaded you must see the following output or behavior.

*ADD HERE IMAGE OF SUCCESSFUL UPLOAD*

*ADD HERE IMAGE OF EXPECTED OUTPUT IN SERIAL IF ANY*

## FAQ
