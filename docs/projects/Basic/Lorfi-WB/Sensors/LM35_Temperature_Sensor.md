---
layout: project
---

# LM35 Temperature Sensor using Lorfi-WB

# Description

The LM35 Linear Temperature Sensor is a semiconductor-based sensor designed to measure ambient air temperature. It operates within a range of 0°C to 100°C and has a sensitivity of 10mV per degree Celsius, with its output voltage directly proportional to the temperature. Widely used for temperature monitoring, the LM35 belongs to a broader category of sensors including thermocouples, platinum resistance, and thermal resistance types. While thermocouples are suitable for high-temperature applications, such as measuring up to 800°C, thermal and semiconductor sensors like the LM35 are ideal for temperatures below 200°C due to their simplicity, good linearity, and high sensitivity.

# Specification

- Sensitivity: 10mV per degree Celsius
- Functional range: 0 degree Celsius to 100 degree Celsius
- Size: 30*20mm
- Weight: 3g

## Hardware Setup

|     Module    |   Lorfi WB  |
|---------------|-------------|
| Signal        | A0          |
| VCC           | 5V          |
| GND           | GND         |

Connect the Signal pin of the sensor to the Analog Signal on the Lorfi board, connect the GND pin to GND port, VCC pin to 5V port.

![LM35 Temperature Sensor](\assets\Images\LORFI_Components\Lorfi-WB_Sensors\11.png)

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
#define Sensor A0
int val;
int dat;

void setup() {
  Serial.begin(9600);  //Set Baud Rate to 9600 bps
}
void loop() {
  val = analogRead(Sensor);  //Connect LM35 on Analog 0
  dat = (500 * val) / 1024;
  Serial.print("Temp:");  //Display the temperature on Serial monitor
  Serial.print(dat);
  Serial.println("C");
  delay(500);
}
```

## Expected Output

Once the code is succesfully uploaded you must see the following output or behavior.

*ADD HERE IMAGE OF SUCCESSFUL UPLOAD*

*ADD HERE IMAGE OF EXPECTED OUTPUT IN SERIAL IF ANY*

## FAQ
