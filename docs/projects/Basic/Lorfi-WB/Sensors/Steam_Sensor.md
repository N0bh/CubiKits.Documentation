---
layout: project
---

# Steam Sensor using Lorfi-WB

# Description

The steam sensor is an analog sensor that can be used as a basic rain detector or liquid level switch. As the moisture level on its surface increases, the output voltage also rises.

**Note:** The connector components are not waterproof, so avoid immersing them in water.

# Specification

- Working Voltage: 3.3V or 5V
- Working Current: <20mA
- Range of Working Temperature: －10℃～＋70℃
- Interface Type: Analog Signal Output

## Hardware Setup

|     Sensor    |   Lorfi WB  |
|---------------|-------------|
| Signal        | A0          |
| VCC           | 5V          |
| GND           | GND         |

Connect the S pin of module to Analog A0 of the Lorfi board, connect the negative pin to GND port, positive pin to 5V port.

<p style="text-align: center;">
  <img src="\assets\Images\LORFI_Components\Lorfi-WB_Sensors\20.png" alt="Centered Image" width="900" />
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
int val;

void setup() {
  Serial.begin(9600);  //open serial port, and set baud rate at 9600bps
}
void loop() {
  int val;
  val = analogRead(Sensor);  //plug vapor sensor into analog port 0
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
