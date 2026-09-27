# Smart Vehicle Immobilizer & Keyless Ignition System

An Arduino-based Smart Vehicle Immobilizer and Keyless Ignition System that uses RFID authentication to control a vehicle motor. The project demonstrates how an authorized RFID vehicle key can start and stop a motor while providing LCD, LED, and buzzer indications for system status and unauthorized access.

## Components Used

* Arduino Uno
* RC522 RFID Reader
* RFID Vehicle Key/Card
* 16×2 I2C LCD
* L298N Motor Driver
* DC Motor
* Red LED
* Green LED
* Active Buzzer
* 220Ω Resistors
* Jumper Wires
* External Motor Power Supply

## Pin Connections

| Component     | Arduino Uno |
| ------------- | ----------- |
| RFID SDA / SS | D10         |
| RFID RST      | D9          |
| RFID MOSI     | D11         |
| RFID MISO     | D12         |
| RFID SCK      | D13         |
| RFID VCC      | 3.3V        |
| RFID GND      | GND         |
| LCD SDA       | A4          |
| LCD SCL       | A5          |
| LCD VCC       | 5V          |
| LCD GND       | GND         |
| L298N IN1     | D7          |
| L298N IN2     | D8          |
| L298N ENA     | D6          |
| Green LED     | D3          |
| Red LED       | D4          |
| Buzzer        | D5          |

## Working

1. When the system is powered on, the LCD displays the startup messages **SMART VEHICLE / IMMOBILIZER** and **KEYLESS IGNITION / SYSTEM**.
2. The system then enters the secure state with the motor OFF, red LED ON, and green LED OFF.
3. The LCD displays **READY TO START / TAP VEHICLE KEY**.
4. The RC522 RFID reader reads the vehicle key and compares its UID with the authorized UID stored in the Arduino.
5. When the authorized key is detected, the L298N starts the motor, the green LED turns ON, the red LED turns OFF, and the buzzer gives one beep.
6. The LCD displays **ACCESS GRANTED / VEHICLE STARTED**, followed by **VEHICLE STARTED / TAP KEY TO STOP**.
7. When the authorized key is tapped again, the motor stops, the green LED turns OFF, the red LED turns ON, and the buzzer gives one beep.
8. The LCD displays **VEHICLE STOPPED / KEY ACCEPTED** and then returns to the ready screen.
9. If an unauthorized key is detected, the LCD displays **ACCESS DENIED / WRONG VEHICLE**. The red LED blinks five times and the buzzer sounds as a security alert.

## Authorized RFID Key

The programmed authorized RFID UID is:

`40 CA 5B 53`

## Features

* RFID-based vehicle authentication
* Keyless vehicle start and stop
* LCD status indication
* Green and red security indicators
* Unauthorized key alarm
* DC motor control using L298N
* Arduino-based embedded control

## Required Arduino Libraries

Install these libraries in the Arduino IDE:

* `MFRC522`
* `LiquidCrystal_I2C`

The `SPI` and `Wire` libraries are included with the Arduino environment.

## Project Purpose

This project is designed for educational and demonstration purposes to understand RFID authentication, Arduino programming, motor control, LCD interfacing, and hardware-software integration in a vehicle security application.

## Safety Note

This is a prototype for learning and demonstration. It is not intended to be used as a production automotive immobilizer or as a safety-critical vehicle control system.

## Author

Developed as an embedded systems and electronics project using Arduino Uno and RFID technology.
