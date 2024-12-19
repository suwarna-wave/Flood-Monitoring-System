# Simple Flood Monitoring System

## Overview
This is a simple flood monitoring system using an Arduino, an ultrasonic sensor, and a buzzer. The system measures the distance to water levels and triggers an alarm when the water exceeds a predefined threshold. It also displays water level messages on the Serial Monitor.

---

## Features
- Real-time water level monitoring using an **ultrasonic sensor** (HC-SR04).
- **Buzzer alarm** to signal flood conditions.
- Water level and alert messages displayed on the Serial Monitor.

---

## Components Required
| Component            | Quantity |
|----------------------|----------|
| Arduino Board        | 1        |
| Ultrasonic Sensor (HC-SR04) | 1 |
| Buzzer               | 1        |
| Breadboard           | 1        |
| Jumper Wires         | Several  |

---

## Pin Connections
| Component           | Pin Type     | Arduino Pin |
|---------------------|--------------|-------------|
| **Ultrasonic Sensor** | **Trig Pin**   | Pin 9       |
|                     | **Echo Pin**   | Pin 10      |
|                     | **VCC**       | 5V          |
|                     | **GND**       | GND         |
| **Buzzer**          | **Signal Pin** | Pin 8       |
|                     | **VCC**       | 5V          |
|                     | **GND**       | GND         |

### Ultrasonic Sensor HC-SR04:
- **Trig Pin**: Used to send ultrasonic pulses.
- **Echo Pin**: Receives the reflected pulse to calculate distance.

### Buzzer:
- **Signal Pin**: Receives HIGH/LOW signal to turn the buzzer ON/OFF.

---

## Setup Instructions

1. **Hardware Setup**:
   - Place the ultrasonic sensor and buzzer on a breadboard.
   - Use jumper wires to connect the components to the Arduino as per the pin configuration table above.
   - Ensure proper power supply connections to the ultrasonic sensor and buzzer (5V and GND).

2. **Arduino IDE Setup**:
   - Open the Arduino IDE on your computer.
   - Connect your Arduino board to the computer using a USB cable.
   - Paste the code from the file given in this Repo into the IDE.
   - Select the correct board and port:
     - Go to `Tools > Board` and select your Arduino board (e.g., Arduino Uno).
     - Go to `Tools > Port` and select the appropriate COM port.

3. **Upload the Code**:
   - Click on the **Upload** button to upload the code to your Arduino.

4. **Monitor Water Levels**:
   - Open the **Serial Monitor** in the Arduino IDE (`Tools > Serial Monitor`) to observe real-time water level readings and flood alerts.
   - Set the baud rate to `9600`.

---

## How It Works
1. The ultrasonic sensor continuously measures the distance to the water surface.
2. If the measured distance is less than the `floodThreshold` (e.g., 20 cm), the system:
   - Activates the buzzer.
   - Displays a "Flood Detected" message on the Serial Monitor.
3. If the distance is greater than the threshold, the system:
   - Deactivates the buzzer.
   - Displays a "Water Level Safe" message.

---

## Example Output
When running, the **Serial Monitor** will display:

