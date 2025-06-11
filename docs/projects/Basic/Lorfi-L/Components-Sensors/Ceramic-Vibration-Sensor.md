# Ceramic Vibration Sensor using Lorfi-W

# Description

This vibration sensor operates using a piezoelectric ceramic chip that detects analog vibrations. It works on the principle that vibrations applied to the piezoelectric material generate electrical signals through an energy conversion process. When the ceramic chip is vibrated, the sensor’s output terminal produces a corresponding electrical signal. It can be easily connected to an Arduino through a dedicated sensor shield, allowing the analog input to detect even subtle vibrations. This makes it ideal for interactive vibration-based projects, such as an electronic drum.

# Specification

- Supply Voltage: 3.3V to 5V
- Working Current：<1mA
- Working Temperature Range：－10℃～＋70℃
- Output Signal：analog signal

## Hardware Setup

Connect the S pin of module to Analog A0 of Lorfi Board, connect the negative pin to GND port, NC pin to 5V port.

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
#define Sensor PB3

void setup() {
  Serial.begin(9600);  //Open the serial to set the baud rate as 9600bps
}
void loop() {
  int val = analogRead(Sensor);  //Connect the sensor to analog interface A0
  Serial.print("Vibration is ");
  Serial.println(val, DEC);  //Print the analog value read on serial port
  delay(100);
}
```

## Expected Output

Once the code is succesfully uploaded you must see the following output or behavior.

*ADD HERE IMAGE OF SUCCESSFUL UPLOAD*

*ADD HERE IMAGE OF EXPECTED OUTPUT IN SERIAL IF ANY*

## FAQ
