---
layout: project
---

# Microphone Sound Sensor using Lorfi-WB

# Description

The analog sound sensor is mainly used to detect the intensity of surrounding sounds. It features a built-in potentiometer, allowing you to adjust the signal gain as needed. This sensor is great for creating interactive projects, such as a voice-activated switch.

# Specification

- Supply Voltage: 3.3V to 5V
- Interface: Analog
- Size: 30*20mm
- Weight: 4g

## Hardware Setup

|     Sensor    |   Lorfi WB  |
|---------------|-------------|
| Signal        | A0          |
| VCC           | 5V          |
| GND           | GND         |


Connect the S pin of module to Analog A0 of the Lorfi board, connect the negative pin to GND port, positive pin to 5V port.

<p style="text-align: center;">
  <img src="\assets\Images\LORFI_Components\Lorfi-WB_Sensors\12.png" alt="Centered Image" width="900" />
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
#define Sensor A0
  int value = 0;  // variable for reading the sensor status

void setup() {
  Serial.begin(9600);
}
void loop() {
  value = analogRead(Sensor);
  Serial.println(value, DEC);
  delay(1000);
}
```

## Expected Output

Once the code is succesfully uploaded you must see the following output or behavior.

*ADD HERE IMAGE OF SUCCESSFUL UPLOAD*

*ADD HERE IMAGE OF EXPECTED OUTPUT IN SERIAL IF ANY*

## FAQ
