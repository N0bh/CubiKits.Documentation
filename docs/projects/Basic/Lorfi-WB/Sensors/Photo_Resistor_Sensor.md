---
layout: project
---

# Photo Resistor Sensor using Lorfi-WB

# Description

Photocells, often found in everyday applications, are primarily used in smart switches and general electronic designs. To enhance usability and efficiency, ready-to-use modules are available. As semiconductor devices, photocells offer high sensitivity, fast response, consistent spectral characteristics, and stable R-values. They maintain strong performance even in harsh conditions like high temperature and humidity. Common applications include automatic control systems in devices such as cameras, solar garden lights, lawn lamps, currency detectors, clocks, novelty items, night lights, and sound/light-activated switches.

# Specification

- Interface type: Analog
- Working voltage: 5V
- Size: 30*20mm
- Weight: 3g

## Hardware Setup

|     Module    |   Lorfi WB  |
|---------------|-------------|
| Signal        | AO          |
| VCC           | 5V          |
| GND           | GND         |

Connect the S pin of module to Analog A0 of the Lorfi board, connect the negative pin to GND port, positive pin to 5V port.

![Photo Resistor Sensor](\assets\Images\LORFI_Components\Lorfi-WB_Sensors\16.png)

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
///Arduino Sample Code
#define Sensor A0
int val;

void setup() {
  Serial.begin(9600);  //open serial port, and set baud rate at 9600bps
}
void loop() {
  int val = analogRead(Sensor);  //plug vapor sensor into analog port 0
  Serial.print("Moisture is ");
  Serial.println(val, DEC);  //read analog value through serial port printed
  delay(100);
}

```

## Expected Output

Once the code is succesfully uploaded you must see the following output or behavior.

*ADD HERE IMAGE OF SUCCESSFUL UPLOAD*

*ADD HERE IMAGE OF EXPECTED OUTPUT IN SERIAL IF ANY*

## FAQ
