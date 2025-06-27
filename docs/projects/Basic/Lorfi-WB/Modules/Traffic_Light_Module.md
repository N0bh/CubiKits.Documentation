# RRG Led Module using Lorfi-WB

# Description

The Traffic LED Module features built-in red, yellow, and green LEDs to simulate real traffic lights. It simplifies wiring and is perfect for learning microcontroller control and traffic light sequences.

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
| YELLOW        | GPIO14      |
| GREEN         | GPIO2       |
| VCC           | 5V          |
| GND           | GND         |

Connect the three signal pin (RED, YELLOW, GREEN) of the sensors to the GPIO pins of the Lorfi board, negative pin to GND port, positive pin to 5V port.

![Traffic Light Module](\assets\Images\LORFI_Components\Lorfi-WB_Modules\13.png)

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

### Sample Code
```c
int redled = 13;     // initialize digital pin 5.
int yellowled = 14;  // initialize digital pin 4.
int greenled = 2;   // initialize digital pin 3.

void setup() {
  pinMode(redled, OUTPUT);     // set the pin with red LED as “output”
  pinMode(yellowled, OUTPUT);  // set the pin with yellow LED as “output”
  pinMode(greenled, OUTPUT);   // set the pin with green LED as “output”
}
void loop() {
  digitalWrite(greenled, HIGH);  //// turn on green LED
  delay(5000);                   // wait 5 seconds
  digitalWrite(greenled, LOW);   // turn off green LED
  for (int i = 0; i < 3; i++)    // blinks for 3 times
  {
    delay(500);                     // wait 0.5 seconds
    digitalWrite(yellowled, HIGH);  // turn on yellow LED
    delay(500);                     // wait 0.5 seconds
    digitalWrite(yellowled, LOW);   // turn off yellow LED
  }
  delay(500);                  // wait 0.5 seconds
  digitalWrite(redled, HIGH);  // turn on red LED
  delay(5000);                 // wait 5 seconds
  digitalWrite(redled, LOW);   // turn off red LED
}
```

## Expected Output

Once the code is succesfully uploaded you must see the following output or behavior.

*ADD HERE IMAGE OF SUCCESSFUL UPLOAD*

*ADD HERE IMAGE OF EXPECTED OUTPUT IN SERIAL IF ANY*

## FAQ
