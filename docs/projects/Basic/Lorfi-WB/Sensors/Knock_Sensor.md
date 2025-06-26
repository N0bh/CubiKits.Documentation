# Knock Sensor using Lorfi-WB

# Description

This module functions as a knock sensor that generates a brief signal when tapped or knocked. It can be paired with an Arduino for creative projects, such as building an electronic drum.


# Specification

- Working voltage: 5V
- Size: 30*20mm
- Weight: 3g

## Hardware Setup

|     Module    |   Lorfi WB  |
|---------------|-------------|
| Signal        | GPIO2       |
| VCC           | 5V          |
| GND           | GND         |

Connect the Signal pin of the sensor to the Digital Input GPIO2 on the Lorfi board, connect the GND pin to GND port, VCC pin to 5V port.

![Knock Sensor](\assets\Images\LORFI_Components\Lorfi-WB_Sensors\9.png)

#### Using directly Lorfi-WB

You can find complete <a href="/docs/Hardware-Guide.html">Lorfi-WB IO pinout here</a>.

#### Using Lorfi Interface board

You can find complete guide for <a href="/docs/Hardware-Guide.html">Lorfi Interface here</a>.

## Software Setup

Lorfi-WB is built around the ESP32 chipset and supports both Wi-Fi and Bluetooth Low Energy (BLE). This must be added to Arduino IDE.

Here's the guide on <a href="/docs/Software-Guide.html">how to add ESP32 board on your Arduino IDE</a>.

Once ESP32 board is added, you can now select it from the board selection.

![Software Guide 4](\assets\Images\LORFI_Components\Software-Guide_Images\Software_Guide4.png)

## **Sample Code**
```c
#define Sensor 2  // PB5 corresponds to a pin number (depends on the board, e.g. D11 on Uno)

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
