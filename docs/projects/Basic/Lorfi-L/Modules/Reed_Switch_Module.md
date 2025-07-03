---
layout: project
title: Reed Switch Module using Lorfi-L
---

# Description

A reed switch is a specialized type of switch that serves as a key component in reed relays and proximity switches.

It typically consists of two flexible metal reed contacts made of soft magnetic material. These contacts separate when no magnetic field is present. In some designs, a third reed is added to function as a normally-closed contact. All reed elements are sealed within a glass tube filled with inert gases like nitrogen or helium, or in some cases, a vacuum, to protect the contacts.

Inside the tube, the reed contacts are positioned parallel to each other with their ends overlapping. Depending on the spacing or contact between the reeds, the switch can be normally open or normally closed.

Reed switches are versatile and used in a variety of applications such as counters, limit switches, and more. For example, a bicycle odometer can be built by attaching a magnet to the wheel and positioning a reed switch nearby. They are also commonly installed on doors for alarm systems or used as simple on/off switches.

Widely adopted in household appliances, automobiles, communication equipment, industrial systems, healthcare devices, and security systems, reed switches also integrate well with other components like liquid level sensors, magnetic door sensors, reed relays, oil level detectors, and magnetic proximity sensors. They are suitable for use even in high-risk environments.


# Specification

- Working voltage: DC 3.3V-5V
- Working current: ≥20mA
- Working temperature: －10℃ to ＋50℃
- Detection distance: ≤10mm
- IO Interface: 3 wire interfaces (-/+/S)
- Size: 30*20mm
- Weight: 3g


## Hardware Setup

|     Module    |   Lorfi L   |
|---------------|-------------|
| Signal        | PB5         |
| VCC           | 5V          |
| GND           | GND         |

Connect the Signal pin of sensor to Digital Input of the Lorfi board, negative pin to GND port, positive pin to 5V port.

<p style="text-align: center;">
  <img src="\assets\Images\LORFI_Components\Lorfi-L_Modules\10.png" alt="Centered Image" width="900" />
</p>

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

<p style="text-align: center;">
  <img src="\assets\Images\LORFI_Components\Software-Guide_Images\Software_Guide4.png" alt="Centered Image" width="900" />
</p>

If failing, test the UART connection by checking the version. Use `AT+VER=?` command with baud rate of 115200. In case of MCU brick, revive the RAK3172 by following this [guide from RAKwireless](https://learn.rakwireless.com/hc/en-us/articles/26687606549911-How-To-Guide-STM32CubeProgrammer-for-RAK-Modules).

## Sample Code:
```c
#define Sensor PB5
int val;  //define digital variable val

void setup() {
  pinMode(Sensor, INPUT);  //define magnetic ring sensor as output interface
  Serial.begin(9600);
}
void loop() {
  val = digitalRead(Sensor);  // read and assign the value of digital interface 3 to val
  if (val == HIGH) {          //When a signal is detected by magnetic ring sensor, LED will flash
    Serial.println("Signal Detected!");
  } else {
    Serial.println("No Signal Detected!");
  }
  delay(100);
}
```

## Expected Output

Once the code is succesfully uploaded you must see the following output or behavior.

*ADD HERE IMAGE OF SUCCESSFUL UPLOAD*

*ADD HERE IMAGE OF EXPECTED OUTPUT IN SERIAL IF ANY*

## FAQ
