# Digital IR Transmitter using Lorfi-L

# Description

The IR transmitter module is designed for infrared communication, a method commonly used to control devices like televisions over short distances with a direct line of sight. Since IR signals are a form of light, they require a clear path to the receiving device, though they can also be reflected off surfaces like mirrors.

Infrared receivers typically have a limited detection angle, which is influenced by the optical properties of the phototransistor. However, placing a matte, transparent material in front of the receiver can help widen this angle and improve performance.

# Specification

- Power Supply: 3-5V
- Infrared center frequency: 850nm-940nm
- Infrared emission angle: about 20 degrees
- Infrared emission distance: about 1.3m (5V 38Khz)
- Interface socket: JST PH2.0
- Mounting hole: inner diameter is 3.2mm, spacing is 15mm

## Hardware Setup

![IR Transmitter Module](\assets\Images\LORFI Components\Lorfi-L_Modules\7.png)

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
#define led PB5
void setup() {                
   pinMode(led, OUTPUT);     
}
void loop() {
  digitalWrite(led, HIGH);  

  delay(1000);               
  digitalWrite(led, LOW);   
  delay(1000); }
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
