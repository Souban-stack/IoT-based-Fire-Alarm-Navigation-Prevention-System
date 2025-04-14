# 🔥 Automated Fire Alarm Prevention and Navigation System

![Fire Detection Banner](https://via.placeholder.com/1200x400?text=Automated+Fire+Prevention+System)

## 📌 Overview
This project is an **IoT-based fire detection and suppression system** designed to improve the shortcomings of traditional fire alarm setups. It uses a **multi-sensor grid** to detect smoke and elevated temperatures, activates **localized water pumps** through relays, and transmits real-time alerts via **ESP32** to a **mobile app**.

Built using **Arduino UNO, ESP32, MQ2 smoke sensors, and DS18B20 temperature sensors**, the system minimizes water waste by activating only the pump in the affected sector.

---

## 🚨 Key Features

- 🔥 **Localized Detection** using 2x2 sensor-pump grid (4 zones)
- 📲 **Real-time Alerts** through ESP32 to mobile application
- 💧 **Zone-wise Suppression** using 4 individual 12V pumps
- 🌡️ **Multi-Sensor Input**: MQ2 for smoke, DS18B20 for temperature
- 🧠 Microcontroller-based automation (Arduino UNO + ESP32)
- 🗄️ Logs incidents with timestamp and sensor data

---

## 🔧 Hardware Components

| Component         | Quantity |
|------------------|----------|
| Arduino UNO       | 1        |
| ESP32             | 1        |
| MQ2 Smoke Sensor  | 4        |
| DS18B20 Temp Sensor | 4      |
| 5V Relay Module (4-channel) | 1 |
| 12V Water Pumps   | 4        |
| HW-131 Power Supply Module | 1 |
| Chassis, Breadboard, Wires | - |

---

## 🧩 System Flow (Logic)

```plaintext
1. Sensors take readings every second.
2. If both smoke and temp exceed threshold in a zone:
    → Relay turns ON that zone’s pump.
    → ESP32 sends alert + data to mobile app.
3. After 15 seconds, if safe:
    → Pump turns OFF.
    → Alert stops.
    → Event logged (timestamp + data).
