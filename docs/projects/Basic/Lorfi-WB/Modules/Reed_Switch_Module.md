---
layout: project
title: Reed Switch Module using Lorfi-WB
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

|     Module    |   Lorfi WB  |
|---------------|-------------|
| Signal        | GPIO2       |
| VCC           | 5V          |
| GND           | GND         |

Connect the Signal pin of sensor to Digital Input of the Lorfi board, negative pin to GND port, positive pin to 5V port.

<p style="text-align: center;">
  <img src="\assets\Images\LORFI_Components\Lorfi-WB_Modules\10.png" alt="Centered Image" width="900" />
</p>

#### Using directly Lorfi-WB

You can find complete <a href="/docs/Hardware_Guide.html">Lorfi-WB IO pinout here</a>.

*MIGHT NEED TO ADD NOTES ON POWER REQUIREMENTS, PIN CONSIDERATIONS, ETC.*

#### Using Lorfi Interface board

You can find complete guide for <a href="/docs/Hardware_Guide.html">Lorfi Interface here</a>.

*MIGHT NEED TO ADD NOTES ON POWER REQUIREMENTS, PIN CONSIDERATIONS, ETC.*

## Software Setup

Lorfi-WB is built around the ESP32 chipset and supports both Wi-Fi and Bluetooth Low Energy (BLE). This must be added to Arduino IDE.

Here's the guide on <a href="/docs/Software_Guide.html">how to add ESP32 board on your Arduino IDE</a>.

Once ESP32 board is added, you can now select it from the board selection.

<p style="text-align: center;">
  <img src="\assets\Images\LORFI_Components\Software-Guide_Images\Software_Guide4.png" alt="Centered Image" width="900" />
</p>

## Sample Code

```c
#define Sensor 2
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
