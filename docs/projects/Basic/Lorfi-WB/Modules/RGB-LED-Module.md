# RRG Led Module using Lorfi-WB

# Description

This is an RGB LED module that features three primary colors—red, green, and blue—each functioning as individual LEDs.

With proper programming, you can control each LED to turn on or off in sequence, or use PWM (pulse-width modulation) to blend the colors and create a variety of other colors.

# Specification

- Color: red, green and blue
- Brightness: High
- Voltage: 5V
- Input: digital level
- Size: 30 *20mm
- Weight: 3g

## Hardware Setup

|     Module    |   Lorfi WB  |
|---------------|-------------|
| RED           | GPIO13      |
| GREEN         | GPIO2       |
| BLUE          | GPI014      |
| VCC           | 5V          |
| GND           | GND         |

Connect the three signal pin (RED, GREEN, BLUE) of the sensors to the GPIO pins of the Lorfi board, negative pin to GND port, positive pin to 5V port.

![RGB LED Module](\assets\Images\LORFI Components\Lorfi-WB_Modules\11.png)

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

#### Sample Code
```c
#define RED 13   // used as digital input
#define GREEN 2  // used as digital input
#define BLUE 14  // used as digital input
int val;

void setup() {
  pinMode(RED, OUTPUT);
  pinMode(BLUE, OUTPUT);
  pinMode(GREEN, OUTPUT);
}
void loop() {
  for (val = 255; val > 0; val--) {
    analogWrite(11, val);
    analogWrite(10, 255 - val);
    analogWrite(9, 128 - val);
    delay(1);
  }
  for (val = 0; val < 255; val++) {
    analogWrite(11, val);
    analogWrite(10, 255 - val);
    analogWrite(9, 128 - val);
    delay(1);
  }
}
```

## Expected Output

Once the code is succesfully uploaded you must see the following output or behavior.

*ADD HERE IMAGE OF SUCCESSFUL UPLOAD*

*ADD HERE IMAGE OF EXPECTED OUTPUT IN SERIAL IF ANY*

## FAQ


