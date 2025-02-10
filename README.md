# ESP8266 & Arduino Uno Radar System

## Overview

This project integrates **ESP8266 NodeMCU** and **Arduino Uno** to create a **radar-based monitoring system** using an **HC-SR04 ultrasonic sensor, SG90 microservo, Wheatstone bridge with a photoresistor, and a 1602 LCD display**. The system visualizes distance measurements using an HTML-based radar animation while also enabling synchronization via a **photoresistor-based detection system**.

Additionally, the **ESP8266 NodeMCU can send HTTP requests to a server**, allowing **further functionalities** like **USB camera activation and cloud recording**.

---

## Features

- **ESP8266 NodeMCU**
  - Reads **HC-SR04 ultrasonic sensor** data.
  - Displays distance values on a **1602 LCD display**.
  - Synchronizes with the radar system via a **photoresistor detection mechanism**.
  - Controls an **LED** mounted on the **SG90 servo motor**.
  - Sends **HTTP requests** to trigger server-based actions (e.g., USB camera recording).

- **Arduino Uno**
  - Controls the **SG90 servo motor** for radar movement.
  - Monitors the **Wheatstone bridge** circuit with **three 10k resistors and a photoresistor**.
  - Detects LED pulses from the servo-mounted LED and sends a **voltage-divided signal** to **ESP8266** for radar synchronization.

- **Radar Visualization**
  - HTML + CSS-based **animated radar UI**.
  - The **radar pointer** synchronizes with the **servo movement**.
  - Distance detection is **visually represented**.

---

## Hardware Components

| Component              | Function |
|------------------------|----------|
| **ESP8266 NodeMCU**    | Handles distance measurement, LCD display, and server communication. |
| **Arduino Uno**        | Controls the servo and photoresistor detection. |
| **HC-SR04**           | Measures distance to obstacles. |
| **1602 LCD Display**   | Shows distance readings in real-time. |
| **SG90 Servo Motor**   | Rotates the radar system. |
| **LED Diode**         | Used for synchronization via the photoresistor. |
| **Photoresistor**      | Detects LED pulses for precise radar synchronization. |
| **Wheatstone Bridge**  | Used with resistors for voltage-based signal transmission. |

---

## Installation & Setup

### 1️⃣ Wiring Connections

- **ESP8266 NodeMCU:**
  - **HC-SR04 Trig** → **D3 (GPIO 0)**
  - **HC-SR04 Echo** → **D4 (GPIO 2)**
  - **1602 LCD RS** → **D1 (GPIO 5)**
  - **LCD Enable** → **D2 (GPIO 4)**
  - **LCD D4-D7** → **D5-D8 (GPIO 14, 12, 13, 15)**
  - **LED (Sync)** → **D0 (GPIO 16)**
  - **Sync Input (from Arduino)** → **A0**

- **Arduino Uno:**
  - **Servo SG90** → **D9**
  - **Photoresistor (Voltage Divider)** → **A0**
  - **Control Signal Output** → **D7**

### 2️⃣ Uploading Code

- **ESP8266 Code**: Upload `kod_za_radar.txt` using the **Arduino IDE** with the **ESP8266 board library** installed.
- **Arduino Uno Code**: Upload `UNO_servo_and_bridge.txt` using **Arduino IDE**.

### 3️⃣ Running the System

1. **Power Up** ESP8266 and Arduino.
2. The **servo begins scanning**, LED turns on when detecting an object.
3. **ESP8266 receives sync signal** from the photoresistor and **updates the radar display**.
4. Distance values appear on the **LCD display**.
5. Radar visualization in **test.html** syncs with the actual system.

---

## Radar Visualization (HTML)

The `test.html` file provides a **web-based radar animation** that simulates real-time scanning. The **radar needle synchronizes with the ESP8266 readings** and displays **distance information**.

To run the radar UI:

1. Open `test.html` in a **web browser**.
2. Ensure ESP8266 **sends data to the webpage** (further implementation needed for WebSockets or HTTP updates).

---

## Future Enhancements

✅ Implement **server-side control** for:
- USB Camera activation upon object detection.
- Cloud recording triggered by ESP8266.
- WebSocket-based **live data streaming** for improved radar updates.

✅ **Improve synchronization** between the **physical system and radar UI** using real-time **WebSockets** instead of static HTML animations.

---

## Contributions

Feel free to contribute to this project by:
1. Forking the repository.
2. Submitting pull requests for new features.
3. Reporting bugs and suggesting improvements.

---

## License

This project is open-source and licensed under the **MIT License**.

---

🎯 **Status**: *Work in Progress (WIP)* 🚀

---
