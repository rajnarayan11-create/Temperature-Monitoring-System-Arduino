# 🌡️ Task 1: Temperature Monitoring System

**Alfido Tech - Embedded Systems Internship**

This repository contains the solution for **Task 1**, which involves reading temperature data from an LM35 sensor (simulated via a potentiometer) and displaying the real-time values on a 16x2 I2C LCD using an Arduino UNO.

## 👤 Intern Details
- **Name:** [RAJ NARAYAN GAUR]
- **Internship ID:** [BS/REG/121633]
- **Domain:** Embedded Systems

---

## 🛠️ Hardware Components
1. Arduino UNO
2. LM35 Temperature Sensor (Simulated)
3. 16x2 I2C LCD Display
4. Breadboard & Jumper Wires

---

## 📸 Circuit Diagram
The circuit has been designed with accurate pin mapping for the I2C protocol and analog reading.


![Circuit Diagram](https://github.com/user-attachments/assets/35ce006e-2f73-4601-824f-19fbbb5580c3)
---

## 🎥 Working Demonstration
Below is the 60-second live demonstration of the simulation. As the sensor values are adjusted, the temperature updates in real-time on both the Serial Monitor and the I2C LCD.

*(Note: Replace the URL in `src=""` with your actual video link copied from the Issues page)*

<br>
<video src="https://github.com/user-attachments/assets/a0e142a9-3230-43d1-ab76-08e5c72754aa" width="100%" controls>
  Your browser does not support the video tag.
</video>
<br>

---

## 💻 Arduino Source Code
The project uses the `LiquidCrystal_I2C` library for display management and non-blocking `millis()` logic for optimal performance.

```cpp
```cpp
#include <Wire.h>
#include <LiquidCrystal_I2C.h>

// Create LCD object (I2C Address: 0x27, LCD Size: 16x2)
LiquidCrystal_I2C lcd(0x27, 16, 2);

// LM35 sensor connected to analog pin A0
const int lm35Pin = A0;

// Variables for timed temperature updates
unsigned long lastUpdateTime = 0;
const unsigned long updateInterval = 1000; // Update every 1 second

void setup() {
  // Start Serial Communication
  Serial.begin(9600);

  // Initialize LCD
  lcd.init();
  lcd.backlight();

  // Welcome message
  lcd.setCursor(0, 0);
  lcd.print("Temp Monitor");
  delay(2000);
  lcd.clear();
}

void loop() {

  // Check if it's time to update the temperature
  if (millis() - lastUpdateTime >= updateInterval) {

    lastUpdateTime = millis();

    // Read sensor value from LM35
    int sensorValue = analogRead(lm35Pin);

    // Convert ADC value to voltage
    float sensorVoltage = sensorValue * (5.0 / 1023.0);

    // Convert voltage to temperature (LM35: 10mV per °C)
    float temperature = sensorVoltage * 100.0;

    // Print temperature on Serial Monitor
    Serial.print("Current Temp: ");
    Serial.print(temperature);
    Serial.println(" °C");

    // Display temperature on LCD
    lcd.setCursor(0, 0);
    lcd.print("Temp: ");
    lcd.print(temperature);
    lcd.print(" C   ");   // Extra spaces clear old digits
  }
}
```
