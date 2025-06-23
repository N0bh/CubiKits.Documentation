# Infrared Obstacle Avoidance using Lorfi-L

# Description

The infrared obstacle sensor is designed for wheeled robots, with adjustable detection range (2–40 cm) and strong resistance to ambient light. It uses infrared reflection to detect objects and outputs a digital signal when an obstacle is sensed. Compatible with 3.3V–5V systems, it's ideal for Arduino and other microcontrollers.

# Specification

- Working voltage: DC 3.3V-5V
- Working current: ≥20mA
- Working temperature: －10℃ to＋50℃
- Detection distance: 2-40cm
- IO Interface: 4 wire interfaces (-/+/S/EN)
- Output signal: TTL voltage
- Accommodation mode: Multi-circle resistance regulation
- Effective Angle: 35°

## Hardware Setup

|     Module    |   Lorfi L   |
|---------------|-------------|
| Signal        | PB5         |
| VCC           | 5V          |
| GND           | GND         |

Connect the Signal pin of the sensor to the Digital Input PB5 on the Lorfi board, connect the GND pin to GND port, VCC pin to 5V port.

![Obstacle Avoidance Sensor](\assets\Images\LORFI Components\Lorfi-L_Sensors\16.png)

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

![Software Guide 4](\assets\Images\LORFI Components\Software-Guide_Images\Software_Guide4.png)

If failing, test the UART connection by checking the version. Use `AT+VER=?` command with baud rate of 115200. In case of MCU brick, revive the RAK3172 by following this [guide from RAKwireless](https://learn.rakwireless.com/hc/en-us/articles/26687606549911-How-To-Guide-STM32CubeProgrammer-for-RAK-Modules).

## **Sample Code**

```c
#define sensorPin PB5    // the number of the sensor pin
int sensorState = 0;         // variable for reading the sensor status
void setup() {    
  pinMode(sensorPin, INPUT); }
void loop(){
  // read the state of the sensor value:
  sensorState = digitalRead(sensorPin);
  // if it is, the sensorState is HIGH:
  if (sensorState == HIGH) {     
     Serial.print("Object Detected!");  
  } 
  else {
     Serial.print("Object not Detected!");
  }
}
```

## **How It Works**
1. The sensor sends out an ultrasonic pulse
2. The pulse reflects off objects and returns
3. The sensor measures the time between sending and receiving
4. Distance is calculated using: `Distance = (Time × Speed of Sound) / 2`

## **Applications**
- Robot obstacle avoidance
- Automatic parking systems  
- Liquid level measurement
- Security systems

## **Troubleshooting**
- **No readings:** Check wiring connections
- **Inconsistent readings:** Ensure sensor is mounted securely
- **Out of range:** Target may be too close (<2cm) or too far (>40cm)

## Expected Output

Once the code is succesfully uploaded you must see the following output or behavior.

*ADD HERE IMAGE OF SUCCESSFUL UPLOAD*

*ADD HERE IMAGE OF EXPECTED OUTPUT IN SERIAL IF ANY*

## FAQ

