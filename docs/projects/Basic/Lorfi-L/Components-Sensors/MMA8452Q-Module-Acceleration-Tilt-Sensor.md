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