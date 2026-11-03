# ESP32 BESS Monitoring Gateway

**An IoT-based battery monitoring and fleet management gateway for Battery Energy Storage Systems (BESS).**

## Overview

The ESP32 BESS Monitoring Gateway is a hardware and firmware development project designed to enable remote monitoring, health tracking, fault detection, and security monitoring of battery energy storage systems.

The gateway communicates with compatible Battery Management Systems (BMS) over Bluetooth Low Energy (BLE), collects battery operating parameters, and transmits the information to a cloud-based monitoring platform using Wi-Fi.

The primary objective is to develop a scalable monitoring solution for battery rental systems, Energy Storage as a Service (BaaS), and distributed energy storage applications.

## Key Features

- **Wireless BMS Communication:** Acquires battery data through Bluetooth communication.
- **Battery Health Monitoring:** Tracks available battery parameters, including SoC, SoH, voltage, current, and temperature, subject to BMS protocol support.
- **Heartbeat Monitoring:** Detects loss of BMS communication and generates alerts after a configurable timeout (initial target: 5 minutes).
- **Tamper Detection:** Designed to detect gateway removal, communication interruption, and potential battery tampering.
- **Real-Time Monitoring:** Supports a planned live monitoring mode with approximately 2-second updates.
- **Data Logging:** Periodic battery data logging at 5-minute intervals.
- **Cloud Integration:** Sends monitoring data and alerts to a centralized platform.
- **Local Data Buffering:** Maintains temporary data when network connectivity is unavailable.
- **Fleet Management:** Designed to monitor multiple battery packs through a centralized dashboard.

## Hardware

| Component | Specification |
|---|---|
| Microcontroller | ESP32-WROOM-32 |
| Wireless Communication | Wi-Fi + Bluetooth |
| BMS Interface | BLE (protocol dependent) |
| Data Storage | Cloud + Local Buffer |
| Deployment | One gateway per battery pack |

## System Architecture

```text
      Battery Pack
           |
           v
          BMS
           |
           | Bluetooth LE
           v
    ESP32 Monitoring
        Gateway
           |
           | Wi-Fi
           v
      Cloud Platform
           |
           v
    Monitoring Dashboard
           |
           v
       Fleet Management
```

## Security & Monitoring

The system is designed to monitor communication health and identify abnormal gateway or battery communication events.

A communication timeout is intended to trigger an alert. Additional security features include tamper-event detection and remote safety-response integration, subject to compatible BMS command support.

## Data Management

- Periodic logging: 5 minutes.
- Live monitoring target: 2 seconds.
- Planned cloud data retention: 3 months.
- Older records: scheduled deletion during the fourth month.
- Local buffering for temporary network interruptions.

## Development Roadmap

- [x] ESP32-WROOM-32 hardware selection.
- [x] Wi-Fi and Bluetooth architecture planning.
- [ ] BMS Bluetooth protocol investigation.
- [ ] BMS data acquisition and decoding.
- [ ] Battery parameter monitoring.
- [ ] Heartbeat monitoring.
- [ ] Cloud connectivity and data transmission.
- [ ] Local data buffering.
- [ ] Tamper detection and alert system.
- [ ] Centralized fleet dashboard.
- [ ] Remote safety-response integration.

## Long-Term Vision

The long-term objective is to develop an intelligent battery monitoring ecosystem and eventually integrate the monitoring and safety architecture into a proprietary Battery Management System (BMS).

The project aims to contribute towards safer, smarter, and more accessible battery energy storage solutions.

---

**Status:** Research & Development / Prototype

**Platform:** ESP32-WROOM-32

**Application:** Battery Energy Storage Systems (BESS), BaaS, and IoT-based battery fleet monitoring.
