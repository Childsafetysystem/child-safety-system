# Child Safety System - Methodology

## 3.0 METHODOLOGY

### 3.1 Introduction

in this project covers the process of designing, building, and testing the in-vehicle child safety system. This project follows a **prototype design and development approach**, which involves component selection, circuit assembly, firmware development, and functional & performance testing. This approach was chosen because it allows the researcher to develop the system in stages and test each module individually before full integration.

---

### 3.2 Materials and Components

#### 3.2.1 Component List

| No. | Component | Function | Quantity |
|-----|-----------|----------|----------|
| 1 | ESP32 Development Board | Main microcontroller | 1 |
| 2 | LD2410C 24GHz Radar Sensor | Detects human presence (stationary/moving) | 1 |
| 3 | 10kg Load Cell + HX711 Amplifier | Measures occupant weight (display only) | 1 set |
| 4 | SHT31 Sensor | Measures cabin temperature & humidity | 1 |
| 5 | PS-3150 Magnetic Door Sensor (NC) | Detects door open/closed status | 1 |
| 6 | A7670C 4G LTE Module | Sends Telegram notifications | 1 |
| 7 | Buzzer (5V Active) | Provides local audible alarm | 1 |
| 8 | LED | Provides visual alarm | 1 |
| 9 | 18650 Batteries (2 x 3.7V) | Power source | 2 |
| 10 | LM2596 Buck Converter | Regulates voltage to 5V | 1 |
| 11 | Jumper Wires | Circuit connections | Set |

---

### 3.3 System Design

#### 3.3.1 System Overview

The system is divided into three (3) main layers:

1. **Detection Layer** – Collects data from all sensors.
2. **Processing Layer** – ESP32 processes data and makes decisions.
3. **Action Layer** – Sends notifications and activates the buzzer.
