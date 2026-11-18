# CPR-Coach
### A Low-Cost Universal Feedback Add-On for Infant CPR Training

CPR-Coach is a low-cost, sensor-based feedback system designed to assist learners during infant Cardiopulmonary Resuscitation (CPR) training. The project aims to make CPR practice more interactive and informative by providing real-time feedback on compression force and compression rate.

The system is designed as a retrofit module that can be attached to existing infant CPR training mannequins, reducing the need for expensive feedback-enabled training equipment.

---

## 1. Academic Information

| Field | Details |
|---|---|
| Course ID | 21CSC305P |
| Course Name | Machine Learning |
| Department | Computer Science and Engineering |
| Institution | SRM Institute of Science and Technology, Tiruchirappalli |
| Academic Year | 2026–2027 |

## 2. Team Members

| S. No. | Full Name | Register Number | Department | Section | Academic Year |
|---|---|---|---|---|---|
| 1 | Devansh Sharma | RA2411003050035 | CSE | A | 3rd Year |
| 2 | Varadha P. Sajeev | RA2411003050004 | CSE | A | 3rd Year |

## 3. Mentor Details

| Field | Details |
|---|---|
| Mentor Name | Dr. S. Kanaga Subaraja |
| Designation | Head of Department (HOD), Computer Science and Engineering |
| Institution | SRM Institute of Science and Technology, Tiruchirappalli |

---

## 4. Project Overview

Cardiopulmonary Resuscitation (CPR) is an essential emergency procedure that can help save lives during cardiac arrest. Learning the correct CPR technique requires regular practice, particularly when dealing with infants, where appropriate compression technique is especially important.

Traditional CPR training mannequins often provide limited feedback unless they are equipped with specialized monitoring systems. Such equipment can be expensive and may not be accessible to all educational institutions.

CPR-Coach addresses this challenge by introducing an affordable, sensor-based feedback mechanism that can be integrated with existing infant CPR training mannequins.

The system detects applied compression force using a Force Sensitive Resistor (FSR) and processes the sensor readings through an Arduino microcontroller. Feedback is communicated through an OLED display, LED indicators, and an optional buzzer. A Python-based dashboard can also be used to visualize sensor readings and system status.

## 5. Problem Statement

Existing CPR training equipment with real-time feedback capabilities can be expensive and inaccessible to smaller institutions and training centres.

Additionally, learners practicing on conventional mannequins may not receive immediate information about their compression performance.

There is a need for an affordable, portable, and adaptable feedback system that can be incorporated into existing infant CPR training equipment without requiring a complete replacement of the mannequin.

## 6. Objectives

The primary objectives of CPR-Coach are:

- Develop an affordable sensor-based CPR feedback system.
- Measure compression force using a Force Sensitive Resistor.
- Provide real-time feedback regarding compression performance.
- Monitor compression timing and rate.
- Display feedback through an OLED screen and visual indicators.
- Develop an optional Python dashboard for live monitoring.
- Design a retrofit solution compatible with different training mannequins.
- Reduce the cost and complexity of CPR training feedback systems.

## 7. Hardware Requirements

| Component | Purpose |
|---|---|
| Arduino Uno R3 | Main microcontroller for processing sensor data |
| FSR402 Force Sensor | Detects applied compression force |
| OLED Display | Displays real-time feedback |
| LED Indicators | Provides visual feedback |
| Buzzer | Provides optional audio alerts |
| Resistors | Used in the sensor voltage divider circuit |
| Connecting Wires | Establishes electrical connections |
| Breadboard | Used for prototyping and circuit connections |
| USB Cable | Provides power and serial communication |

## 8. Software Requirements

| Software / Technology | Purpose |
|---|---|
| Arduino IDE | Programming and uploading firmware |
| Embedded C/C++ | Microcontroller programming |
| Python | Dashboard development and serial data processing |
| Tkinter | Graphical user interface |
| PySerial | Communication between Arduino and computer |
| Serial Monitor | Debugging and monitoring sensor output |

## 9. System Architecture

The CPR-Coach system consists of three primary stages.

### 9.1 Sensor Input

The FSR402 sensor detects the pressure applied during CPR compressions. Its resistance changes according to the applied force. A voltage divider circuit converts this change into a measurable analog signal.

### 9.2 Data Processing and Feedback

The Arduino Uno R3 reads the sensor values and processes them using predefined thresholds and timing logic.

The processed information is used to determine compression activity and provide feedback through the connected output devices.

### 9.3 Output and Visualization

The system communicates feedback through:

- OLED display for information output.
- LED indicators for visual feedback.
- Buzzer for optional audio alerts.
- Python dashboard for live monitoring and visualization.

### System Flow Diagram

```text
       CPR Compression
              |
              v
       FSR402 Sensor
              |
              v
      Voltage Divider
              |
              v
        Arduino Uno
              |
       Data Processing
              |
       +------+------+
       |      |      |
       v      v      v
      OLED   LEDs  Buzzer
              |
              v
       USB Serial Data
              |
              v
      Python Dashboard
              |
              v
       Live Monitoring
```

## 10. Working Methodology

The working process of CPR-Coach is divided into the following steps:

