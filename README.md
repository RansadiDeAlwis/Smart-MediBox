# 🧠 Smart MediBox

## 📌 Introduction

**Smart MediBox** is an intelligent pharmaceutical storage solution developed using ESP32 and embedded systems technologies. This project was completed in **two phases**:

- **Phase 1**: Programming Assignment 1 – focused on building a basic medicine reminder system with alarm and environmental monitoring features.
- **Phase 2**: Programming Assignment 2 – extended the project by integrating dynamic light control, servo motor adjustment, and real-time dashboard visualization via Node-RED.

---

## 🧭 System Overview

The MediBox combines hardware and software to support:

- Timely medication reminders
- Continuous monitoring of environmental conditions
- Light sensitivity management for medicine storage
- A responsive UI and remote dashboard integration

---

## ⚙️ Core Functionalities

### ✅ Phase 1: Basic Features (Assignment 1)
- **Time Synchronization** via NTP with time zone configuration
- **Alarm Management**: Set, view, delete, and snooze alarms
- **OLED Display**: Shows current time, active alarms, and warning messages
- **Alarm Notification**: Audible alerts using a buzzer
- **Environmental Monitoring**:
  - Monitors temperature and humidity using DHT11
  - Alerts if out of healthy range (24°C–32°C, 65%–80% RH)

### ✅ Phase 2: Advanced Features (Assignment 2)
- **Light Intensity Monitoring**:
  - Uses LDR sensors
  - Configurable sampling and update intervals (default: 5s & 2min)
  - Normalized values (0–1) sent to Node-RED dashboard
- **Servo Motor Controlled Shaded Window**:
  - Adjusts based on light and temperature using a custom equation
  - User-configurable parameters:  
    - Minimum angle (θoffset)  
    - Controlling factor (γ)  
    - Ideal temperature (Tmed)
- **Node-RED Dashboard**:
  - Realtime plots, gauges, and sliders for parameter control
  - Remote monitoring and adjustments via MQTT

---

## 🏗️ Software Architecture

### 1. **Hardware Abstraction Layer**
- Encapsulates OLED, buttons, buzzer, LDR, DHT11, and servo motor

### 2. **Sensor Management**
- Collects, processes, and transmits temperature, humidity, and light intensity

### 3. **Alarm Management**
- Schedules, triggers, and manages alarms with persistent storage

### 4. **Time Management**
- NTP-based clock with user-settable time zones and backup storage

### 5. **User Interface**
- Menu-driven OLED interface navigated via push buttons

### 6. **Communication Layer**
- MQTT-based data exchange with Node-RED
- Subscribes to control topics and publishes sensor readings

---

## 📊 Node-RED Dashboard Features

- Real-time intensity graph & latest value
- Sliders for:
  - Sampling Interval (ts)
  - Sending Interval (tu)
  - θoffset (0°–120°)
  - γ (0–1)
  - Tmed (10–40°C)

Access the dashboard via:  
`http://localhost:1880/ui`

---

## 🧰 Hardware Components

- ESP32 Development Board
- OLED Display (SSD1306)
- Buzzer
- Push Buttons
- LDR Sensors
- DHT11 Temperature & Humidity Sensor
- Servo Motor (for shaded sliding window)

---

## 💻 Software Requirements

- [Arduino IDE](https://www.arduino.cc/en/software)
- [Node-RED](https://nodered.org/)
- MQTT Broker: [test.mosquitto.org](https://test.mosquitto.org/)
- [Wokwi Simulator](https://wokwi.com/)
- VS Code (recommended for editing)

---

## 🚀 Installation Guide

### 🔧 Hardware Setup
- Wire components as per port map (refer to `circuit_diagram.jpg` or schematic)

### 🛠️ Software Setup

1. Clone the repository:
   ```bash
   git clone https://github.com/uvinduuu/Smart-Medibox.git
