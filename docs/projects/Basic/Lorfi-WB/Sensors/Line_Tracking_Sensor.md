# Line Tracking Sensor using Lorfi-WB

# Description

This Line Tracking Sensor is capable of detecting black lines on a white background or white lines on a black background. It outputs a stable TTL signal for precise and reliable line detection. For multi-line tracking, additional sensors can be installed to expand functionality as needed.

# Specification

- Power supply: +5V
- Operating current: <10mA
- Operating temperature range: 0°C ~ + 50°C
- Output interface: 3-wire interface (1 - signal, 2 - power, 3 - power supply negative)
- Output Level: TTL level

## Hardware Setup

|     Module    |   Lorfi WB  |
|---------------|-------------|
| Signal        | GPIO2       |
| VCC           | 5V          |
| GND           | GND         |

Connect the Signal pin of the sensor to the Digital Input GPIO2 on the Lorfi board, connect the GND pin to GND port, VCC pin to 5V port.

![Line Tracking Sensor](\assets\Images\LORFI_Components\Lorfi-WB_Sensors\10.png)

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
#define sensor 2

void setup()
{
  pinMode(sensor, OUTPUT);
  Serial.begin(9600);
}
void loop()
{
  Serial.println(digitalRead(sensor)); 
  delay(500);
}
```

## Expected Output

Once the code is succesfully uploaded you must see the following output or behavior.

*ADD HERE IMAGE OF SUCCESSFUL UPLOAD*

*ADD HERE IMAGE OF EXPECTED OUTPUT IN SERIAL IF ANY*

## FAQ
