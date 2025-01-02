# Ultrasonic Distance Measurement System

## Overview
This project implements a system to measure the distance of objects using an ultrasonic sensor. The measured distance is displayed on a 16x2 LCD in real-time. It uses an ATmega microcontroller to interface with the ultrasonic sensor and manage the measurement and display process.

### Features
- **Real-Time Distance Measurement**: Measures distances in centimeters.
- **LCD Display**: Continuously updates the measured distance on a 16x2 LCD.
- **Interrupt-Based Measurement**: Uses Input Capture Unit (ICU) for precise time measurements.

---

## System Design

### Hardware Requirements
1. **ATmega Microcontroller**
2. **Ultrasonic Sensor** (e.g., HC-SR04)
3. **16x2 LCD**
4. **Power Supply** (5V)
5. **Resistors and Wires**

### Software
- **C Programming** using AVR libraries
- Modularized drivers for GPIO, ICU, LCD, and Ultrasonic Sensor

---

## File Descriptions

### `DistanceMeasurement.c`
The main program for the distance measurement system. Includes:
- Initializing the Ultrasonic Sensor and LCD.
- Reading the distance from the sensor.
- Displaying the distance on the LCD in real-time.

### Supporting Modules
- **`ultrasonic.c/h`**: Interfaces with the ultrasonic sensor for distance measurements.
- **`icu.c/h`**: Configures the Input Capture Unit for time measurement.
- **`lcd.c/h`**: Manages LCD initialization and display functions.
- **`gpio.c/h`**: Configures GPIO pins for peripheral communication.
- **`std_types.h` & `common_macros.h`**: Defines standard data types and reusable macros.

---

## Functionality

### How It Works
1. The ultrasonic sensor emits a sound wave and detects the echo.
2. The time delay between sending and receiving the wave is measured using the Input Capture Unit (ICU).
3. The system calculates the distance based on the time delay:
   \[
   \text{Distance (cm)} = \frac{\text{Time (us)} \times \text{Speed of Sound (cm/us)}}{2}
   \]
   - Speed of sound = **0.034 cm/μs**

4. The calculated distance is displayed on the LCD in centimeters.

### Real-Time Display
- The LCD shows:
  ```
  Distance= XXX cm
  ```
  - Updates continuously with the measured distance.
  - Pads with spaces for distances less than 100 cm to maintain display alignment.

---

## How to Use

### Setup
1. Connect the hardware as per the system design.
2. Compile and upload `DistanceMeasurement.c` to the ATmega microcontroller.
3. Power the system.

### Operation
- The system starts measuring distance and displays the result on the LCD.
- The distance updates in real-time.

---

## Future Enhancements
- Add support for measuring longer distances or higher precision.
- Include EEPROM to log distance readings over time.
- Implement a graphical interface for advanced monitoring.

---

## Author
**Basel Dawoud**  
*Contact*: baseldawoud2003@gmail.com  

Contributions and suggestions are welcome!  
