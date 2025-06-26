# Soil Humidity Sensor using Lorfi-L

# Description

This soil moisture sensor is designed to measure the humidity level in soil. When the soil is dry, the sensor's analog output decreases; when the soil is moist, the output increases. It's ideal for creating an automatic watering system that can detect when your plant needs water, helping prevent it from drying out while you're away.

When paired with an Arduino, this sensor can make plant care smarter and more efficient. It features two probes that are inserted into the soil. By measuring the change in current between the probes, it determines the soil's resistance and converts it into a moisture level. Higher moisture means lower resistance and better conductivity. The sensor's surface is metal-coated to enhance durability. Simply insert it into the soil and use an ADC to read the values—your plant can now "tell" you when it's thirsty.

# Specification

- Power Supply Voltage: 3.3V or 5V
- Working Current: ≤ 20mA
- Output Voltage: 0-2.3V (When the sensor is totally immersed in water, the voltage will be 2.3V). The higher humidity, the higher the output voltage.
- Sensor type: Analog output
- Interface: Pin1- signal, Pin2- GND, Pin3 - VCC

## Hardware Setup

|     Sensor    |   Lorfi L   |
|---------------|-------------|
| Signal        | A0          |
| VCC           | 5V          |
| GND           | GND         |

Connect the S pin of module to Analog A0 of the Lorfi board, connect the negative pin to GND port, positive pin to 5V port.

![Soil Humidity Sensor](\assets\Images\LORFI_Components\Lorfi-L_Sensors\19.png)

#### Using directly Lorfi-L

You can find complete <a href="/docs/Hardware-Guide.html">Lorfi-L IO pinout here</a>.

*MIGHT NEED TO ADD NOTES ON POWER REQUIREMENTS, PIN CONSIDERATIONS, ETC.*

#### Using Lorfi Interface board

You can find complete guide for <a href="/docs/Hardware-Guide.html">Lorfi Interface here</a>.

*MIGHT NEED TO ADD NOTES ON POWER REQUIREMENTS, PIN CONSIDERATIONS, ETC.*

## Software Setup

Lorfi-L is based on RAK3172 LoRaWAN module. This must be added to Arduino IDE.

Here's the guide on <a href="/docs/Software-Guide.html">how to add RAK3172 on your Arduino IDE</a>.

Once RAK3172 is added, you can now select it from the board selection.

![Software Guide 4](\assets\Images\LORFI_Components\Software-Guide_Images\Software_Guide4.png)

If failing, test the UART connection by checking the version. Use `AT+VER=?` command with baud rate of 115200. In case of MCU brick, revive the RAK3172 by following this [guide from RAKwireless](https://learn.rakwireless.com/hc/en-us/articles/26687606549911-How-To-Guide-STM32CubeProgrammer-for-RAK-Modules).

## **Sample Code**
```c
#define Sensor A0 //Connect sensor pin to Analog Input

void setup() {
  Serial.begin(115200);
  pinMode(Sensor, INPUT);
}

void loop() {

  Serial.print("Moisture Sensor Value:");
  Serial.println(Sensor);
  delay(100);
}
```

## Expected Output

Once the code is succesfully uploaded you must see the following output or behavior.

*ADD HERE IMAGE OF SUCCESSFUL UPLOAD*

*ADD HERE IMAGE OF EXPECTED OUTPUT IN SERIAL IF ANY*

## FAQ


