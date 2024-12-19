# Flood Monitoring System using ESP32

## Overview
This project implements an **IoT-based Flood Monitoring System** using an **ESP32**, an ultrasonic sensor, and a buzzer. It monitors water levels and provides real-time alerts via Wi-Fi when flood conditions are detected.

## Features
- Real-time monitoring of water levels using an ultrasonic sensor (HC-SR04).
- Flood alert notification via HTTP POST request.
- Audible flood alert using a buzzer.
- Wi-Fi connectivity for sending alerts to a server or API.

## Components Required
1. **ESP32 Board**
2. **Ultrasonic Sensor (HC-SR04)**
3. **Buzzer**
4. **Jumper Wires**
5. **Power Supply (5V)**

## Pin Connections
| Component           | ESP32 Pin  |
|---------------------|------------|
| Ultrasonic Trig Pin | GPIO 25    |
| Ultrasonic Echo Pin | GPIO 26    |
| Buzzer              | GPIO 27    |

## Software Requirements
- Arduino IDE
- ESP32 Board Manager for Arduino
- Required libraries:
  - `WiFi.h`
  - `HTTPClient.h`

## Setup Instructions
1. **Install Arduino IDE**: Download and install from [Arduino's official website](https://www.arduino.cc/en/software).
2. **Configure ESP32 Board**:
   - Go to `File > Preferences`.
   - Add the following URL in the "Additional Board Manager URLs" field:
     ```
     https://dl.espressif.com/dl/package_esp32_index.json
     ```
   - Go to `Tools > Board > Board Manager` and search for "ESP32" to install.
3. **Install Required Libraries**:
   - Ensure `WiFi.h` and `HTTPClient.h` are included (bundled with ESP32 library).

4. **Upload the Code**:
   - Connect the ESP32 to your computer via USB.
   - Select the correct COM port under `Tools > Port`.
   - Upload the provided code.

5. **Wi-Fi Configuration**:
   - Edit the code to replace `Your_SSID` and `Your_PASSWORD` with your Wi-Fi credentials.

6. **Server Endpoint**:
   - Replace `http://yourserver.com/flood-alert` with your server's URL to handle flood alerts.

## Working Principle
1. The **ultrasonic sensor** continuously measures the water level by calculating the distance to the surface.
2. If the distance drops below a predefined threshold (e.g., `20 cm`), it triggers:
   - A **buzzer alarm**.
   - A **HTTP POST alert** sent via Wi-Fi to a server or API.
3. Alerts stop automatically when the water level returns to a safe range.

## Circuit Diagram
![Circuit Diagram]([https://example.com/circuit-diagram.png](https://www.upesy.com/blogs/tutorials/esp32-pinout-reference-gpio-pins-ultimate-guide))

## Example HTTP Request
- **URL**: `http://yourserver.com/flood-alert`
- **Method**: POST
- **Headers**:
  - `Content-Type: application/json`
- **Body**:
  ```json
  {
    "alert": "Flood detected! Water level is critical."
  }
