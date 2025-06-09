---
layout: project
title: "Module 1: White Led"
difficulty: basic
components: ["Whie Led Module", "Lorfi-L Rak3172", "Jumper Wires"]
---

# Project 36: Ultrasonic Ranger

## **Description**
This white LED light module is perfect for Arduino beginners. It easily connects to an IO or sensor shield and allows for experimentation with light-based projects.

## **Specifications**
- **White LED module:**
- **Type:** Digital 
- **PH2.54 socket:**
- **Effective Angle:** 35°
- **Size:** 30*20mm
- **Weight:** 3g

## **Required Components**
- UNO Board × 1
- Ultrasonic Sensor × 1  
- USB Cable × 1
- Jumper Wires × 4

## **Connection Diagram**

![Ultrasonic Sensor Connection]({{ '/assets/images/ultrasonic-connection.png' | relative_url }})

| Sensor Pin | Arduino Pin |
|------------|-------------|
| VCC | 5V |
| GND | GND |
| Trig | Digital Pin 7 |
| Echo | Digital Pin 8 |

## **Sample Code**
```c
#define LED PB5

void setup()
{
  pinMode(LED, OUTPUT);     //Set Pin7 as output
}
void loop()
{    digitalWrite(LED, HIGH);   //Turn off led
     delay(1000);
     digitalWrite(LED, LOW);    //Turn on led
     delay(1000);
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
