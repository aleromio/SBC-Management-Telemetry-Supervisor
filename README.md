# Smart SBC Power & Telemetry Supervisor

This repository showcases a non-confidential example of an advanced power management and telemetry supervisor designed to protect, monitor, and manage Single Board Computers (SBCs) in demanding automotive and industrial environments.

The system acts as a "Smart UPS" and watchdog, ensuring high availability and safe operation for high-level OS platforms (like Raspberry Pi, Jetson, or similar) deployed in the field.

---

## 🔧 Project Overview

The system acts as an intelligent supervisor responsible for:

- **Graceful Shutdown & Power Control:** Prevents data corruption by managing the SBC's boot and shutdown cycles via MOSFET-based load switching.
- **Embedded UPS:** Integrated Li-Ion battery management to keep the SBC running during vehicle cranking or power loss.
- **Active Watchdog:** Runs a dedicated heartbeat/daemon monitor to detect and recover from SBC OS freezes.
- **Vehicle Telemetry:** Data acquisition via CAN Bus (ECU data) and motion sensing.
- **Real-Time Monitoring:** High-precision V/I (Voltage/Current) and temperature sensing for the SBC and surroundings.
- **Cloud Connectivity:** Reports all telemetry and health metrics to a broker via MQTT.

---

## 👨‍💻 My Role

**End-to-End Embedded System Development:**

- **Hardware architecture:** Design of the power path, MOSFET load switching, and battery management system.
- **Firmware development:** Implementation of the supervisor logic, watchdog protocols, and sensor fusion.
- **Protocol Integration:** CAN Bus decoding, MQTT payload structuring, and I2C/SPI sensor drivers.
- **Power Sequencing:** Logic design for safe startup/shutdown handshaking between the supervisor and the SBC.

---

## 🛠 Technical Stack

**Firmware:**
- **Language:** Embedded C
- **Logic:** State-machine based supervisor for power sequencing.
- **Communication:** MQTT for cloud reporting and Heartbeat protocol for SBC health.

**Hardware & Interfaces:**
- **CAN Bus:** Vehicle ECU and diagnostic data acquisition.
- **Power Management:** MOSFET Load Switching (High-side/Low-side control).
- **Sensors:** Accelerometer (IMU), NTC Temperature monitoring, and V/I sensing.
- **Power Source:** Li-Ion battery charger and automotive-grade power regulation.
- **Connectivity:** MQTT Broker integration for remote telemetry.

**Management Features:**
- **SBC Watchdog:** Hardware-level supervision of the SBC OS status.
- **Power Save Mode:** Advanced low-power logic to preserve vehicle battery.
- **Safety:** Automatic cutoff based on temperature or voltage thresholds.

---

## 🧱 System Architecture Overview
[SBC OS Daemon] ← Heartbeat → [Supervisor Firmware] → [Load Switching MOSFETs]
                                     ↓
                          [CAN Bus / Sensors / Power]
                                     ↓
                               [MQTT Broker]

---

## 📦 Production-Oriented Design Considerations

- **Graceful Handshaking:** Ensures the SBC has finished all disk writes before cutting power.
- **Automotive Reliability:** Protection against transients and voltage drops during engine start.
- **Failsafe Recovery:** Hardware watchdog to force a hard reset if the SBC becomes unresponsive.
- **Telemetry-Driven Maintenance:** MQTT reporting for proactive health monitoring of the fleet.

---

## 📸 Hardware Showcase

Custom supervisor PCB designed for automotive reliability and seamless SBC integration:

![Preview](media/ST1_1.png)
![Preview](media/ST1_2.png)
![Preview](media/ST1_3.png)
![Preview](media/ST1_4.jpeg)
![Preview](media/ST1_5.jpeg)
![Preview](media/ST1_6.jpeg)

---

## 📌 Note

This repository contains only public, non-confidential examples.  
Commercial firmware and proprietary schematics are protected under NDA and are not included.

---

[⬅ Back to Main Portfolio](https://github.com)
