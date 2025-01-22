

# 🌐 Arduino IoT Cloud Smart Home Automation System 🏠

🚀 **Welcome to the Smart Home Automation System!** This project integrates Arduino IoT Cloud, DHT sensors, IR remote controls, and relays for efficient home automation. Control your devices remotely, monitor temperature and humidity, and make your home smarter!  

---

## 📋 **Features**  
- 🌡️ **Temperature & Humidity Monitoring** using DHT sensors.  
- 📡 **WiFi Connectivity** for real-time IoT cloud synchronization.  
- 📱 **Manual Control** with physical switches.  
- 🎛️ **Remote Control** using IR remotes.  
- 🔄 **Automated Relays** for device control.  
- 💡 **Status Sync** with Arduino IoT Cloud for live updates.  

---

## 🔧 **Hardware Requirements**  
- 🛠️ ESP32 Board  
- 🌬️ DHT11/DHT22 Temperature & Humidity Sensor  
- 📡 IR Receiver Module  
- 🔌 Relays (4)  
- 💡 Switches (4)  
- 💻 WiFi-enabled network  

---

## 📂 **File Structure**  
```plaintext
📦 SmartHomeAutomation  
 ┣ 📜 main.ino        // Arduino code for ESP32  
 ┣ 📜 thingProperties.h  // Auto-generated IoT cloud file  
 ┗ 📄 README.md       // Project documentation  
```

---

## ⚙️ **Setup Instructions**  
1. 🖥️ Clone the repository:  
   ```bash
   git clone https://github.com/your-username/SmartHomeAutomation.git
   cd SmartHomeAutomation
   ```
2. 🔌 Connect the hardware:  
   - Relay Module: Pins 23, 19, 18, 5.  
   - Switches: Pins 13, 12, 14, 27.  
   - DHT Sensor: Pin 4.  
   - IR Receiver: Pin 35.  

3. 📶 Update the credentials in the code:  
   - `SSID`: Your WiFi name.  
   - `PASS`: Your WiFi password.  
   - `DEVICE_KEY`: Your Arduino IoT secret key.  

4. 📤 Upload the code to ESP32 using the Arduino IDE.  

5. 🔍 Monitor the status via Serial Monitor and Arduino IoT Cloud.

---

## 🖥️ **Usage**  
- 🕹️ Use an IR remote to control devices remotely.  
- 🖲️ Toggle switches for manual control.  
- 📊 Monitor sensor data via Arduino IoT Cloud.  

---

## 📚 **Code Highlights**  

### 🌡️ **Sensor Reading**  
```cpp
void readSensor() {
  float h = dht.readHumidity();
  float t = dht.readTemperature();
  if (isnan(h) || isnan(t)) {
    Serial.println("Sensor Error!");
    return;
  }
  humidity1 = h;
  temperature = t;
}
```

### 🎛️ **Relay Control**  
```cpp
void relayOnOff(int relay) {
  if (relay == 1) {
    digitalWrite(RelayPin1, toggleState_1 ? HIGH : LOW);
    toggleState_1 = !toggleState_1;
  }
}
```

---

## 🌟 **Key Functions**  
| Function             | Description                                |  
|----------------------|--------------------------------------------|  
| `readSensor()`       | Reads and updates temperature & humidity. |  
| `manual_control()`   | Manages switch-based manual device control.|  
| `relayOnOff()`       | Toggles relay state for connected devices. |  

---

## 🌐 **Connect with Arduino IoT Cloud**  
- Real-time device monitoring and control.  
- Synchronize device states automatically.
- 
---

## 💻 **Contributing**  
Feel free to fork, improve, and submit a pull request! Your contributions make this project better.  

---


---
