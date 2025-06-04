## Introduction

Pushbuttons is the most common hardware interface to different hardware.

## Hardware Setup

The pushbutton will be connected to digital IO pin of Lorfi-L.

## Software Setup

Lorfi-L is based on RAK3172 LoRaWAN module. This must be added to Arduino IDE.

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

## Expected Output

## FAQ
