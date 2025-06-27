# Single Relay Module using Lorfi-WB

# Description

This single relay module is suitable for use in interactive projects and features a high-quality SINGLE 5V relay. It's capable of controlling lights, electrical appliances, and other equipment. Its modular design allows for easy integration with Arduino boards. The module can be operated via a digital I/O pin, making it ideal for switching devices like solenoid valves, lamps, motors, and other components that require high current or high voltage.

# Specification

- Type: Digital
- Rated current: 10A (NO) 5A (NC)
- Maximum switching voltage: 150VAC 24VDC
- Digital interface
- Control signal: TTL level
- Rated load: 8A 150VAC (NO), 10A 24VDC (NO), 5A 250VAC (NO/NC), 5A 24VDC (NO/NC)
- Maximum switching power: AC1200VA DC240W (NO), AC625VA DC120W (NC)
- Contact action time: 10ms

## Hardware Setup

|     Module    |   Lorfi WB  |
|---------------|-------------|
| Signal        | GPIO2       |
| VCC           | 5V          |
| GND           | GND         |

Connect the Signal pin of sensor to Digital Input of the Lorfi board, negative pin to GND port, positive pin to 5V port.

![Single Relay Module](\assets\Images\LORFI_Components\Lorfi-WB_Modules\12.png)

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

![Software Guide 4](\assets\Images\LORFI_Components\Software-Guide_Images\Software_Guide4.png)

## **Sample Code**
```c
#define Relay 2

void setup() {
  pinMode(Relay, OUTPUT); 
}
void loop() {
  digitalWrite(Relay, HIGH);    //Turn off relay
  Serial.println("Relay ON!");  //Print that relay is ON!
  delay(2000);
  digitalWrite(Relay, LOW);     //Turn on relay
  Serial.println("Relay OFF!");  //Print that relay is OFF!
  delay(2000);
}
```

## Expected Output

Once the code is succesfully uploaded you must see the following output or behavior.

*ADD HERE IMAGE OF SUCCESSFUL UPLOAD*

*ADD HERE IMAGE OF EXPECTED OUTPUT IN SERIAL IF ANY*

## FAQ


