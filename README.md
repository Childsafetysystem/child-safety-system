<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Methodology - Child Safety System</title>
    <style>
        /* Academic Style */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background-color: #f5f7fa;
            font-family: 'Arial', 'Helvetica Neue', sans-serif;
            padding: 40px 20px;
            color: #1e2a41;
        }

        .container {
            max-width: 1100px;
            margin: 0 auto;
            background: white;
            padding: 50px 60px;
            border-radius: 12px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.08);
            line-height: 1.6;
        }

        h1 {
            font-size: 28px;
            font-weight: bold;
            text-align: center;
            margin-bottom: 30px;
            color: #0a1a3a;
            border-bottom: 3px solid #2a6b9c;
            padding-bottom: 15px;
        }

        h2 {
            font-size: 22px;
            font-weight: bold;
            margin-top: 40px;
            margin-bottom: 18px;
            color: #10345e;
            border-left: 6px solid #2a6b9c;
            padding-left: 15px;
        }

        h3 {
            font-size: 18px;
            font-weight: bold;
            margin-top: 28px;
            margin-bottom: 12px;
            color: #1a4a7a;
        }

        h4 {
            font-size: 16px;
            font-weight: bold;
            margin-top: 20px;
            margin-bottom: 8px;
            color: #1e5a8a;
        }

        p {
            margin-bottom: 16px;
            text-align: justify;
        }

        ul, ol {
            margin: 10px 0 20px 25px;
        }

        li {
            margin-bottom: 6px;
        }

        table {
            width: 100%;
            border-collapse: collapse;
            margin: 20px 0 30px;
            font-size: 14px;
        }

        th {
            background-color: #1e3a5f;
            color: white;
            font-weight: bold;
            padding: 12px 10px;
            text-align: center;
            border: 1px solid #2c4d74;
        }

        td {
            border: 1px solid #d0d8e5;
            padding: 10px 12px;
            vertical-align: middle;
            background-color: white;
        }

        tr:nth-child(even) td {
            background-color: #f8faff;
        }

        .diagram-box {
            background-color: #f8faff;
            border: 1px solid #d0d8e5;
            border-radius: 8px;
            padding: 20px;
            margin: 20px 0;
            text-align: center;
            font-family: 'Courier New', monospace;
            font-size: 14px;
            overflow-x: auto;
            white-space: pre;
            line-height: 1.8;
        }

        .highlight-box {
            background-color: #f0f5fe;
            border-left: 5px solid #2a6b9c;
            padding: 15px 20px;
            margin: 25px 0;
            border-radius: 4px;
            font-family: 'Courier New', monospace;
            font-size: 14px;
            white-space: pre-wrap;
            word-break: break-word;
        }

        @media (max-width: 768px) {
            .container {
                padding: 20px 15px;
            }
            table {
                font-size: 12px;
            }
            th, td {
                padding: 6px 4px;
            }
            .diagram-box {
                font-size: 11px;
                padding: 12px;
                white-space: pre-wrap;
                word-break: break-all;
            }
            h1 {
                font-size: 22px;
            }
            h2 {
                font-size: 19px;
            }
        }

        @media print {
            body { background: white; padding: 0; }
            .container { box-shadow: none; padding: 30px; }
        }

        hr {
            margin: 30px 0 20px;
            border: 0;
            border-top: 2px dashed #ccd7e6;
        }
    </style>
