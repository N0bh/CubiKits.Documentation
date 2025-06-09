# White LED Module using Lorfi-L

# Description
This white LED light module is perfect for Arduino beginners. It easily connects to an IO or sensor shield and allows for experimentation with light-based projects.

# Specification

- White LED Module
- Type: Digital
- PH2.54 socket
- Size: 30*20mm
- Weight: 3g


## Hardware Setup

The pushbutton will be connected to digital IO pin of Lorfi-L. 

#### Using directly Lorfi-L

You can find complete [Lorfi-L IO pinout here].

![Ultrasonic Sensor Connection]({{ '/assets/images/ultrasonic-connection.png' | relative_url }})

*MIGHT NEED TO ADD NOTES ON POWER REQUIREMENTS, PIN CONSIDERATIONS, ETC.*

#### Using Lorfi Interface board

You can find complete guide for [Lorfi Interface here].

![Ultrasonic Sensor Connection]({{ '/assets/images/ultrasonic-connection.png' | relative_url }})

*MIGHT NEED TO ADD NOTES ON POWER REQUIREMENTS, PIN CONSIDERATIONS, ETC.*

## Software Setup

Lorfi-L is based on RAK3172 LoRaWAN module. This must be added to Arduino IDE.

Here's the guide [how to add RAK3172 on your Arduino IDE].

Once RAK3172 is added, you can now select it from the board selection.

*ADD HERE IMAGE OF RAK3172 ON BOARD SELECTION IN ARDUINO IDE.*

If failing, test the UART connection by checking the version. Use `AT+VER=?` command with baud rate of 115200. In case of MCU brick, revive the RAK3172 by following this [guide from RAKwireless](https://learn.rakwireless.com/hc/en-us/articles/26687606549911-How-To-Guide-STM32CubeProgrammer-for-RAK-Modules).

## **Sample Code**
```c
#define LED PB5

void setup()
{
  pinMode(LED, OUTPUT);     //Set PB5 as output
}
void loop()
{    digitalWrite(LED, HIGH);   //Turn off led
     delay(1000);
     digitalWrite(LED, LOW);    //Turn on led
     delay(1000);
}
```

## Expected Output

Once the code is succesfully uploaded you must see the following output or behavior.

*ADD HERE IMAGE OF SUCCESSFUL UPLOAD*

*ADD HERE IMAGE OF EXPECTED OUTPUT IN SERIAL IF ANY*

## FAQ

1. Why button is not responding?
- Check if the header pins are properly connected

2. Why LED is dim?
- Check if you are using 5V or 3.3V

