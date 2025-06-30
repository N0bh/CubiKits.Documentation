---
layout: project
---

# GUVA S12SD-3528 Ultraviolet Sensor using Lorfi-WB

# Description

The GUVA-S12SD ultraviolet sensor is designed to detect UV light. It is commonly used to measure the UV index in smart wearable devices like watches, smartphones, and other outdoor gadgets. Additionally, it can monitor UV light intensity and serve as a UV flame detector, especially in applications involving UV-based disinfection.

# Specification

- Supply Voltage: 3.3V to 5V
- Detection range: 20cm (4.8V) ~ 100cm (1V)
- Rang of Spectral Bandwidth: 760nm to 1100nm
- Operating temperature: -25℃to 85℃
- Interface: digital
- Size: 44*16.7mm
- Weight: 4g

## Hardware Setup

|     Module    |   Lorfi L   |
|---------------|-------------|
| Signal        | A0          |
| VCC           | 5V          |
| GND           | GND         |

Connect the Signal pin of the sensor to the Analog Signal on the Lorfi board, connect the GND pin to GND port, VCC pin to 5V port.

![Ultra Violet Sensor](\assets\Images\LORFI_Components\Lorfi-WB_Sensors\6.png)

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
#define Sensor 2

void setup() {
  Serial.begin(9600);  //Open the serial to set the baud rate as 9600bps
}
void loop() {
  int sensorValue = analogRead(Sensor);
  // print out the value you read:
  Serial.println(sensorValue);
  delay(1000);        // delay in between reads for stability
}
```

## Expected Output

Once the code is succesfully uploaded you must see the following output or behavior.

*ADD HERE IMAGE OF SUCCESSFUL UPLOAD*

*ADD HERE IMAGE OF EXPECTED OUTPUT IN SERIAL IF ANY*

## FAQ