</head>
<body>
<div class="container">

    <h1>3.0 METHODOLOGY</h1>

    <!-- ============================================================ -->
    <h2>3.1 Introduction</h2>
    <p>The methodology used in this project covers the process of designing, building, and testing the in-vehicle child safety system. This project follows a <strong>prototype design and development approach</strong>, which involves component selection, circuit assembly, firmware development, and functional &amp; performance testing. This approach was chosen because it allows the researcher to develop the system in stages and test each module individually before full integration.</p>

    <!-- ============================================================ -->
    <h2>3.2 Materials and Components</h2>

    <h3>3.2.1 Component List</h3>
    <table>
        <thead>
            <tr><th>No.</th><th>Component</th><th>Function</th><th>Quantity</th></tr>
        </thead>
        <tbody>
            <tr><td>1</td><td>ESP32 Development Board</td><td>Main microcontroller</td><td>1</td></tr>
            <tr><td>2</td><td>LD2410C 24GHz Radar Sensor</td><td>Detects human presence (stationary/moving)</td><td>1</td></tr>
            <tr><td>3</td><td>10kg Load Cell + HX711 Amplifier</td><td>Measures occupant weight (display only)</td><td>1 set</td></tr>
            <tr><td>4</td><td>SHT31 Sensor</td><td>Measures cabin temperature &amp; humidity</td><td>1</td></tr>
            <tr><td>5</td><td>PS-3150 Magnetic Door Sensor (NC)</td><td>Detects door open/closed status</td><td>1</td></tr>
            <tr><td>6</td><td>A7670C 4G LTE Module</td><td>Sends Telegram notifications</td><td>1</td></tr>
            <tr><td>7</td><td>Buzzer (5V Active)</td><td>Provides local audible alarm</td><td>1</td></tr>
            <tr><td>8</td><td>LED</td><td>Provides visual alarm</td><td>1</td></tr>
            <tr><td>9</td><td>18650 Batteries (2 x 3.7V)</td><td>Power source</td><td>2</td></tr>
            <tr><td>10</td><td>LM2596 Buck Converter</td><td>Regulates voltage to 5V</td><td>1</td></tr>
            <tr><td>11</td><td>Jumper Wires</td><td>Circuit connections</td><td>Set</td></tr>
        </tbody>
    </table>

    <!-- ============================================================ -->
    <h2>3.3 System Design</h2>

    <h3>3.3.1 System Overview</h3>
    <p>The system is divided into three (3) main layers:</p>
    <ol>
        <li><strong>Detection Layer</strong> – Collects data from all sensors.</li>
        <li><strong>Processing Layer</strong> – ESP32 processes data and makes decisions.</li>
        <li><strong>Action Layer</strong> – Sends notifications and activates the buzzer.</li>
    </ol>

    <div class="diagram-box">
┌─────────────────────────────────────────────────────────────────┐
│                      DETECTION LAYER                           │
├───────────┬───────────┬───────────┬───────────┬───────────────┤
│  Load Cell│   Radar   │   SHT31   │   Door    │   4G Module   │
│  (Weight) │ (Presence)│ (Temp.)   │  (Door)   │   (Telegram)  │
└─────┬─────┴─────┬─────┴─────┬─────┴─────┬─────┴───────────────┘
      │           │           │           │
      ▼           ▼           ▼           ▼
┌─────────────────────────────────────────────────────────────────┐
│                   PROCESSING LAYER (ESP32)                     │
│  ┌──────────────────────────────────────────────────────────┐  │
│  │  1. Read all sensor data                                │  │
│  │  2. Logic: Radar = Child Presence                       │  │
│  │  3. If temp ≥ 40°C AND door closed → ALARM             │  │
│  └──────────────────────────────────────────────────────────┘  │
└─────────────────────────────────────────────────────────────────┘
      │           │           │           │
      ▼           ▼           ▼           ▼
