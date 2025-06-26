# Digital Push Button Module using Lorfi-WB

# Description

This is a simple push-button module that's perfect for getting started with Arduino. Just plug it into an I/O shield to begin experimenting.


# Specification

- Supply Voltage: 3.3V to 5V
- Interface: Digital
- Dimensions: 30*20mm
- Weight: 4g
- Wide voltage range from 3.3V to 5V
- Easily recognizable interfaces of sensors (“A” for Analog and “D” for Digital)
- Standard assembled hole
- Clear icons illustration
- High quality connector
- Easy to plug and operate
- Large button and high-quality cap
- To achieve interesting and interactive works

## Hardware Setup 

|     Module    |   Lorfi WB  |
|---------------|-------------|
| Signal        | GPIO2       |
| VCC           | 5V          |
| GND           | GND         |

Connect the Signal pin of sensor to Digital Input of the Lorfi board, negative pin to GND port, positive pin to 5V port.

![Digital Push Button Module](\assets\Images\LORFI Components\Lorfi-WB_Modules\4.png)

#### Using directly Lorfi-WB

You can find complete <a href="/docs/Hardware-Guide.html">Lorfi-WB IO pinout here</a>.

*MIGHT NEED TO ADD NOTES ON POWER REQUIREMENTS, PIN CONSIDERATIONS, ETC.*

#### Using Lorfi Interface board

You can find complete guide for <a href="/docs/Hardware-Guide.html">Lorfi Interface here</a>.

*MIGHT NEED TO ADD NOTES ON POWER REQUIREMENTS, PIN CONSIDERATIONS, ETC.*

## Software Setup

Lorfi-WB is built around the ESP32 chipset and supports both Wi-Fi and Bluetooth Low Energy (BLE). This must be added to Arduino IDE.

Here's the guide on <a href="/docs/Software-Guide.html">how to add ESP32 board on your Arduino IDE</a>.

Once ESP32 board is added, you can now select it from the board selection.

![Software Guide 4](\assets\Images\LORFI Components\Software-Guide_Images\Software_Guide4.png)

## **Sample Code**
```c
#define LED 2

void setup()
{
  pinMode(LED, OUTPUT); 
}
void loop()
{    digitalWrite(LED, HIGH);   //Turn off led
     delay(1000);
     digitalWrite(LED, LOW);    //Turn on led
     delay(1000);
}
```

## Expected Output

Once the code is succesfully uploaded you must see the following output or behavior.

*ADD HERE IMAGE OF SUCCESSFUL UPLOAD*

*ADD HERE IMAGE OF EXPECTED OUTPUT IN SERIAL IF ANY*

## FAQ


