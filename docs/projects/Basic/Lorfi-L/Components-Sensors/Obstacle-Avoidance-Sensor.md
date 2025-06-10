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
// Ultrasonic Sensor Distance Measurement V4
const int trigPin = 7;
const int echoPin = 8;

void setup() {
Serial.begin(9600);
pinMode(trigPin, OUTPUT);
pinMode(echoPin, INPUT);
}

void loop() {
long duration, distance;

// Clear the trigPin
digitalWrite(trigPin, LOW);
delayMicroseconds(2);

// Trigger the sensor
digitalWrite(trigPin, HIGH);
delayMicroseconds(10);
digitalWrite(trigPin, LOW);

// Read the echoPin
duration = pulseIn(echoPin, HIGH);

// Calculate distance
distance = duration * 0.034 / 2;

Serial.print("Distance: ");
Serial.print(distance);
Serial.println(" cm");

delay(500);
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

