# 🎛️ ESP32 Professional Audio Spectrum Visualizer

[![Web Installer](https://img.shields.io/badge/Web%20Installer-Flash%20Online-0284c7?style=for-the-badge&logo=googlechrome&logoColor=white)](https://wilson3682.github.io/esp32-visualizer/)
[![Platform](https://img.shields.io/badge/Platform-ESP32%20Hardware-38bdf8?style=for-the-badge)]()
[![Status](https://img.shields.io/badge/Status-Commercial%20Firmware-green?style=for-the-badge)]()

An ultra-responsive, professional sound-reactive spectrum analyzer and LED music visualizer designed for custom audio rigs, karaoke speakers, home theaters, and studio matrix displays.

---

## ⚡ Install Firmware in 60 Seconds (Free Web Installer)

You can flash this firmware directly from your computer without downloading any software or development tools:

👉 **[Click Here to Launch Web Serial Installer](https://wilson3682.github.io/esp32-visualizer/)**

> **Requirements:** Use **Google Chrome** or **Microsoft Edge** on a desktop/laptop computer and connect your ESP32 board with a standard USB data cable.

---

## ✨ Features & Capabilities

* **Instant Beat & Transient Snap:** Professional-grade digital audio pickup via I2S microphone for razor-sharp response to kick drums, basslines, snares, and vocals.
* **Massive Theme & Pattern Engine:**
  * **81 Custom Color Themes:** Classic Stereo EQ, Miami Vice, Cyberpunk Synthwave, Volcanic Magma, Toxic Hazard, Tri-Zone separation, and multi-color dynamic flows.
  * **10 Animation Patterns:** Standard theme bars, center-outward expansion, edge-to-center bars, inverted waterfall drops, radial pulses, and dots-only modes.
  * **32 Peak Dot Colors & Modes:** Pinpoint, bold, and chunky peak hold options with gravity fall and auto-color matching.
* **Direction-Aware Ballistic Cannon Sparks:** Heavy bass and percussion hits trigger shooting projectile sparks that launch in the direction of the active pattern.
* **Built-In Responsive Web Dashboard:**
  * Control every parameter in real time from your phone, tablet, or laptop browser.
  * Live slider synchronization across all connected devices.
* **Dedicated Parametric Equalizer Studio (`/eq`):**
  * Fine-tune 16 or 32 individual frequency bands with noise-floor calibration.
  * **22 Audio Profiles:** 11 specialized vocal modes (Vocal Clarity Pro, Warm Acoustic, Sibilance Tamer, Podcast) and 11 music genre profiles (Club Sub-Bass, R&B, Rock, Lo-Fi, EDM).
* **Flexible Matrix Scaling:**
  * Supports panels from **16, 32, or 64 columns** and up to **64 rows** (up to 4,096 LEDs).
  * On-the-fly adjustable band thickness (1, 2, 3, or 4 LEDs per band) with auto-centering.
  * Multi-pin parallel output support (1, 2, or 4 GPIO data channels) for ultra-high framerates.
* **Dual Wi-Fi & mDNS Support:**
  * Connect to your home Wi-Fi network while keeping the fallback hotspot active.
  * Access the dashboard easily at **`http://vumeter.local`**.
  * Scrolls the assigned local IP across the LED matrix on boot.
* **Wireless Over-The-Air (OTA) Updates:** Flash future firmware updates over Wi-Fi through the browser at **`/update`**.
* **Auto-Standby / Silence Detection:** Automatically turns off the LED display after a configurable period of silence (1–30 minutes) and wakes up instantly when sound returns.
* **Handheld IR Remote Support:** Control power, brightness, patterns, and themes directly using standard 24-key and 44-key NEC remotes.

---

## 🔌 Hardware Connections & Matrix Layout

### 1. Physical Matrix Layout & Orientation

The visualizer firmware is pre-configured for a **Vertical Serpentine (Zigzag)** format. When viewing the display directly from the **front**:

```text
┌─────────────────────────────────────────────────────────────┐
│                 FRONT VIEW OF THE LED MATRIX                │
├─────────────────────────────────────────────────────────────┤
│                                                             │
│   (Top-Left)                                    (Top-Right) │
│       ▲       │       ▲       │                             │
│       │       │       │       │   ... (Zigzag continues     │
│       │       ▼       │       ▼        across all columns)  │
│                                                             │
│    [LED 0]                                  (Bottom-Right)  │
│ (Bottom-Left)                                               │
│   DATA IN ──►                                               │
└─────────────────────────────────────────────────────────────┘
```

* **Physical Origin:** LED 0 must be positioned at the **Bottom-Left corner** when looking at the matrix from the front.
* **Layout Format:** **Vertical Serpentine (Zigzag)**.
  * **Column 0 (First Column):** Data travels from **Bottom → Up**.
  * **Column 1 (Second Column):** Turns at the top and travels from **Top → Down**.
  * **Column 2 (Third Column):** Turns at the bottom and travels from **Bottom → Up**.
  * This alternating pattern continues across all columns.

---

### 2. Addressable LED Matrix (WS2812B / WS2811)
* **VCC & GND:** Connect directly to an external 5V power supply sized appropriately for your LED count. Connect power supply ground to the ESP32 ground.
* **Data Pins:**
  * **Single-Pin Mode (Default):** `GPIO 0`
  * **2-Pin Mode (2× Framerate):** `GPIO 0` (Left half) and `GPIO 4` (Right half)
  * **4-Pin Mode (4× Framerate):** `GPIO 0`, `GPIO 4`, `GPIO 16`, `GPIO 17`

---

### 3. Audio Microphone (INMP441 Digital I2S)
| Microphone Pin | Connects to ESP32 | Notes |
| :--- | :--- | :--- |
| **VDD** | **3.3V** | Do NOT use 5V |
| **GND** | **GND** | Common Ground |
| **SD** | **GPIO 32** | Serial Data |
| **WS** | **GPIO 15** | Word Select Clock |
| **SCK** | **GPIO 14** | Serial Clock |
| **L/R** | **GND** | Sets channel to Left |

---

### 4. Optional IR Remote Receiver (VS1838B / KY-022)
| Sensor Pin | Connects to ESP32 | Notes |
| :--- | :--- | :--- |
| **VCC (+)** | **3.3V** | Power |
| **GND (-)** | **GND** | Ground |
| **OUT (S)** | **GPIO 13** | 38 kHz NEC Demodulated Signal |

---

## 📱 Getting Started & First Connection

1. Flash your board using the **[Web Installer](https://wilson3682.github.io/esp32-visualizer/)**.
2. Connect your smartphone or computer to the visualizer's Wi-Fi hotspot:
   * **Network Name (SSID):** `ESP32_VU_METER`
   * **Password:** `password123`
3. Open your browser and navigate to:
   * **Main Dashboard:** `http://192.168.4.1` or `http://vumeter.local`
   * **Equalizer Studio:** `http://vumeter.local/eq`
4. Under the **📐 Matrix** tab, configure your panel's columns, height, and optional home Wi-Fi credentials, then click **Save Geometry & Network**.

---

## 🔑 License Activation & Pricing(Donation)

This software includes a **free 2-minute demo mode** on every boot so you can test your hardware, microphone, and LED connections before purchasing. 

After 2 minutes of demonstration, the LEDs enter standby and prompt for activation. Each ESP32 contains a permanent, factory-burned hardware ID. To activate your board permanently:

1. Open the visualizer dashboard and go to the **📐 Matrix** tab.
2. Locate the **Device Hardware ID (MAC Address)** and click **📋 Copy**.
3. Contact us with your **Device Hardware ID** for pricing and payment details.
4. You will receive your unique cryptographic **Activation Key**. Paste it into the activation box on your dashboard and click **🔑 Activate Device**.

Once activated, your visualizer is permanently unlocked—even across reboots, power cuts, and future OTA updates!

### 📩 Contact for Pricing & License Keys
* **Developer / Sales:** *Wilson*
* **Email:** *[willypeter67@gmail.com]*

---

## 🎥 Video Demonstration

Check out the spectrum visualizer in action:

▶️ https://www.youtube.com/watch?v=BLfNkWLkR30