1. **Pressure Detection:** The FSR402 sensor detects pressure applied during each compression.
2. **Analog Signal Acquisition:** The Arduino reads the analog output generated by the sensor circuit.
3. **Signal Processing:** The microcontroller processes the readings and compares them against predefined thresholds.
4. **Compression Detection:** The system identifies compression activity based on sensor readings and the implemented detection logic.
5. **Rate Monitoring:** Timing information is used to estimate compression frequency, with a target monitoring range based on approximately 100–120 compressions per minute.
6. **Feedback Generation:** LEDs, the OLED display, and the optional buzzer communicate the detected status.
7. **Dashboard Communication:** Sensor information is transmitted through USB serial communication to a Python application for additional visualization.

## 11. Python Dashboard

An optional Python-based graphical dashboard is included to provide a more detailed view of the system's operation.

The dashboard is developed using Tkinter and PySerial.

### Dashboard Features

- Serial port configuration.
- Live sensor value monitoring.
- Compression status visualization.
- Compression rate display.
- Serial communication with the Arduino.
- Basic diagnostics and monitoring.

### Serial Communication Format

The Arduino transmits data in CSV format:

```text
raw,status,rate
```

Example:

```text
420,ACTIVE,105
380,ACTIVE,110
120,REST,0
```

The dashboard reads incoming serial data at a baud rate of **9600** and updates the displayed information.

## 12. Key Features

- **Low-Cost Design:** Uses affordable electronic components and an existing training mannequin.
- **Universal Retrofit Approach:** Designed to be adaptable to different infant CPR training mannequins.
- **Real-Time Monitoring:** Continuously reads sensor information during practice.
- **Visual Feedback:** Uses LEDs and an OLED display to communicate system status.
- **Audio Feedback:** Supports optional buzzer-based alerts.
- **Compression Rate Monitoring:** Uses timing logic to estimate compression frequency.
- **Computer Dashboard:** Provides an additional interface for monitoring sensor information.
- **Modular Architecture:** Allows individual hardware and software components to be modified or upgraded.

## 13. Installation and Setup

### 13.1 Hardware Setup

1. Connect the FSR402 sensor to the Arduino through a voltage divider circuit.
2. Connect the OLED display to the appropriate Arduino pins.
3. Connect the LED indicators and buzzer.
4. Position the sensor appropriately within the mannequin's compression area.
5. Connect the Arduino to a computer using a USB cable.

### 13.2 Arduino Setup

1. Install the Arduino IDE.
2. Connect the Arduino Uno R3 to the computer.
3. Open the CPR-Coach Arduino firmware.
4. Select the appropriate board and COM port.
5. Upload the firmware.
6. Open the Serial Monitor to verify sensor readings.

### 13.3 Python Dashboard Setup

Ensure Python is installed on your computer.

Install the required dependency:

```bash
pip install pyserial
```

Run the dashboard:

```bash
python dashboard.py
```

Select the appropriate COM port and establish the serial connection.

**Note:** Close the Arduino Serial Monitor before connecting the Python dashboard to the same serial port.

## 14. Applications

CPR-Coach can be used in:

- Educational institutions.
- First-aid and CPR training centres.
- Nursing and medical simulation laboratories.
- Basic emergency response training.
- Low-cost CPR training equipment development.
- Academic research and prototyping.

## 15. Future Enhancements

The project can be extended through the following improvements:

- Calibration for more consistent force measurements.
- Improved compression detection and filtering algorithms.
- More detailed performance analysis.
- Data logging and session history.
- Wireless monitoring using Bluetooth or Wi-Fi.
- Improved dashboard visualizations.
- Compatibility testing across different mannequin models.
- Further validation against established CPR training reference equipment.

## 16. Limitations

- Sensor readings depend on sensor placement and calibration.
- The FSR sensor provides an electrical response to applied force rather than a direct clinical measurement of compression depth.
- Compression detection accuracy depends on the implemented signal-processing and threshold logic.
- The prototype requires further systematic testing and validation.
- The current implementation is intended for training and educational experimentation.

## 17. Expected Outcome

CPR-Coach aims to demonstrate that a low-cost electronic feedback module can be developed to enhance conventional infant CPR training mannequins.

By combining pressure sensing, microcontroller-based processing, visual and audio feedback, and a computer-based monitoring interface, the project provides a foundation for more accessible CPR training technology.

## 18. Sustainable Development Goals (SDGs)

This project primarily aligns with:

### SDG 3 – Good Health and Well-Being

The project supports improved access to CPR training resources by exploring affordable technologies that can assist in emergency response education.

## 19. Disclaimer

CPR-Coach is an academic prototype developed for educational and CPR training purposes. It is not a certified medical device and must not be used as a substitute for professional medical equipment, certified CPR instruction, or clinical guidance.

## 20. Authors

**Devansh Sharma**  
Register Number: RA2411003050035  
Department of Computer Science and Engineering  
Section: A | Academic Year: 3rd Year  
SRM Institute of Science and Technology, Tiruchirappalli, India

**Varadha P. Sajeev**  
Register Number: RA2411003050004  
Department of Computer Science and Engineering  
Section: A | Academic Year: 3rd Year  
SRM Institute of Science and Technology, Tiruchirappalli, India

---

**Mentored by:**  
Dr. S. Kanaga Subaraja  
Head of Department, Computer Science and Engineering  
SRM Institute of Science and Technology, Tiruchirappalli

---

*CPR-Coach – Making CPR Training More Accessible Through Affordable Technology.*
