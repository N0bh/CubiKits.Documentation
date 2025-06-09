# Active Buzzer Module using Lorfi-L

# Description

This is one of the simplest sound-generating modules available. It can be driven using a high or low signal, and varying the input frequency allows it to produce different tones.

Commonly found in everyday devices like computers, refrigerators, and phones, this module is highly versatile.

Despite its small size, it’s a powerful tool for creating engaging interactive projects. Give it a try — you'll be amazed by the unique electronic sounds it can produce!

# Specification

- Working voltage: 3.3-5v
- Interface type: digital
- Size: 30*20mm
- Weight: 4g

## Hardware Setup

#### Using directly Lorfi-L

You can find complete [Lorfi-L IO pinout here].

*MIGHT NEED TO ADD NOTES ON POWER REQUIREMENTS, PIN CONSIDERATIONS, ETC.*

#### Using Lorfi Interface board

You can find complete guide for [Lorfi Interface here].

*MIGHT NEED TO ADD NOTES ON POWER REQUIREMENTS, PIN CONSIDERATIONS, ETC.*

## Software Setup

Lorfi-L is based on RAK3172 LoRaWAN module. This must be added to Arduino IDE.

Here's the guide [how to add RAK3172 on your Arduino IDE].

Once RAK3172 is added, you can now select it from the board selection.

*ADD HERE IMAGE OF RAK3172 ON BOARD SELECTION IN ARDUINO IDE.*

If failing, test the UART connection by checking the version. Use `AT+VER=?` command with baud rate of 115200. In case of MCU brick, revive the RAK3172 by following this [guide from RAKwireless](https://learn.rakwireless.com/hc/en-us/articles/26687606549911-How-To-Guide-STM32CubeProgrammer-for-RAK-Modules).

## **Sample Code**
```c
#define buzzPin PB5  //Connect Buzzer to a Digital Pin

void setup() {
  pinMode(buzzPin, OUTPUT);
}
void loop() {
  digitalWrite(buzzPin, HIGH);
  delay(1000);
  digitalWrite(buzzPin, LOW);
  delay(1000);
}
```

## Expected Output

Once the code is succesfully uploaded you must see the following output or behavior.

*ADD HERE IMAGE OF SUCCESSFUL UPLOAD*

*ADD HERE IMAGE OF EXPECTED OUTPUT IN SERIAL IF ANY*

## FAQ
