<<<<<<< HEAD
# IoT25-HW04: ESP32 Bluetooth Classic Serial Communication

This project demonstrates how to establish Serial communication between a computer and an ESP32 via **Classic Bluetooth (SPP - Serial Port Profile)** using the Arduino IDE. It enables bidirectional data transfer between the ESP32 and a smartphone or PC terminal via Bluetooth.

---

## 🧾 Objectives

- Understand the basics of ESP32 Bluetooth Classic (SPP)
- Set up Bluetooth device pairing with custom device name
- Bridge serial communication between USB (Serial) and Bluetooth (SerialBT)
- Test bidirectional data exchange

---

## 🧰 Components Used

- ESP32 DevKit v1  
- Micro USB Cable  
- Android Smartphone with **Serial Bluetooth Terminal** App  
- Laptop with Arduino IDE  

---

## 🧠 How It Works

The ESP32 uses `BluetoothSerial` library to establish a classic Bluetooth connection. It functions as a serial bridge between the USB serial and Bluetooth serial interfaces:

- Any data sent via the Arduino Serial Monitor is forwarded to the connected Bluetooth device.
- Any data received from the Bluetooth device is echoed back to the Serial Monitor.

---

## 💡 Code Summary

```cpp
#include "BluetoothSerial.h"

BluetoothSerial SerialBT;

void setup() {
  Serial.begin(115200);
  SerialBT.begin("202035536_임동현");  // Replace with your name
  Serial.println("The device started, now you can pair it with bluetooth!");
}

void loop() {
  if (Serial.available()) {
    SerialBT.write(Serial.read());
  }
  if (SerialBT.available()) {
    Serial.write(SerialBT.read());
  }
  delay(20);
}
```

- Uses `SerialBT.begin()` to set up Bluetooth Classic with a custom name.
- Bridges input/output between USB serial (`Serial`) and Bluetooth (`SerialBT`).

---

## 📱 Mobile App

You can test the Bluetooth communication using the **Serial Bluetooth Terminal** Android App:

- App Link: [Play Store](https://play.google.com/store/apps/details?id=de.kai_morich.serial_bluetooth_terminal)

Steps:
1. Pair your phone with ESP32 (name: `202035536_임동현`)
2. Open the app and connect to the paired ESP32 device
3. Send and receive messages

---

## 📸 Photos of Deployment

Photos showing the ESP32 connected to PC, Bluetooth pairing on the phone, and Serial Monitor outputs:

![Setup 1](./media/hw%204-1.png)  
![Setup 2](./media/hw%204-2.png)  
![Phone Screenshot 1](./media/hw%204-3.jpg)  
![Phone Screenshot 2](./media/hw%204-4.jpg)  
![Terminal Demo 1](./media/hw%204-5.jpg)  
![Terminal Demo 2](./media/hw%204-6.jpg)

---

## ✅ Results & Verification

- [x] Successfully uploaded the code to ESP32  
- [x] Bluetooth paired and recognized as expected  
- [x] Messages sent from Serial Monitor appear on the phone terminal  
- [x] Messages typed in the phone app appear on the Serial Monitor  

---

## 🔗 Reference

- [ESP32 Bluetooth Classic Tutorial](https://randomnerdtutorials.com/esp32-bluetooth-classic-arduino-ide/)
=======
# IoT25-HW04
>>>>>>> 9f4d1b040ffec5c59747b1c370c5fbd7886648e6
