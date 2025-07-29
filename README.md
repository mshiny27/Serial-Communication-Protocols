
# Serial Communication Protocols Between ESP32 and Arduino Uno

This project demonstrates the successful implementation of **three fundamental serial communication protocols**  **UART, I2C, and SPI**    between **ESP32** and **Arduino Uno** boards. Each protocol is configured in different master-slave roles, showcasing robust interfacing and reliable data exchange between microcontrollers.

---

## Project Overview

The project involves setting up:
- **UART Communication** (Arduino Uno → ESP32)
- **I2C Communication** (ESP32 → Arduino Uno)
- **SPI Communication** (ESP32 → Arduino Uno)


---

## Hardware Components Used
- ESP32 Dev Board
- Arduino Uno
- Jumper Wires
- Breadboard
- USB cables for programming
- Resistors (for voltage level shifting)

---

## 🔄 Communication Roles

| Protocol | Master       | Slave         |
|----------|--------------|---------------|
| UART     | Arduino Uno  | ESP32         |
| I2C      | ESP32        | Arduino Uno   |
| SPI      | ESP32        | Arduino Uno   |




---

## Protocol-wise Description

### 🔸 UART (Universal Asynchronous Receiver Transmitter)
   -   **Use case:** Simple serial text data transmission.
   -   **Setup:** Arduino sends a message over TX to ESP32 RX.
   -   **Verification:** ESP32 Serial Monitor displays the received data.

### 🔸 I2C (Inter-Integrated Circuit)
- **Use case:** Master sends a message and receives a reply from the slave.
- **Addressing:** Arduino is assigned a slave address (e.g., `0x0A`).
- **Verification:** Both master and slave serial monitors show the transaction logs.

### 🔸 SPI (Serial Peripheral Interface)
- **Use case:** Fast synchronous communication using MOSI, MISO, SCLK, and SS.
- **Setup:** ESP32 sends a message via MOSI, and Arduino responds via MISO.
- **Verification:** Data is confirmed at both ends using Serial Monitor.

---

## Serial Monitor Output Samples

| Protocol | ESP32 Serial Output                      | Arduino Serial Output                 |
|----------|------------------------------------------|----------------------------------------|
| UART     | ` Message received from Arduino: Hello! I am Arduino Uno`     | `Hello! I am Arduino Uno`                   |
| I2C      | ` Hello from Arduino`     | `Received: Hello rom ESP32`    |
| SPI      | `Sending message to slave...                      Message sent`| `Message received from Master: System check passed.Device communication successful.`    |


---

### Applications

These communication protocols are widely used in real-world electronics and embedded systems. Here’s how they apply in practical scenarios:

#### 🔹 UART (Universal Asynchronous Receiver Transmitter)
- Used in debugging and logging over Serial Monitor.
- Communication between GPS modules and microcontrollers.
- Wireless module communication (e.g., HC-05 Bluetooth, GSM modules).
- Console terminals in embedded Linux devices.

#### 🔹 I2C (Inter-Integrated Circuit)
- Interfacing with multiple sensors (e.g., temperature, accelerometers).
- Used in OLED, LCD, and EEPROM communication.
- Real-time clock (RTC) module interfacing.
- Ideal for short-distance, multiple-slave networks on two wires.

#### 🔹 SPI (Serial Peripheral Interface)
- Fast communication with flash memory, SD cards, and displays (e.g., TFT, OLED).
- Wireless transceivers like nRF24L01 use SPI.
- Used in audio DACs, analog-to-digital converters (ADCs).
- Preferred in systems requiring high-speed, low-latency communication.

> These protocols are foundational in robotics, IoT devices, consumer electronics, industrial automation, and automotive systems.

---

### 🔁 Communication Type

| Protocol | Communication Type | Description                                                                 |
|----------|--------------------|-----------------------------------------------------------------------------|
| UART     | Simplex (here)           |There is no return communication, data flows only from Arduino to ESP32.                |
| I2C      | Half-Duplex        | Master and slave share the same SDA line for both transmission and reception.|
| SPI      | Full-Duplex        | Separate MOSI and MISO lines allow simultaneous two-way communication.      |

> **Note**: While I2C is technically capable of two-way communication, it cannot send and receive at the same time — hence, it's considered **half-duplex**.
>
> **UART** is primarily **full-duplex**,which is achieved through the **TX** and **RX** lines allowing bidirectional communication.

---


## Learning Outcome

This project strengthens understanding of embedded serial communication by practically implementing:
- Master-slave roles
- Handshaking & data integrity
- Protocol-specific wiring and timing considerations.

> Open the `.zip` for code and connection reference.
[serial_protocols.zip](https://github.com/user-attachments/files/21496881/serial_protocols.zip)
