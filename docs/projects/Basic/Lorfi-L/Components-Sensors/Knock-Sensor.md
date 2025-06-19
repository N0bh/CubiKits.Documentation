# knock Sensor using Lorfi-W

# Description

This module functions as a knock sensor that generates a brief signal when tapped or knocked. It can be paired with an Arduino for creative projects, such as building an electronic drum.


# Specification

- Working voltage: 5V
- Size: 30*20mm
- Weight: 3g

## Hardware Setup

Connect the S pin of module to Digital Input of Lorfi board, connect the negative pin to GND port, positive pin to 5V port.

![Knock Sensor](\assets\Images\LORFI Components\Lorfi-L_Sensors\11.png)

#### Using directly Lorfi-L

You can find complete [Lorfi-L IO pinout here].

*MIGHT NEED TO ADD NOTES ON POWER REQUIREMENTS, PIN CONSIDERATIONS, ETC.*

#### Using Lorfi Interface board

You can find complete guide for [Lorfi Interface here].

*MIGHT NEED TO ADD NOTES ON POWER REQUIREMENTS, PIN CONSIDERATIONS, ETC.*

## Software Setup

Lorfi-L is based on RAK3172 LoRaWAN module. This must be added to Arduino IDE.

Here's the guide on <a href="/docs/Software-Guide.html">how to add RAK3172 on your Arduino IDE</a>.

Once RAK3172 is added, you can now select it from the board selection.

![Software Guide 4](\assets\Images\LORFI Components\Software-Guide_Images\Software_Guide4.png)

If failing, test the UART connection by checking the version. Use `AT+VER=?` command with baud rate of 115200. In case of MCU brick, revive the RAK3172 by following this [guide from RAKwireless](https://learn.rakwireless.com/hc/en-us/articles/26687606549911-How-To-Guide-STM32CubeProgrammer-for-RAK-Modules).

## **Sample Code**
```c
#define Sensor PB5  // PB5 corresponds to a pin number (depends on the board, e.g. D11 on Uno)

// State variable to detect knock
volatile bool knockDetected = false;

void setup() {
  pinMode(Sensor, INPUT);
  attachInterrupt(digitalPinToInterrupt(Sensor), blink, FALLING);  // Use digitalPinToInterrupt
  Serial.begin(9600);
}

void loop() {
  if (knockDetected) {
    knockDetected = true;
    Serial.println("Knock Detected!");
    delay(1000);  // Debounce delay
  } else {
    knockDetected = false;
    Serial.println("Knock Not Detected!");
    delay(1000);
  }
}

void blink() {
  knockDetected = true;
}
```

## Expected Output

Once the code is succesfully uploaded you must see the following output or behavior.

*ADD HERE IMAGE OF SUCCESSFUL UPLOAD*

*ADD HERE IMAGE OF EXPECTED OUTPUT IN SERIAL IF ANY*

## FAQ
