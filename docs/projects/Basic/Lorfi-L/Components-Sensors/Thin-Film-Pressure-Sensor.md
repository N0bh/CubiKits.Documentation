# Thin-Film Pressure Sensor using Lorfi-L

# Description

This sensor uses advanced flexible nano pressure-sensitive material combined with an ultra-thin film pad. It features both waterproofing and pressure detection capabilities. When external pressure is applied, the sensor's resistance changes. Through a connected circuit, these resistance changes are converted into corresponding electrical signals, allowing pressure variations to be monitored by observing the signal output.

# Specification

- Working Voltage：DC 3.3V—5V
- Range：0-10KG
- Thickness：＜0.25mm
- Response Point：＜20g
- Repeatability：＜±5.8%（50% load）
- Accuracy：±2.5%（85% range interval）
- Durability：＞100 thousand times
- Initial Resistance：＞100MΩ(no load)
- Response Time：＜1ms
- Recovery Time：＜15ms
- Working Temperature：﹣20℃—60℃

## Hardware Setup

Connect the S pin of module to Analog A0 of the Lorfi board, connect the negative pin to GND port, positive pin to 5V port.

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
#define Sensor A0
void setup()
{
  Serial.begin(9600);
  pinMode(Sensor,INPUT);

}

void loop() 
{
  Serial.println(analogRead(Sensor));
  delay(500);
}
```

## Expected Output

Once the code is succesfully uploaded you must see the following output or behavior.

*ADD HERE IMAGE OF SUCCESSFUL UPLOAD*

*ADD HERE IMAGE OF EXPECTED OUTPUT IN SERIAL IF ANY*

## FAQ
