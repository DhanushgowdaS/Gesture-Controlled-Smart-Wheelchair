# Gesture-Controlled Smart Wheelchair

An ESP32-based gesture-controlled smart wheelchair designed to provide intuitive, wireless mobility assistance using hand movements. The system utilizes an ADXL345 accelerometer mounted on a wearable glove to detect hand gestures and transmit commands to the wheelchair via ESP-NOW, enabling real-time control without requiring a Wi-Fi network.

The wheelchair also incorporates obstacle detection and safety mechanisms using ultrasonic and IR sensors, making it a reliable embedded systems project focused on assistive technology.

---

## Features

- Wireless hand gesture control using ESP32 + ADXL345
- ESP-NOW communication (No Wi-Fi router required)
- Real-time movement control
- Forward, Backward, Left, Right and Stop gestures
- Dual ultrasonic sensors for obstacle detection
- Dual IR sensors for safety detection
- PWM-based motor speed control
- Audio and LED status indication
- Battery-powered embedded system

---

## System Architecture

```
        Hand Gesture

             │
             ▼

      ADXL345 Sensor
             │
             ▼

       ESP32 (Glove)
             │
      ESP-NOW Wireless
             │
             ▼

    ESP32 (Wheelchair)
             │
             ▼

      Motor Controller
          (L298N)
             │
             ▼

        DC Motors
             │
     ┌───────┴────────┐
     ▼                ▼

 Ultrasonic        IR Sensors
    Sensors

```

---

## Working Principle

1. The ADXL345 continuously measures the orientation of the user's hand.
2. Hand movements are classified into predefined gestures.
3. The glove ESP32 transmits the detected gesture using ESP-NOW.
4. The wheelchair ESP32 receives the command.
5. The motor driver executes the corresponding movement.
6. Safety sensors continuously monitor obstacles and prevent unsafe movement.

---

## Gesture Mapping

| Hand Gesture | Wheelchair Action |
|--------------|------------------|
| Tilt Forward | Move Forward |
| Tilt Backward | Move Backward |
| Tilt Left | Turn Left |
| Tilt Right | Turn Right |
| Neutral | Stop |

---

## Technologies Used

- Embedded C++
- Arduino Framework
- ESP-NOW Protocol
- I2C Communication
- PWM Motor Control

---

## Repository Structure

```
Gesture-Controlled-Smart-Wheelchair
│
├── Transmitter_Glove/
├── Receiver_Wheelchair/
├── Hardware/
├── Documentation/
├── Images/
└── README.md
```

---

## Future Improvements

- AI-based voice control
- Smartphone application
- GPS navigation
- Emergency SOS feature
- Fall detection
- Cloud connectivity
- Battery monitoring
- Autonomous navigation


**Status**  
under working
