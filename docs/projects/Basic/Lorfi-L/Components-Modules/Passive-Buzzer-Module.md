# using Lorfi-L

# Description


# Specification



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
#define LED PB5  //set digital IO pin of the buzzer
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
