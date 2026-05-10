<p align="center">

  <img src="https://github.com/user-attachments/assets/10468453-7709-4604-9bee-8ad757b704ef" alt="Project Logo" width="200" style="border-radius:10px;"/>
</p>

<h1 align="center">SURE ProEd</h1>
<h3 align="center">Skill Upgradation for Rural Youth Empowerment Trust</h3>

<p align="center">
  <strong>Multi-Sensor IoT Environmental Hazard Monitoring System</strong>
</p>

<br>

## 👨‍🎓 Student Details

- **Name:** P. Purushotham
- **Course Opted:** Embedded Systems & IoT
- **Instructor/Guide Name:** Ms. Mehak Majeed
- **Duration:** 6 Months
- **Organization:** SURE Trust, Puttaparthi, Andhra Pradesh

---

## 🛠️ Technologies & Tools Used

![C++](https://img.shields.io/badge/C++-00599C?style=for-the-badge&logo=c%2B%2B&logoColor=white)
![ESP32](https://img.shields.io/badge/ESP32-E7352C?style=for-the-badge&logo=espressif&logoColor=white)
![Arduino IDE](https://img.shields.io/badge/Arduino_IDE-00979D?style=for-the-badge&logo=arduino&logoColor=white)
![Firebase](https://img.shields.io/badge/Firebase-FFCA28?style=for-the-badge&logo=firebase&logoColor=white)
![JSON](https://img.shields.io/badge/JSON-000000?style=for-the-badge&logo=json&logoColor=white)
![IoT](https://img.shields.io/badge/Internet_of_Things-4B0082?style=for-the-badge&logo=smartthings&logoColor=white)

---

## 📝 Project Overview

This project presents a highly reliable, edge-to-cloud environmental hazard monitoring system using an **ESP32 microcontroller**. Unlike standard binary alarms, this system evaluates compound environmental anomalies (combustible gas, thermal spikes, and optical smoke obscuration) in real-time. It features **100% offline human voice alerts** using direct DAC processing and securely pushes telemetry to a **Firebase Realtime Database** for remote dashboard monitoring.

## 🚀 Key Technical Features

- **🧠 Context-Aware Risk Scoring:** Replaces false-positive prone binary alarms with a dynamic, normalized risk algorithm: $S = 0.70G + 0.20T + 0.10L$.
- **🔊 Offline DAC Voice Alerts:** Bypasses external MP3 modules by pushing PROGMEM hex audio arrays directly through the ESP32’s internal 8-bit DAC to a PAM8403 Class-D amplifier.
- **⚡ Dual-Core Execution:** Utilizes native FreeRTOS to pin the non-blocking polling loop to Core 1, while the Wi-Fi stack and cloud telemetry run on Core 0.
- **☁️ Secure Cloud Telemetry:** Implements HTTPS/TLS encryption to push JSON payloads asynchronously to Firebase RTDB for real-time web dashboard visualization.

---

## 🧩 Hardware Architecture

- **Microcontroller:** ESP32-WROOM-32 Development Board
- **Gas/Smoke Sensing:** MQ-2 Sensor (Tin Dioxide Chemiresistor)
- **Thermal Sensing:** DHT11 Temperature & Humidity Sensor
- **Optical Sensing:** GL5528 Light Dependent Resistor (LDR)
- **Audio Output:** PAM8403 3W Amplifier + 8-Ohm Loudspeaker
- **Visual Feedback:** Status LEDs & Protection Resistors

---

## ⚙️ Operational Workflow

1. **Acquisition:** A non-blocking `millis()` loop samples the MQ-2, DHT11, and LDR every 5 seconds.
2. **Evaluation:** Data is Min-Max normalized and passed through the weighted risk algorithm. Extreme absolute limits (e.g., Temp > 40°C) trigger hardware boundary overrides.
3. **Local Action:** If a hazard is detected, the ESP32 physically speaks an evacuation warning via the connected loudspeaker—guaranteed to operate even during total Wi-Fi failure.
4. **Cloud Sync:** The system pushes the updated state and sensor telemetry to Firebase, instantly reflecting on the remote Angular dashboard.

---

## 🌍 Real-World Applications

- **🏭 Industrial Safety:** Detects combustible methane and chemical leaks on factory floors prior to centralized alarm activation.
- **🏠 Smart Homes:** Replaces standard piercing buzzers with clear voice alerts for sleeping occupants during LPG leaks.
- **⛏️ Confined Spaces:** Protects underground mining teams where network connectivity is zero, relying on the ESP32's edge-computing capabilities.

---

## 🔮 Future Enhancements

- **Multi-Gas Discrimination:** Integrating MQ-4 and MQ-7 sensors to accurately separate carbon monoxide from generic smoke.
- **Mobile Push Alerts:** Implementing Firebase Cloud Messaging (FCM) to trigger instant notifications on mobile devices.
- **Predictive AI:** Utilizing historical cloud data to train LSTM neural networks for proactive hazard prediction before critical thresholds are breached.

---

## 🤝 Acknowledgments

I would like to express my deepest gratitude to **Prof. Radhakumari Challa**, Executive Director and Founder of SURE Trust, for providing this incredible platform. Special thanks to my mentor and guide, **Ms. Mehak Majeed**, for her invaluable technical guidance, continuous support, and encouragement throughout this 6-month journey.
