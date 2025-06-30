---
layout: project
---

# Infrared Obstacle Avoidance using Lorfi-WB

# Description

The infrared obstacle sensor is designed for wheeled robots, with adjustable detection range (2–40 cm) and strong resistance to ambient light. It uses infrared reflection to detect objects and outputs a digital signal when an obstacle is sensed. Compatible with 3.3V–5V systems, it's ideal for Arduino and other microcontrollers.

# Specification

- Working voltage: DC 3.3V-5V
- Working current: ≥20mA
- Working temperature: －10℃ to＋50℃
- Detection distance: 2-40cm
- IO Interface: 4 wire interfaces (-/+/S/EN)
- Output signal: TTL voltage
- Accommodation mode: Multi-circle resistance regulation
- Effective Angle: 35°

## Hardware Setup

|     Module    |   Lorfi WB  |
|---------------|-------------|
| Signal        | GPIO2       |
| VCC           | 5V          |
| GND           | GND         |

Connect the Signal pin of the sensor to the Digital Input GPIO2 on the Lorfi board, connect the GND pin to GND port, VCC pin to 5V port.

<p style="text-align: center;">
  <img src="\assets\Images\LORFI_Components\Lorfi-WB_Sensors\15.png" alt="Centered Image" width="900" />
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
#define sensorPin A0    // the number of the sensor pin
int sensorState = 0;         // variable for reading the sensor status
void setup() {    
  pinMode(sensorPin, INPUT); }
void loop(){
  // read the state of the sensor value:
  sensorState = digitalRead(sensorPin);
  // if it is, the sensorState is HIGH:
  if (sensorState == HIGH) {     
     Serial.print("Object Detected!");  
  } 
  else {
     Serial.print("Object not Detected!");
  }
}
```

## Expected Output

Once the code is succesfully uploaded you must see the following output or behavior.

*ADD HERE IMAGE OF SUCCESSFUL UPLOAD*

*ADD HERE IMAGE OF EXPECTED OUTPUT IN SERIAL IF ANY*

## FAQ

