# GUVA-S12SD-3528-Ultraviolet-Sensor using Lorfi-W

# Description

The GUVA-S12SD ultraviolet sensor is designed to detect UV light. It is commonly used to measure the UV index in smart wearable devices like watches, smartphones, and other outdoor gadgets. Additionally, it can monitor UV light intensity and serve as a UV flame detector, especially in applications involving UV-based disinfection.

# Specification

- Supply Voltage: 3.3V to 5V
- Detection range: 20cm (4.8V) ~ 100cm (1V)
- Rang of Spectral Bandwidth: 760nm to 1100nm
- Operating temperature: -25℃to 85℃
- Interface: digital
- Size: 44*16.7mm
- Weight: 4g

## Hardware Setup

Connect the D0 pin of module to Digital Input of Lorfi board, connect the GND pin to GND port, VCC pin to 5V port.

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
  Serial.begin(9600);  //Open the serial to set the baud rate as 9600bps
}
void loop() {
  int sensorValue = analogRead(Sensor);
  // print out the value you read:
  Serial.println(sensorValue);
  delay(1000);        // delay in between reads for stability
}
```

## Expected Output

Once the code is succesfully uploaded you must see the following output or behavior.

*ADD HERE IMAGE OF SUCCESSFUL UPLOAD*

*ADD HERE IMAGE OF EXPECTED OUTPUT IN SERIAL IF ANY*

## FAQ
