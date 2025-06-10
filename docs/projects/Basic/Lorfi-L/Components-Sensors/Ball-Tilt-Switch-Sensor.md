# Digital Tilt Switch Sensor using Lorfi-W

# Description

The tilt sensor functions as a digital tilt switch and can be used for basic tilt detection. It easily connects to an IO/Sensor shield, simplifying wiring. When paired with a dedicated sensor shield and an Arduino, it enables the creation of various fun and interactive projects.

# Specification

- Supply Voltage: 3.3V to 5V
- Interface: Digital
- Size: 30*20mm
- Weight: 3g

## Hardware Setup

Connect the S pin of module to digital input of the Lorfi Board, connect the negative pin to GND port, positive pin to 5V port.

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
#define Sensor PB5

void setup() {
  pinMode(Sensor, INPUT);  // Set digital pin 3 to input mode
  Serial.begin(9600);
}
void loop() {
  if (digitalRead(Sensor) == HIGH)  //Read sensor value
  {
    Serial.println("Sensor is tilted");  // Print "Sensor is tilted" when the sensor is tilted
  } else {
    Serial.println("Sensor is stable");  // Print "Sensor is stable" when the sensor is not triggered
  }
  delay(100);
}
```

## Expected Output

Once the code is succesfully uploaded you must see the following output or behavior.

*ADD HERE IMAGE OF SUCCESSFUL UPLOAD*

*ADD HERE IMAGE OF EXPECTED OUTPUT IN SERIAL IF ANY*

## FAQ
