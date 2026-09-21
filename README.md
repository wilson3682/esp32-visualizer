# 🎛️ ESP32 Professional Audio Spectrum Visualizer

[![Web Installer](https://img.shields.io/badge/Web%20Installer-Flash%20Online-0284c7?style=for-the-badge&logo=googlechrome&logoColor=white)](https://wilson3682.github.io/esp32-visualizer/)
[![Platform](https://img.shields.io/badge/Platform-ESP32%20Hardware-38bdf8?style=for-the-badge)]()
[![Status](https://img.shields.io/badge/Status-Commercial%20Firmware-green?style=for-the-badge)]()

An ultra-responsive, studio-grade sound-reactive spectrum analyzer and LED music visualizer designed for custom audio setups, karaoke speakers, home theaters, and commercial matrix displays.

📖 **[Click Here to read the complete user's guide](https://github.com/wilson3682/esp32-visualizer/Complete_User's_Guide.md)**

---

## ⚡ Install Firmware in 60 Seconds (Free Web Installer)

You can flash this firmware directly from your web browser without downloading code or development tools:

👉 **[Click Here to Launch Web Serial Installer](https://wilson3682.github.io/esp32-visualizer/)**

> **Requirements:** Use **Google Chrome** or **Microsoft Edge** on a desktop or laptop computer and connect your ESP32 with a standard USB data cable.

---

## ✨ Features & Capabilities

* **Instant Beat & Transient Snap:** Professional-grade digital audio pickup via I2S microphone for razor-sharp response to kick drums, basslines, snares, and vocals.
* **Massive Visuals & Effects Portfolio:**
  * **25 Animation Patterns:** Standard theme bars, center-out bars, edge-to-center bars, inverted waterfalls, swaying orbital pulses, 4-way spectrogram streams, floating bioluminescent bubbles, calibrated 3-zone popcorn cannon, plasma aurora flames, scrolling horizontal wave bars, negative-space silhouette cutouts, and 3/6/9 sweeping volcanic magma calderas.
  * **105 Curated Color Themes:** Grouped into Classic & Studio EQ, Neon Cyber Synthwave, Scott Marley Specials, Dynamic Flows, Vibrant Atmospheric, Modern Luxury, and Dual Tri-Zone frequency splits.
  * **85 Peak Dot Modes:** Solids, dual-tones, alternating sweeps, tri-zone splits, cycles, metallics, pastels, and sparkles with falling gravity or cannon spark projectiles.
  * **18 Color Flow Directions:** Linear (Up, Down, Left, Right), 4-corner diagonals, radial bloom, radial implosion, center-out diamond ripple, 4-corner radials, harmonic wave collision, and single/dual Knight Rider scanners.

* **Universal 23-Mode Ambient Background Layer:**
  * **23 Ambient Styles (0 to 22):** Pitch black, theme flow canvas, cyber blue aura, deep synthwave glow, starfield sky, bioluminescent ocean, digital rain streams, molten caldera, harmonic ripples, and dynamic shifting random theme canvases (Modes 21 & 22).
  * **Mathematically Decoupled Brightness (1–50):** Background brightness is 100% independent of the main matrix brightness slider via dynamic inverse-scaling compensation.
  * **Music-Reactive Gating:** Background automatically illuminates with audio and smoothly fades to black during silence, or can be locked to "Always On".

* **Tri-Tier Autonomous Auto-Cycling & Shuffling:**
  * Independent timers for **Visual Patterns** (3–60s), **Color Themes** (3–60s), and **Background Themes** (3–60s).
  * Auto-cycle dropdown options (`255`) and independent linear/random shuffle toggles for all three layers.

* **50-Scene Master Show Playlist Engine:**
  * Program up to 50 automated scenes with custom patterns, themes, backgrounds, bar widths, speeds, and durations.
  * Non-destructive live updates: UI never rebuilds or drops dropdowns during background scene transitions.

* **Smart LED 5V Power Management & Configurable GPIO Pins:**
  * Configurable power limiter from **500 mA (0.5A) to 15,000 mA (15A)** to protect USB ports and power supplies.
  * **Fully Custom Pin Mapping:** Change GPIO pins for all 4 LED data strips, I2S microphone pins (WS, SD, SCK), and the IR remote receiver directly from the **Matrix** tab without recompiling.

* **Dedicated Parametric Equalizer Studio (`/eq`):**
  * Fine-tune 16 or 32 individual frequency bands with room ambient noise-floor calibration.
  * **22 Acoustic Profiles:** 11 vocal presets (Vocal Clarity Pro, Warm Acoustic, Sibilance Tamer, Podcast) and 11 genre profiles (Club Sub-Bass, R&B, Rock, Lo-Fi, EDM).

* **Dual-Font Startup Intro & Typography:**
  * 7 boot animations (Radial Bloom, Matrix Rain, Dual Laser, Hyperspace Warp, Plasma Spiral, Diamond Shutter, Firework Mortar).
  * Dual-font rendering (standard 5×7 and compact 3×5 micro font) with two-line custom text banner and optional center pause delay.

* **Zero-Lag Web Dashboard & Sleep Protection:**
  * Lazy-loaded datasets prevent network buffer congestion.
  * Page Visibility API cleanly disconnects sleeping mobile tabs to prevent zombie connection freezes.
  * Accessible over home Wi-Fi or AP hotspot at **`http://vumeter.local`**.

* **Over-The-Air (OTA) Updates & IR Remote:**
  * Built-in browser firmware flasher at **`/update`**.
  * Optional NEC IR remote control for power, brightness, patterns, and themes.

---

## 🔌 Hardware Connections & Matrix Layout

### 1. Physical Matrix Layout & Orientation

The firmware is pre-configured for a **Vertical Serpentine (Zigzag)** layout. When viewing the display directly from the **front**:

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

* **Physical Origin:** LED 0 must be positioned at the **Bottom-Left corner** when viewed from the front.
* **Layout Format:** **Vertical Serpentine (Zigzag)**.
  * **Column 0 (First Column):** Data travels from **Bottom → Up**.
  * **Column 1 (Second Column):** Turns at the top and travels from **Top → Down**.
  * **Column 2 (Third Column):** Turns at the bottom and travels from **Bottom → Up**.
  * This alternating pattern continues across all columns.

---

### 2. Addressable LED Matrix (WS2812B / WS2811)
* **Power (5V & GND):** Connect directly to an external 5V power supply sized for your LED count. Ensure a common ground connection between the power supply and the ESP32.
* **Data Output Pins:** 
  * Defaults are assigned to `GPIO 0` (Strip 1), `GPIO 4` (Strip 2), `GPIO 16` (Strip 3), and `GPIO 17` (Strip 4). 
  * *Note:* You can change these pins dynamically at any time under the **📐 Matrix** tab in the web dashboard.

---

### 3. Audio Microphone (INMP441 Digital I2S)
| Microphone Pin | Connects to ESP32 | Notes |
| :--- | :--- | :--- |
| **VDD** | **3.3V** | Do NOT connect to 5V |
| **GND** | **GND** | Common Ground |
| **SD** | **GPIO 32** | Default Serial Data (Configurable in UI) |
| **WS** | **GPIO 15** | Default Word Select (Configurable in UI) |
| **SCK** | **GPIO 14** | Default Clock (Configurable in UI) |
| **L/R** | **GND** | Left Audio Channel |

---

### 4. Optional IR Remote Receiver (VS1838B / KY-022)
| Sensor Pin | Connects to ESP32 | Notes |
| :--- | :--- | :--- |
| **VCC (+)** | **3.3V** | Power |
| **GND (-)** | **GND** | Ground |
| **OUT (S)** | **GPIO 13** | Default Demodulated Signal (Configurable in UI) |

---

## 📱 Getting Started & First Connection

1. Flash your board using the **[Web Installer](https://wilson3682.github.io/esp32-visualizer/)** or upload the pre-compiled `.bin` file via the **`/update`** page.
2. Connect your smartphone or computer to the visualizer's Wi-Fi hotspot:
   * **Network Name (SSID):** `ESP32_VU_METER`
   * **Password:** `password123`
3. Open your browser and navigate to:
   * **Main Dashboard:** `http://192.168.4.1` or `http://vumeter.local`   
   * **OTA Firmware Update:** `http://vumeter.local/update`
4. Go to the **📐 Matrix** tab:
   * Configure your matrix width (columns), height (rows), custom GPIO pins, 5V power limit, and Wi-Fi credentials.
   * Click **💾 Save Geometry, Power, Pins & Network (Restart ESP32)**.

---

## 🔑 License Activation & Pricing (Donation)

This software includes a **free 2-minute demo mode** on every boot so you can verify your wiring, microphone sensitivity, and LED matrix before activating.

After 2 minutes of demonstration, the LEDs enter standby with a red indicator prompt. Each ESP32 contains a permanent, factory-burned hardware MAC address. To activate your board permanently:

1. Open the dashboard and navigate to the **📐 Matrix** tab.
2. Locate the **Device Hardware ID (MAC Address)** and click **📋 Copy**.
3. Contact us with your **Device Hardware ID** for pricing and activation key generation.
4. You will receive a unique cryptographic **Activation Key**. Paste it into the activation box on your dashboard and click **🔑 Activate Device**.

Once activated, your visualizer is permanently unlocked across all reboots, power cuts, and future OTA firmware updates!

### 📩 Contact for Pricing & License Keys
* **Developer / Sales:** *Wilson*
* **Email:** *[willypeter67@gmail.com]*

---

## 🎥 Video Demonstration

Check out the spectrum visualizer in action:

▶️ https://www.youtube.com/watch?v=FW67ffeyo0Y

▶️ https://www.youtube.com/watch?v=BLfNkWLkR30