┌──────────┐ ┌──────────┐ ┌──────────┐ ┌──────────────────────┐
│ Telegram │ │  Buzzer  │ │   LED    │ │   Serial Monitor     │
│  (4G)    │ │ (Audio)  │ │ (Visual) │ │   (Debugging)        │
└──────────┘ └──────────┘ └──────────┘ └──────────────────────┘
    </div>

    <h3>3.3.2 System Flowchart</h3>
    <div class="diagram-box">
                    ┌─────────────────────────────┐
                    │          START              │
                    │         ESP32 ON           │
                    └──────────────┬──────────────┘
                                   │
                                   ▼
                    ┌─────────────────────────────┐
                    │      INITIALIZE SENSORS     │
                    │   (Radar/Load Cell/SHT31/   │
                    │    Door/4G)                 │
                    └──────────────┬──────────────┘
                                   │
                                   ▼
                    ┌─────────────────────────────┐
                    │        ENGINE OFF?          │
                    └──────────────┬──────────────┘
                                   │
                         ┌─────────┴─────────┐
                        NO                   YES
                         │                    │
                         │                    ▼
                         │     ┌─────────────────────────────┐
                         │     │       DOOR CLOSED?          │
                         │     └──────────────┬──────────────┘
                         │                    │
                         │          ┌─────────┴─────────┐
                         │         NO                   YES
                         │          │                    │
                         │          │                    ▼
                         │          │     ┌─────────────────────────────┐
                         │          │     │    RADAR DETECTED?         │
                         │          │     └──────────────┬──────────────┘
                         │          │                    │
                         │          │          ┌─────────┴─────────┐
                         │          │         NO                   YES
                         │          │          │                    │
                         │          │          │                    ▼
                         │          │          │     ┌─────────────────────────────┐
                         │          │          │     │     CHILD PRESENT           │
                         │          │          │     │     ✅ Child Detected       │
                         │          │          │     └──────────────┬──────────────┘
                         │          │          │                    │
                         │          │          │                    ▼
                         │          │          │     ┌─────────────────────────────┐
                         │          │          │     │  SEND TELEGRAM NOTIFICATION │
                         │          │          │     │   "Child in vehicle"        │
                         │          │          │     └──────────────┬──────────────┘
                         │          │          │                    │
                         │          │          │                    ▼
                         │          │          │     ┌─────────────────────────────┐
                         │          │          │     │   READ TEMPERATURE          │
                         │          │          │     └──────────────┬──────────────┘
                         │          │          │                    │
                         │          │          │                    ▼
                         │          │          │     ┌─────────────────────────────┐
                         │          │          │     │  TEMPERATURE ≥ 40°C?       │
                         │          │          │     └──────────────┬──────────────┘
                         │          │          │                    │
                         │          │          │          ┌─────────┴─────────┐
                         │          │          │         NO                   YES
                         │          │          │          │                    │
                         │          │          │          │                    ▼
                         │          │          │          │     ┌─────────────────────────────┐
                         │          │          │          │     │   ACTIVATE BUZZER           │
                         │          │          │          │     │   Send Emergency Alert      │
                         │          │          │          │     └──────────────┬──────────────┘
                         │          │          │          │                    │
                         └──────────┴──────────┴──────────┴────────────────────┘
                                                                      │
                                                                      ▼
                                                    ┌─────────────────────────────┐
                                                    │    CONTINUE MONITORING      │
                                                    │   UNTIL ESP32 POWER OFF     │
                                                    └─────────────────────────────┘
    </div>

    <!-- ============================================================ -->
    <h2>3.4 Circuit Assembly</h2>

    <h3>3.4.1 Wiring Diagram</h3>
    <div class="diagram-box">
