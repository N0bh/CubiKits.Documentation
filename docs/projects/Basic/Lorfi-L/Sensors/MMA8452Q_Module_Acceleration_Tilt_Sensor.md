# MMA8452Q Module Acceleration Tilt Sensor using Lorfi-L

# Description

The MMA8452Q is a smart, low-power, three-axis capacitive accelerometer with 12-bit resolution. It offers advanced features, including customizable settings and dual interrupt pin configuration. Its built-in interrupt functions help reduce overall power usage by eliminating the need for constant data polling by the main processor. The sensor supports selectable measurement ranges of ±2g, ±4g, and ±8g, and can provide both high-pass filtered and unfiltered output data in real time. Additionally, it includes an inertial wake-up feature that allows the device to stay in low-power mode while monitoring for motion events.

# Specification

- Power Supply Voltage：1.95 V to 3.6 V
- Interface Voltage：1.6 V to 3.6 V
- ±2g/±4g/±8g Optional dynamic range
- Output data rate (ODR) range: 1.56Hz to 800Hz
- Noise：99μg/√Hz
- 12 bits and 8 bits digital outputs;
- I2C digital output interface (up to 2.25MHz when the pull-up resistor is 4.7kΩ);
- Two programmable interruption pins applied to six interruption sources;
- Three motion detection embedded channels: free fall detection, pulse detection, shaking detection;
- Direction (transverse/longitudinal) detection with setting lag compensation;
- Automatic arousal and auto-dormant ODR can be automatically altered;
- High-pass filtering data can be exported in real time;
- Power consumption: 6μA – 165μA

## Hardware Setup

|     Sensor    |   Lorfi L   |
|---------------|-------------|
| SDA           | PA11        |
| SCL           | PA12        |
| VCC           | 3V          |
| GND           | GND         |

Connect the SCL pin to pin 9, SDA pin to pin 10 of the Lorfi Board; Connect positive pin to 3V3 port, negative pin to GND port.

![MMA8452Q Module Acceleration Tilt Senso](\assets\Images\LORFI_Components\Lorfi-L_Sensors\14.png)

#### Using directly Lorfi-L

You can find complete <a href="/docs/Hardware_Guide.html">Lorfi-L IO pinout here</a>.

*MIGHT NEED TO ADD NOTES ON POWER REQUIREMENTS, PIN CONSIDERATIONS, ETC.*

#### Using Lorfi Interface board

You can find complete guide for <a href="/docs/Hardware_Guide.html">Lorfi Interface here</a>.

*MIGHT NEED TO ADD NOTES ON POWER REQUIREMENTS, PIN CONSIDERATIONS, ETC.*

## Software Setup

Lorfi-L is based on RAK3172 LoRaWAN module. This must be added to Arduino IDE.

Here's the guide on <a href="/docs/Software_Guide.html">how to add RAK3172 on your Arduino IDE</a>.

Once RAK3172 is added, you can now select it from the board selection.

![Software Guide 4](\assets\Images\LORFI_Components\Software-Guide_Images\Software_Guide4.png)

If failing, test the UART connection by checking the version. Use `AT+VER=?` command with baud rate of 115200. In case of MCU brick, revive the RAK3172 by following this [guide from RAKwireless](https://learn.rakwireless.com/hc/en-us/articles/26687606549911-How-To-Guide-STM32CubeProgrammer-for-RAK-Modules).

## **Sample Code**
```c
#include <Wire.h>               // Must include Wire library for I2C
#include <SparkFun_MMA8452Q.h>  // Includes the SFE_MMA8452Q library

MMA8452Q accel;
// The setup function simply starts serial and initializes the
//  accelerometer.
void setup() {
  Serial.begin(9600);
  Serial.println("MMA8452Q Test Code!");
  accel.init();

}

void loop() {
  // Use the accel.available() function to wait for new data
  //  from the accelerometer.
  if (accel.available()) {
    // First, use accel.read() to read the new variables:
    accel.read();

    // accel.read() will update two sets of variables.
    // * int's x, y, and z will store the signed 12-bit values
    //   read out of the accelerometer.
    // * floats cx, cy, and cz will store the calculated
    //   acceleration from those 12-bit values. These variables
    //   are in units of g's.
    // Check the two function declarations below for an example
    // of how to use these variables.
    printCalculatedAccels();
    //printAccels(); // Uncomment to print digital readings

    printOrientation();

    Serial.println();  // Print new line every time.
  }
}

void printAccels() {
  Serial.print(accel.x, 3);
  Serial.print("\t");
  Serial.print(accel.y, 3);
  Serial.print("\t");
  Serial.print(accel.z, 3);
  Serial.print("\t");
}

void printCalculatedAccels() {
  Serial.print(accel.cx, 3);
  Serial.print("\t");
  Serial.print(accel.cy, 3);
  Serial.print("\t");
  Serial.print(accel.cz, 3);
  Serial.print("\t");
}

void printOrientation() {
  byte pl = accel.readPL();
  switch (pl) {
    case PORTRAIT_U:
      Serial.print("Portrait Up");
      break;
    case PORTRAIT_D:
      Serial.print("Portrait Down");
      break;
    case LANDSCAPE_R:
      Serial.print("Landscape Right");
      break;
    case LANDSCAPE_L:
      Serial.print("Landscape Left");
      break;
    case LOCKOUT:
      Serial.print("Flat");
      break;
  }
}
```

## Expected Output

Once the code is succesfully uploaded you must see the following output or behavior.

*ADD HERE IMAGE OF SUCCESSFUL UPLOAD*

*ADD HERE IMAGE OF EXPECTED OUTPUT IN SERIAL IF ANY*

## FAQ
