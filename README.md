# Task 1 - Temperature Monitoring & LCD Display

## Intern Details
- **Name:** [Aapka Naam]
- **Internship ID:** [Aapki ID]
- **Company:** Alfido Tech

## Goal
The goal of this task is to read temperature data from an LM35 sensor (simulated via potentiometer) using an Arduino UNO, display the current value on a 16x2 I2C LCD, and log the readings over serial monitor.

## Hardware Components Used
- Arduino UNO
- LM35 Temperature Sensor (or Potentiometer for simulation)
- 16x2 Character I2C LCD Module
- Jumper Wires & Breadboard

## Circuit Wiring Diagram
*(Apni upload ki hui Image file ka name niche box mein replace karein)*

| Component Pin | Arduino Pin |
|---|---|
| LM35 Left (VCC) | 5V |
| LM35 Mid (OUT) | A0 |
| LM35 Right (GND)| GND |
| I2C LCD VCC | 5V |
| I2C LCD GND | GND |
| I2C LCD SDA | A4 |
| I2C LCD SCL | A5 |

<img src="Circuit_Diagram.png" alt="Circuit Wiring Diagram" width="500">

*(Tip: Markdown mein image add karne ke liye upar wala format use karein. Bas file name `Circuit_Diagram.png` apni file ke unique name se badal dein.)*

## Working Demo (60-second Video)
Niche di gayi video system ki live working dikhati hai. Ismein maine potentiometer (Wokwi simulation) ghumakar temperature change karke live LCD update dikhaya hai.

<video src="AlfidoTech_Task1_Demo.mp4" width="600" controls>
Your browser does not support the video tag.
</video># Temperature-Monitoring-System-Arduino
ask 1: Read temperature from LM35/Potentiometer and display on I2C LCD.
