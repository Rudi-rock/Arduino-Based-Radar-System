# Arduino-Based Radar System

A complete Arduino-based radar system using an HC-SR04 ultrasonic sensor and a servo motor, paired with a modern HTML/CSS/JS web-based radar interface. The web UI displays real-time angle–distance readings as a sweeping 360° radar.

---

## Features

### Hardware
- HC-SR04 ultrasonic distance sensor  
- SG90/MG995 servo motor (0°–180° sweep)  
- Arduino UNO/Nano/Mega  
- Optional: ESP8266/ESP32 for wireless streaming

### Web Interface
- Real-time radar sweep  
- Color-coded object detection  
- Fully responsive  
- Modern animation and UI  
- Works on desktop and mobile  
- Uses no external libraries (pure HTML/CSS/JS)

---

## Project Structure

```
Arduino-Based-Radar-System/
│
├── Arduino_Code/
│   └── radar.ino
│
├── Web_Interface/
│   ├── index.html
│   ├── script.js
│   └── style.css
│
└── README.md
```

---

## How It Works

1. Servo sweeps from 0° to 180° and back.
2. At each angle, the ultrasonic sensor measures distance.
3. Arduino outputs data in the format:

```
angle:45 distance:123
angle:46 distance:120
```

4. The web interface reads the serial data and plots objects in real time.
5. The sweeping line displays detected distances as blips on the radar.

---

## Hardware Connections

| Component         | Arduino Pin |
|------------------|-------------|
| HC-SR04 Trigger  | D9          |
| HC-SR04 Echo     | D10         |
| Servo Signal     | D6          |
| VCC              | 5V          |
| GND              | GND         |

---

## Running the Web Interface

### Method 1: Local Browser (USB Serial)
1. Upload the Arduino sketch.
2. Open the `index.html` file in any browser.
3. Click "Connect".
4. Select your Arduino COM port.
5. Live radar display begins.

### Method 2: ESP8266/ESP32 (Wireless)
- Host the HTML/CSS/JS files on SPIFFS/LittleFS.
- Send radar data using WebSocket or serial passthrough.

---

## Screenshots

(Add your images here)

```
/assets/radar_ui.png
/assets/live_detection.png
```

---

## Arduino Output Format

```
Serial.print("angle:");
Serial.print(angle);
Serial.print(" distance:");
Serial.println(distance);
```

---

## Future Improvements
- 3D radar view  
- Sound alert for close objects  
- Object labeling and tracking  
- Data logging to CSV  

---

## Contributing
Pull requests are welcome.  
For major changes, open an issue first before modifying the project.

---

## License
MIT License
