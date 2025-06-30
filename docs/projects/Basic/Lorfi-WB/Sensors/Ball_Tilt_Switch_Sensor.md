---
layout: project
---

# Digital Tilt Switch Sensor using Lorfi-WB

# Description

The tilt sensor functions as a digital tilt switch and can be used for basic tilt detection. It easily connects to an IO/Sensor shield, simplifying wiring. When paired with a dedicated sensor shield and an Arduino, it enables the creation of various fun and interactive projects.

# Specification

- Supply Voltage: 3.3V to 5V
- Interface: Digital
- Size: 30*20mm
- Weight: 3g

## Hardware Setup

|     Module    |   Lorfi WB  |
|---------------|-------------|
| Signal        | GPIO2       |
| VCC           | 5V          |
| GND           | GND         |

Connect the Signal pin of the sensor to the Digital Input GPIO2 on the Lorfi board, connect the GND pin to GND port, VCC pin to 5V port.

![Digital Tilt Switch Sensor](\assets\Images\LORFI_Components\Lorfi-WB_Sensors\1.png)

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

![Software Guide 4](\assets\Images\LORFI_Components\Software-Guide_Images\Software_Guide4.png)

## **Sample Code**
```c
#define Sensor 2

void setup() {
  pinMode(Sensor, INPUT);  // Set digital pin 3 to input mode
  Serial.begin(9600);
}
void loop() {
  if (digitalRead(Sensor) == HIGH)  //Read sensor value
  {
    Serial.println("Sensor is tilted");  // Print "Sensor is tilted" when the sensor is tilted
  } else {
    Serial.println("Sensor is stable");  // Print "Sensor is stable" when the sensor is not triggered
  }
  delay(100);
}
```

## Expected Output

Once the code is succesfully uploaded you must see the following output or behavior.

*ADD HERE IMAGE OF SUCCESSFUL UPLOAD*

*ADD HERE IMAGE OF EXPECTED OUTPUT IN SERIAL IF ANY*

## FAQ

