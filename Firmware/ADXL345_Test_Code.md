#include <Wire.h>
#include <Adafruit_Sensor.h>
#include <Adafruit_ADXL345_U.h>

Adafruit_ADXL345_Unified accel = Adafruit_ADXL345_Unified(12345);

void setup() {

  Serial.begin(115200);
  Wire.begin(21, 22);

  if (!accel.begin()) {
    Serial.println("ADXL345 NOT FOUND!");
    while (1);
  }

  accel.setRange(ADXL345_RANGE_2_G);

  Serial.println("================================");
  Serial.println("ADXL345 Test Started");
  Serial.println("================================");
}

void loop() {

  sensors_event_t event;
  accel.getEvent(&event);

  Serial.print("X: ");
  Serial.print(event.acceleration.x);
  Serial.print(" m/s^2");

  Serial.print("   Y: ");
  Serial.print(event.acceleration.y);
  Serial.print(" m/s^2");

  Serial.print("   Z: ");
  Serial.print(event.acceleration.z);
  Serial.println(" m/s^2");

  delay(200);
}
