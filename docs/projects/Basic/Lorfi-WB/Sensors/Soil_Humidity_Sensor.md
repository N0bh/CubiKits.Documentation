---
layout: project
title: Soil Moisture Sensor using Lorfi-WB
---

# Description

This soil moisture sensor is designed to measure the humidity level in soil. When the soil is dry, the sensor's analog output decreases; when the soil is moist, the output increases. It's ideal for creating an automatic watering system that can detect when your plant needs water, helping prevent it from drying out while you're away.

When paired with an Arduino, this sensor can make plant care smarter and more efficient. It features two probes that are inserted into the soil. By measuring the change in current between the probes, it determines the soil's resistance and converts it into a moisture level. Higher moisture means lower resistance and better conductivity. The sensor's surface is metal-coated to enhance durability. Simply insert it into the soil and use an ADC to read the values—your plant can now "tell" you when it's thirsty.

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

<p style="text-align: center;">
  <img src="\assets\Images\LORFI_Components\Lorfi-WB_Sensors\19.png" alt="Centered Image" width="900" />
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