┌─────────────────────────────────────────────────────────────────────────────┐
│                       Two 18650 Batteries (Series 7.4V)                    │
│                              ┌───────┼───────┐                            │
│                              │  +    │    -  │                            │
│                              └───┬───┴───┬───┘                            │
│                                  │       │                                │
│                                  ▼       ▼                                │
│                           ┌─────────────────────┐                         │
│                           │  Buck Converter     │                         │
│                           │  (LM2596)           │                         │
│                           │  Output: 5V / 3A    │                         │
│                           └──────────┬──────────┘                         │
│                                      │                                     │
│                                  5V  │  GND                               │
│                          ┌───────────┼───────────┐                        │
│                          │           │           │                        │
│                          ▼           ▼           ▼                        │
│  ┌───────────────────────────────────────────────────────────────────┐    │
│  │                          ESP32 Development Board                  │    │
│  │  ┌─────────────────────────────────────────────────────────────┐ │    │
│  │  │  VIN  ←── 5V (from Buck Converter)                          │ │    │
│  │  │  GND  ←── GND                                               │ │    │
│  │  │  GPIO2  ←── LD2410C OUT                                     │ │    │
│  │  │  GPIO13 ←── HX711 DT                                        │ │    │
│  │  │  GPIO14 ←── HX711 SCK                                       │ │    │
│  │  │  GPIO22 ←── SHT31 SCL                                       │ │    │
│  │  │  GPIO21 ←── SHT31 SDA                                       │ │    │
│  │  │  GPIO25 ←── Door Sensor                                     │ │    │
│  │  │  GPIO23 →── Buzzer Signal                                   │ │    │
│  │  │  GPIO26 →── A7670C RX                                       │ │    │
│  │  │  GPIO27 ←── A7670C TX                                       │ │    │
│  │  │  GPIO4  →── A7670C PWRKEY                                   │ │    │
│  │  └─────────────────────────────────────────────────────────────┘ │    │
│  └───────────────────────────────────────────────────────────────────┘    │
    </div>

    <h3>3.4.2 Pin Connection Table</h3>
    <table>
        <thead>
            <tr><th>Module</th><th>Pin</th><th>→</th><th>ESP32 Pin</th></tr>
        </thead>
        <tbody>
            <tr><td rowspan="4"><strong>LD2410C</strong></td><td>VCC</td><td>→</td><td>VIN (5V)</td></tr>
            <tr><td>GND</td><td>→</td><td>GND</td></tr>
            <tr><td>OUT</td><td>→</td><td>GPIO2</td></tr>
            <tr><td>TX/RX</td><td>→</td><td>Not Connected</td></tr>
            <tr><td rowspan="4"><strong>HX711</strong></td><td>VCC</td><td>→</td><td>3.3V</td></tr>
            <tr><td>GND</td><td>→</td><td>GND</td></tr>
            <tr><td>DT</td><td>→</td><td>GPIO13</td></tr>
            <tr><td>SCK</td><td>→</td><td>GPIO14</td></tr>
            <tr><td rowspan="4"><strong>SHT31</strong></td><td>VCC</td><td>→</td><td>3.3V</td></tr>
            <tr><td>GND</td><td>→</td><td>GND</td></tr>
            <tr><td>SCL</td><td>→</td><td>GPIO22</td></tr>
            <tr><td>SDA</td><td>→</td><td>GPIO21</td></tr>
            <tr><td><strong>Door Sensor</strong></td><td>One End</td><td>→</td><td>GND</td></tr>
            <tr><td></td><td>Other End</td><td>→</td><td>GPIO25</td></tr>
            <tr><td rowspan="3"><strong>Buzzer</strong></td><td>VCC</td><td>→</td><td>5V</td></tr>
            <tr><td>GND</td><td>→</td><td>GND</td></tr>
            <tr><td>Signal</td><td>→</td><td>GPIO23</td></tr>
            <tr><td rowspan="4"><strong>A7670C</strong></td><td>VCC</td><td>→</td><td>External 5V</td></tr>
            <tr><td>GND</td><td>→</td><td>GND</td></tr>
            <tr><td>TX</td><td>→</td><td>GPIO27</td></tr>
            <tr><td>RX</td><td>→</td><td>GPIO26</td></tr>
            <tr><td></td><td>PWRKEY</td><td>→</td><td>GPIO4</td></tr>
        </tbody>
    </table>

    <!-- ============================================================ -->
    <h2>3.5 Firmware Development</h2>

    <h3>3.5.1 Development Platform</h3>
    <p>The firmware was developed using the <strong>Arduino IDE</strong> with C++ programming language. The ESP32 was chosen as the main microcontroller because it offers:</p>
    <ul>
        <li>Dual-core processing for simultaneous sensor handling</li>
        <li>Wi-Fi and Bluetooth support (not used in this version)</li>
        <li>Sufficient I/O pins for all sensors</li>
        <li>Affordable cost and large community support</li>
    </ul>

    <h3>3.5.2 Core Logic (Pseudo-code)</h3>
    <div class="highlight-box">
