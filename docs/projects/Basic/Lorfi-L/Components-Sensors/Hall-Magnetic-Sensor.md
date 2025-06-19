# Hall Magnetic Sensor using Lorfi-W

# Description

This magnetic induction sensor detects magnetic materials within a range of up to 3 cm. The detection distance increases proportionally with the strength of the magnetic field. It provides a digital on/off output signal and utilizes the SFE Reed Switch – Magnetic Field Sensor for its operation.

# Specification

- Sensing magnetic materials
- Detection range: up to 3cm
- Output: digital on/off
- Size: 30*20mm
- Weight: 3g

## Hardware Setup

Connect the S pin of module to Digital Input of the Lorfi board, connect the negative pin to GND port, positive pin to 5V port.

![Hall Magnetic Sensor](\assets\Images\LORFI Components\Lorfi-L_Sensors\9.png)

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
int val = 0;  // variable for reading the pin status

void setup() {
  pinMode(Sensor, INPUT);  // declare as input
  Serial.begin(9600);
}

void loop() {
  val = digitalRead(Sensor);  // read input value
  if (val == HIGH) {          // check if the input is HIGH
    Serial.println("Magnetic Signal Detected!");
  } else {
    Serial.println("No Magnetic Signal Detected!");
  }
  delay(500);
}
```

## Expected Output

Once the code is succesfully uploaded you must see the following output or behavior.

*ADD HERE IMAGE OF SUCCESSFUL UPLOAD*

*ADD HERE IMAGE OF EXPECTED OUTPUT IN SERIAL IF ANY*

## FAQ
