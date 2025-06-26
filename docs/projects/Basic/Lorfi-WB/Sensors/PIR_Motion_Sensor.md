# PIR Motion Sensor using Lorfi-WB

# Description

The pyroelectric infrared motion sensor detects infrared radiation emitted by moving people or animals and produces a corresponding switch signal. It's suitable for various applications involving human motion detection. Traditional pyroelectric infrared sensors typically rely on a separate infrared detector, dedicated chip, and complex circuitry, resulting in larger size, more complicated design, and reduced reliability.

This updated version, designed specifically for Arduino, features an all-in-one digital pyroelectric infrared sensor. It offers a more compact form factor, improved reliability, lower power consumption, and a simplified circuit, making it easier to integrate into projects.

# Specification

- Input Voltage: 3.3 ~ 5V, Maximum for 6V
- Working Current: 15uA
- Working Temperature: -20 ~ 85 ℃
- Output Voltage: High 3V, Low 0V
- Output Delay Time (High Level): About 2.3 to 3 Seconds
- Detection Angle: 100 °
- Detection Distance: 7 meters
- Output Indicator LED (if output HIGH, it will be ON)
- Limit Current for Pin: 100mA
- Size: 30*20mm
- Weight: 4g

## Hardware Setup

|     Module    |   Lorfi WB  |
|---------------|-------------|
| Signal        | GPIO2       |
| VCC           | 5V          |
| GND           | GND         |

Connect the Signal pin of the sensor to the Digital Input GPIO2 on the Lorfi board, connect the GND pin to GND port, VCC pin to 5V port.

![PIR Motion Sensor](\assets\Images\LORFI Components\Lorfi-WB_Sensors\17.png)

#### Using directly Lorfi-WB

You can find complete <a href="/docs/Hardware-Guide.html">Lorfi-WB IO pinout here</a>.

#### Using Lorfi Interface board

You can find complete guide for <a href="/docs/Hardware-Guide.html">Lorfi Interface here</a>.

## Software Setup

Lorfi-WB is built around the ESP32 chipset and supports both Wi-Fi and Bluetooth Low Energy (BLE). This must be added to Arduino IDE.

Here's the guide on <a href="/docs/Software-Guide.html">how to add ESP32 board on your Arduino IDE</a>.

Once ESP32 board is added, you can now select it from the board selection.

![Software Guide 4](\assets\Images\LORFI Components\Software-Guide_Images\Software_Guide4.png)

## **Sample Code**
```c
#define Sensor 2

void setup()
{
  pinMode(Sensor,INPUT);
  Serial.begin(9600);
}
void loop()
{
  byte state = digitalRead(Sensor);
  if(state == 1){
    Serial.println("Somebody is in this area!");
  }else if(state == 0){
    Serial.println("No one!");
    delay(500);
  }
}

```

## Expected Output

Once the code is succesfully uploaded you must see the following output or behavior.

*ADD HERE IMAGE OF SUCCESSFUL UPLOAD*

*ADD HERE IMAGE OF EXPECTED OUTPUT IN SERIAL IF ANY*

## FAQ
