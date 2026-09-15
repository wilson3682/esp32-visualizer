# 🎛️ ESP32 Advanced Music Spectrum Analyzer & Visualizer

[![Web Installer](https://img.shields.io/badge/Web%20Installer-Available%20Online-0284c7?style=for-the-badge&logo=googlechrome&logoColor=white)](https://wilson3682.github.io/esp32-visualizer/)
[![ESP-IDF](https://img.shields.io/badge/DSP-esp--dsp%20Hardware%20Accelerated-38bdf8?style=for-the-badge)](https://github.com/espressif/esp-dsp)
[![FastLED](https://img.shields.io/badge/LEDs-FastLED%20Parallel-green?style=for-the-badge)](https://github.com/FastLED/FastLED)
[![License](https://img.shields.io/badge/Security-ECDSA%20P--256%20Hardware%20Locked-red?style=for-the-badge)]()

An ultra-responsive, studio-grade real-time audio spectrum analyzer and music visualizer powered by the **ESP32**, **INMP441 I2S digital microphone**, and **WS2812B addressable LED matrices**. 

Engineered with low-level assembly DSP routines, dual-core task isolation, framerate-independent physics, and an interactive real-time web controller featuring a dedicated 22-preset parametric equalizer studio.

---

## ⚡ Quick Install via Web Browser

No Arduino IDE, Python, or command-line tools required. Connect your ESP32 to your computer with a USB data cable, open Google Chrome or Microsoft Edge, and click the link below:

👉 **[Launch Web Serial Firmware Installer](https://wilson3682.github.io/esp32-visualizer/)**

---

## ✨ Key Features

### 🚀 Audio & DSP Architecture
* **Hardware-Accelerated FFT (`esp-dsp`):** Computes 512-point Radix-2 floating-point FFTs in **~100 microseconds** using native Xtensa LX6 assembly instructions.
* **75% Overlapping I2S Buffering:** Samples audio in 128-sample chunks (~10.6 ms hop size) for an audio refresh rate of **~94 Hz**—delivering immediate transient response for percussive beats and snares.
* **Dual-Core FreeRTOS Isolation:**
  * **Core 0:** Dedicated strictly to real-time I2S DMA audio sampling, Hann windowing, and FFT calculations.
  * **Core 1:** Manages graphics rendering, physics simulation, WebSocket broadcasting, and web servers.
* **Thread-Safe Memory Sharing:** Core-to-core magnitude transfers protected by FreeRTOS mutex synchronization to eliminate torn frames or race conditions.

### 🎨 Visuals & Ballistics
* **Framerate-Independent Delta-Time ($\Delta t$) Physics:** Peak dots, falling bars, and projectile sparks calculate trajectories based on elapsed wall-clock time, preventing stutter or mid-air pauses during network bursts.
* **Direction-Aware Cannon Sparks:** High-energy transients launch ballistic projectile sparks in the physical orientation of the active pattern (bottom-up, inverted-down, center-outward, or inward).
* **Dynamic Matrix Geometry:** Supports panels up to **64 columns × 64 rows** (up to 4,096 LEDs max), with live on-the-fly column width adjustments (1, 2, 3, or 4 LEDs per band).
* **Multi-Pin Parallel Output:** Drive strips across 1, 2, or 4 GPIO pins simultaneously to bypass WS2812B single-pin serial bottlenecking and achieve high refresh rates (up to 80+ FPS).
* **Extensive Theme Library:** 81 custom color themes, 32 peak dot color options, and 10 dynamic pattern modes.

### 🌐 Connectivity & Controls
* **Dual Wi-Fi Networking:** Operates simultaneously in SoftAP mode (`ESP32_VU_METER`) and Station mode (connected to your home router), featuring a 30-second background auto-reconnect heartbeat.
* **mDNS Network Addressing:** Access the dashboard from any device at **`http://vumeter.local`**.
* **On-Matrix IP Banner:** Scrolls the assigned local IP address across the panel on boot when connected to home Wi-Fi.
* **Wireless Web OTA Updates:** Flash future firmware updates over Wi-Fi directly from your browser via the built-in **/update** portal.
* **Auto-Standby / Sleep on Silence:** Continuously monitors total acoustic energy; powers down LEDs during extended periods of silence (1–30 minutes) and wakes instantly when music resumes.
* **Hardware IR Remote Control:** Native support for standard NEC 24-key and 44-key handheld infrared remotes for couch control.

### 🎛️ Dedicated Equalizer Studio (`/eq`)
* Web-based parametric equalizer interface supporting live 16-band or 32-band visual tuning.
* **22 Acoustic Profiles:** 11 specialized vocal presets (Vocal Clarity Pro, Warm Acoustic, Sibilance Tamer, Podcast, etc.) and 11 genre profiles (Club Sub-Bass, R&B, Rock, Lo-Fi, EDM, etc.).
* Live bidirectional slider synchronization across all connected devices in real time.

### 🔒 Hardware-Locked Cryptographic Licensing
* **Silicon-Bound Security:** Firmly binds execution to the ESP32's immutable, factory-burned 48-bit silicon MAC address (`esp_read_mac()`).
* **Asymmetric ECDSA (NIST P-256 / SHA-256):** Firmware verifies digital signatures using native `mbedtls` public-key cryptography. Unlicensed clone boards enter a 2-minute demo mode before locking down with a status indicator.
* **Companion License Studio:** Includes an offline browser-based signing utility (`license_studio.html`) and Python generator (`license_keygen.py`) with automatic customer ledger export to CSV.

---

## 🛠️ Hardware Wiring Guide

### 1. INMP441 I2S Digital Microphone
| INMP441 Pin | ESP32 GPIO | Description |
| :--- | :--- | :--- |
| **VDD** | **3.3V** | Power (Do NOT connect to 5V) |
| **GND** | **GND** | Ground |
| **SD** | **GPIO 32** | Serial Data Out |
| **WS** | **GPIO 15** | Word Select (Left/Right Clock) |
| **SCK** | **GPIO 14** | Serial Clock |
| **L/R** | **GND** | Sets audio channel to Left |

### 2. WS2812B / WS2811 Addressable LED Matrix
* **Power (VCC / GND):** Connect directly to an external 5V power supply. Ensure common ground with the ESP32.
* **Data Output Pin(s):**
  * **1-Pin Mode (Default):** `GPIO 0`
  * **2-Pin Mode (Parallel 2× FPS):** `GPIO 0` (First half) and `GPIO 4` (Second half)
  * **4-Pin Mode (Parallel 4× FPS):** `GPIO 0`, `GPIO 4`, `GPIO 16`, `GPIO 17`

### 3. Optional IR Remote Receiver (VS1838B / KY-022)
| Sensor Pin | ESP32 GPIO | Notes |
| :--- | :--- | :--- |
| **VCC (+)** | **3.3V** | Powers sensor |
| **GND (-)** | **GND** | Ground |
| **OUT (S)** | **GPIO 13** | 38 kHz NEC Demodulated Data Input |

---

## 💻 Manual Compilation (Arduino IDE)

If compiling manually from source rather than using the Web Installer:

1. **Board Settings:**
   * **Board:** `ESP32 Dev Module` (or equivalent ESP32 board)
   * **Partition Scheme:** `Minimal SPIFFS (1.9MB APP with OTA)` *(Required)*
   * **Core Debug Level:** `None`
2. **Required Libraries (Install via Arduino Library Manager):**
   * `FastLED` (by Daniel Garcia)
   * `WebSockets` (by Markus Sattler)
   * `ArduinoJson` (v6 or v7)
   * `IRremoteESP8266` *(Optional, set `ENABLE_IR_REMOTE false` if not used)*
3. **Sketch Files:** Ensure all modular headers are placed in the same folder:
   * `spectrum_analyzer.ino`
   * `fonts.h`
   * `themes.h`
   * `intro_effects.h`
   * `spectrum_effects.h`
   * `webpages.h`
   * `public_key.h`

---

## 📱 Initial Setup & Navigation

1. Power on the device. On first boot, connect your phone or laptop to the visualizer's Wi-Fi Access Point:
   * **SSID:** `ESP32_VU_METER`
   * **Password:** `password123`
2. Open your web browser and go to:
   * **Dashboard:** `http://192.168.4.1` or `http://vumeter.local`
   * **Parametric Equalizer:** `http://vumeter.local/eq`
   * **Wireless OTA Firmware Flasher:** `http://vumeter.local/update`
3. Under the **📐 Matrix** tab, configure your physical grid columns, height, number of output pins, and optional home Wi-Fi credentials.
4. Click **Save Geometry & Network** to reboot.

---

## 🔑 Device Activation & Licensing

Each ESP32 contains a permanent silicon MAC address. Unlicensed installations run in a **2-Minute Demo Mode** on power-up:

1. Copy the **Device Hardware ID (MAC)** displayed on the LED panel or in the **📐 Matrix** tab.
2. Sign the MAC address using your private master key (via `license_studio.html` or `license_keygen.py`).
3. Paste the generated cryptographic key into the **Activation Key** input on the web dashboard and click **Activate Device**.
4. The key is verified against the embedded public key and saved permanently to NVS flash memory. The full visualizer unlocks immediately and stays unlocked across all future power cycles and OTA updates.

---

## 📄 License & Attribution

* Built with [FastLED](https://github.com/FastLED/FastLED) and Espressif [esp-dsp](https://github.com/espressif/esp-dsp).
* Web serial installation powered by [ESP Web Tools](https://esphome.github.io/esp-web-tools/).
* Cryptographic signature verification powered by Mbed TLS ECDSA.
