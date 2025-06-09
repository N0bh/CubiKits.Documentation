# Digital IR Receiver using Lorfi-L

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
 #define RECV_PIN PB5
 IRrecv irrecv(RECV_PIN);
 decode_results results;
 void setup()
{
  Serial.begin(9600);
  irrecv.enableIRIn(); // Start the receiver
}
 void loop() {
  if (irrecv.decode(&results)) {
    Serial.println(results.value, HEX);
    irrecv.resume(); // Receive the next value
  }
}
```

## Expected Output

Once the code is succesfully uploaded you must see the following output or behavior.

*ADD HERE IMAGE OF SUCCESSFUL UPLOAD*

*ADD HERE IMAGE OF EXPECTED OUTPUT IN SERIAL IF ANY*

## FAQ