SETUP:
  - Initialize Serial (115200 baud)
  - Initialize Radar (OUT pin mode)
  - Initialize Load Cell (tare)
  - Initialize SHT31 (I2C)
  - Initialize Door Sensor (pull-up)
  - Initialize 4G Module (A7670C)

LOOP (every 2 seconds):
  - READ: radar status (HIGH/LOW)
  - READ: weight (kg) - display only
  - READ: temperature (°C)
  - READ: door status (Closed/Open)

  - SET: childPresent = radarDetected

  - PRINT: all sensor values to Serial Monitor

  - IF: childPresent == YES AND doorClosed == YES AND temperature >= 40°C
    - ACTIVATE: buzzer
    - SEND: Telegram emergency alert (every 15 seconds)
  - ELSE
    - DEACTIVATE: buzzer
    - RESET: alert timer
    </div>

    <!-- ============================================================ -->
    <h2>3.6 Testing Procedure</h2>

    <h3>3.6.1 Individual Component Tests</h3>
    <table>
        <thead>
            <tr><th>No.</th><th>Test</th><th>Procedure</th><th>Success Criteria</th></tr>
        </thead>
        <tbody>
            <tr><td>1</td><td>Radar</td><td>Place hand in front of radar</td><td>OUT pin = HIGH</td></tr>
            <tr><td>2</td><td>Load Cell</td><td>Place 2kg weight</td><td>Reading ≈ 2.0 kg</td></tr>
            <tr><td>3</td><td>SHT31</td><td>Compare with thermometer</td><td>Within ±0.5°C</td></tr>
            <tr><td>4</td><td>Door Sensor</td><td>Open/close door</td><td>Status changes</td></tr>
            <tr><td>5</td><td>Buzzer</td><td>Call digitalWrite(HIGH)</td><td>Sound heard</td></tr>
            <tr><td>6</td><td>4G Module</td><td>Send AT command</td><td>"OK" response</td></tr>
        </tbody>
    </table>

    <h3>3.6.2 Integration Tests</h3>
    <table>
        <thead>
            <tr><th>No.</th><th>Test</th><th>Procedure</th><th>Success Criteria</th></tr>
        </thead>
        <tbody>
            <tr><td>1</td><td>Child Detection</td><td>Place hand in front of radar</td><td>"CHILD: YES" on Serial Monitor</td></tr>
            <tr><td>2</td><td>Temperature Alert</td><td>Heat SHT31 to 40°C</td><td>Buzzer sounds</td></tr>
            <tr><td>3</td><td>Notification</td><td>Check Telegram</td><td>Message received within 5-10s</td></tr>
            <tr><td>4</td><td>Full System</td><td>All sensors active</td><td>No pin/power conflicts</td></tr>
        </tbody>
    </table>

    <!-- ============================================================ -->
    <h2>3.7 Gantt Chart</h2>
    <table>
        <thead>
            <tr><th>Activity</th><th>Week 1</th><th>Week 2</th><th>Week 3</th><th>Week 4</th><th>Week 5</th><th>Week 6</th></tr>
        </thead>
        <tbody>
            <tr><td>Literature Review</td><td>████████</td><td></td><td></td><td></td><td></td><td></td></tr>
            <tr><td>Component Selection</td><td>████████</td><td>████████</td><td></td><td></td><td></td><td></td></tr>
            <tr><td>Circuit Assembly</td><td></td><td>████████</td><td>████████</td><td></td><td></td><td></td></tr>
            <tr><td>Code Development</td><td></td><td></td><td>████████</td><td>████████</td><td></td><td></td></tr>
            <tr><td>Component Testing</td><td></td><td></td><td></td><td>████████</td><td>████████</td><td></td></tr>
            <tr><td>Integration Testing</td><td></td><td></td><td></td><td></td><td>████████</td><td>████████</td></tr>
            <tr><td>Documentation</td><td>████████</td><td>████████</td><td>████████</td><td>████████</td><td>████████</td><td>████████</td></tr>
        </tbody>
    </table>

    <hr>
    <p style="text-align: right; font-style: italic; color: #1e3a5f;">— End of Methodology Section —</p>

</div>
</body>
</html>
