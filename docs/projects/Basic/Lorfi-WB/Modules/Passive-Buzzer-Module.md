# Passive Buzzer Module using Lorfi-WB

# Description

The buzzer used in this project is a passive buzzer. It doesn't generate sound on its own but requires external pulse signals to operate. Varying the frequency of these pulses produces different tones. With an Arduino, you can easily program melodies, making it a fun and straightforward way to create music.

# Specification

- Working voltage: 3.3-5v
- Interface type: digital
- Size: 30*20mm
- Weight: 4g

## Hardware Setup

|     Module    |   Lorfi WB  |
|---------------|-------------|
| Signal        | GPIO2       |
| VCC           | 5V          |
| GND           | GND         |

Connect the Signal pin of sensor to Digital Input of the Lorfi board, negative pin to GND port, positive pin to 5V port.

![Passive Buzzer Module](\assets\Images\LORFI Components\Lorfi-WB_Modules\8.png)

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
int buzzer = 2;  //set digital IO pin of the buzzer
void setup() {
  pinMode(buzzer, OUTPUT);  // set digital IO pin pattern, OUTPUT to be output
}
void loop() {
  unsigned char i, j;  //define variable
  while (1) {
    for (i = 0; i < 80; i++)  // output a frequency sound
    {
      digitalWrite(buzzer, HIGH);  // sound
      delay(1);                    //delay1ms
      digitalWrite(buzzer, LOW);   //not sound
      delay(1);                    //ms delay
    }
    for (i = 0; i < 100; i++)  // output a frequency sound
    {
      digitalWrite(buzzer, HIGH);  // sound
      digitalWrite(buzzer, LOW);   //not sound
      delay(2);                    //2ms delay
    }
  }
}
```
## Expected Output

Once the code is succesfully uploaded you must see the following output or behavior.

*ADD HERE IMAGE OF SUCCESSFUL UPLOAD*

*ADD HERE IMAGE OF EXPECTED OUTPUT IN SERIAL IF ANY*

## FAQ
