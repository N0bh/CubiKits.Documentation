# Digital IR Receiver using Lorfi-WB

# Description

Infrared (IR) technology is commonly used in remote controls. With this IR receiver, your Arduino project can accept signals from most IR remotes, provided the correct decoding method is used. You can also easily create your own IR controller using an IR transmitter.

# Specification

- Power Supply: 5V
- Interface: Digital
- Modulation Frequency: 38Khz
- Module Interface Socket: JST PH2.0
- Size: 30*20mm
- Weight: 4g

## Hardware Setup 

|     Module    |   Lorfi WB  |
|---------------|-------------|
| Signal        | GPIO2       |
| VCC           | 5V          |
| GND           | GND         |

Connect the Signal pin of sensor to Digital Input of the Lorfi board, negative pin to GND port, positive pin to 5V port.

![IR Receiver Module](\assets\Images\LORFI_Components\Lorfi-WB_Modules\6.png)

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

## **Sample Code 1: Simple Approach**
```c
## **Sample Code**
```c
#define Sensor 2

void setup() {
  pinMode(Sensor, OUTPUT);
}
void loop() {
  digitalWrite(Sensor, HIGH);

  delay(1000);
  digitalWrite(Sensor, LOW);
  delay(1000);
}
```

## **Sample Code**
```c
#include <IRremote.h>
IRsend irsend;
void setup() {}
void loop() {
  irsend.sendRC5(0x0, 8);  //send 0x0 code (8 bits)
  delay(200);
  irsend.sendRC5(0x1, 8);
  delay(200);
}
```

## Expected Output

Once the code is succesfully uploaded you must see the following output or behavior.

*ADD HERE IMAGE OF SUCCESSFUL UPLOAD*

*ADD HERE IMAGE OF EXPECTED OUTPUT IN SERIAL IF ANY*

## FAQ

