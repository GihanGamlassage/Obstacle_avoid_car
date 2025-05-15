# Obstacle_avoid_car
# 🚗 Arduino Obstacle Avoidance Robot with Ultrasonic Sensor & Servo

This project is an **autonomous obstacle-avoiding robot** built using an **Arduino Nano**, an **ultrasonic sensor**, a **servo motor**, and **DC motors** controlled via an **L298N motor driver**.

The robot detects obstacles using an **HC-SR04 ultrasonic sensor**, scans left and right with a **servo**, and decides the best path to avoid obstacles.

---

## 🔧 Hardware Components

| Component             | Quantity |
|-----------------------|----------|
| Arduino Nano          | 1        |
| HC-SR04 Ultrasonic Sensor | 1    |
| Servo Motor (SG90/MG90) | 1      |
| L298N Motor Driver Module | 1    |
| DC Gear Motors        | 2        |
| Robot Chassis         | 1        |
| Wheels                | 2        |
| Power Supply (Battery or Power Bank) | 1 |
| Jumper Wires          | Many     |
| Breadboard (optional) | 1        |

---

## 📌 Wiring & Pin Connections

### 🧠 Arduino Nano Pinout

| Function           | Arduino Pin | Connected To              |
|--------------------|-------------|----------------------------|
| Ultrasonic Trigger | D2          | HC-SR04 **Trig**           |
| Ultrasonic Echo    | D4          | HC-SR04 **Echo**           |
| Servo Signal       | D9          | Servo Motor **Signal**     |
| Motor 1 (Left)     | D5, D6      | L298N IN1, IN2             |
| Motor 2 (Right)    | D7, D8      | L298N IN3, IN4             |
| L298N ENA, ENB     | Connect to 5V or PWM pins if needed |
| HC-SR04 VCC        | 5V          |                            |
| HC-SR04 GND        | GND         |                            |
| Servo VCC          | 5V          | Use external 5V if needed  |
| Servo GND          | GND         |                            |

⚠️ **Important**: Power the **motors and servo** using an **external 5V supply**, not directly from the Nano.

---

## 📚 Required Arduino Libraries

Install these libraries using the **Library Manager** in Arduino IDE (`Sketch > Include Library > Manage Libraries`):

1. **Servo** by Arduino  
   - Controls the servo motor for left/right scanning

---

## 🧠 How It Works

1. The robot moves forward by default.
2. If it detects an obstacle within 20 cm using the ultrasonic sensor:
   - It stops.
   - Rotates the servo to **0° (left)** and checks for space.
   - If left is blocked, it checks **180° (right)**.
   - Based on the readings, it turns in the free direction and continues.
   - If both sides are blocked, it reverses and tries again.

---

## ▶️ How to Upload and Run

1. Connect your Arduino Nano to the PC.
2. Open the `.ino` file in the Arduino IDE.
3. Select:
   - **Board**: Arduino Nano
   - **Processor**: ATmega328P (Old Bootloader, if needed)
   - **Port**: COM port where your Nano is connected
4. Click **Upload**.
5. Power your robot with an external battery.

---



---

## 🔄 Future Improvements (Optional Ideas)
- Add IR sensors for cliff detection
- Add more ultrasonic sensors (fixed left/right)
- Add Bluetooth/WiFi (ESP32 or ESP8266)
- Add a buzzer or LED indicators
- Add MPU6050 for stability tracking

---

## 📜 License

This project is open-source. Use it, modify it, and share it!

