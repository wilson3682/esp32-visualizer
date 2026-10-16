# 🎛️ ESP32 Professional Audio Spectrum Visualizer

[![Web Installer](https://img.shields.io/badge/Web%20Installer-Flash%20Online-0284c7?style=for-the-badge&logo=googlechrome&logoColor=white)](https://wilson3682.github.io/esp32-visualizer/)
[![Platform](https://img.shields.io/badge/Platform-ESP32%20Hardware-38bdf8?style=for-the-badge)]()
[![Status](https://img.shields.io/badge/Status-Commercial%20Firmware%20v1.2-green?style=for-the-badge)]()

An ultra-responsive, studio-grade sound-reactive spectrum analyzer and LED music visualizer appliance engineered for custom audio racks, commercial equalizer displays, karaoke stages, home theaters, architectural mood lighting, and high-density addressable LED matrix installations.

📖 **[Click Here to read the complete user's guide](https://github.com/wilson3682/esp32-visualizer/blob/main/Complete_User's_Guide.md)**

---

## ⚡ Install Firmware in 60 Seconds (Free Web Installer)

Flash this firmware directly from your web browser without downloading code, compilers, or development software:

👉 **[Click Here to Launch Web Serial Installer](https://wilson3682.github.io/esp32-visualizer/)**

> **Requirements:** Use **Google Chrome** or **Microsoft Edge** on a desktop or laptop computer and connect your ESP32 with a standard USB data cable.

---

## 🔌 Recommended "Plug & Play" Hardware Controller

Don't want to deal with loose breadboards, jumper wires, or soldering level shifters? We recommend this ready-to-run ESP32 addressable LED controller:

🛒 **[View & Order the Tested ESP32 Controller on Amazon](https://www.amazon.com/dp/B0F5B2G6P5?ref=ppx_yo2ov_dt_b_fed_asin_title&th=1)**

### 🛠️ Tested & Verified Out of the Box:
* **Zero Soldering Required:** Complete with heavy-duty screw terminals for power (`V+`, `GND`) and LED strip/matrix data connections.
* **Tested Output Pin:** Fully tested, validated, and confirmed to work straight out of the box using **Output IO Pin 16 (`GPIO 16`)**.
* **Clean 5V Signal:** Integrated logic-level shifting ensures rock-solid signal transmission to WS2812B/WS2811/SK6812 LEDs without data line flickering.
* **Wide Voltage Support:** Supports common 5V–24V DC input rails to match your LED setup power supply.
* **Fast Setup:** Simply plug it into your computer via USB, flash the firmware binary using our **[Web Installer](https://wilson3682.github.io/esp32-visualizer/)**, wire your LED data line to **IO 16**, and you are ready to visualize!

> ⚠️ **Power Supply Recommendation:**  
> For maximum visual performance, rock-solid stability, and zero brownout resets, **a high-quality 5V power supply rated for at least 10 Amps (5V @ 10A / 50W+) is highly recommended**. Addressable LED matrices draw significant current during white flashes and energetic sub-bass transient spikes. An underpowered supply will cause voltage drop, LED discoloration, flickering, or controller reboots.

---

## ✨ Features & Capabilities

### 🚀 High-Precision Acoustic Response & Real-Time DSP
* **Digital I2S Audio Pipeline:** High-speed 32-bit digital audio acquisition operating at a locked 12.0 kHz sampling frequency for razor-sharp response to kick drums, sub-bass transients, snares, and vocal harmonics.
* **Assembly-Accelerated Radix-2 FFT:** Employs optimized 512-point hardware FFT with 256 frequency bins and Hann windowing on Core 0, operating under FreeRTOS mutex protection.
* **Continuous Real-Time Physics ($\Delta t$):** Frame-rate independent physics engine calculating true delta-time gravity, ballistic bar drops, and floating peak dot hang/fall decay times.
* **Deep-Range Noise Gate Filter:** Configurable noise suppression filter ($0\text{ to }5,000\text{ units}$ via `* 50.0f` scalar) rejecting ambient room hum, PC fans, and air conditioning noise while preserving delicate musical passages.

---

### 🎨 Massive Visual Effects Portfolio
* **37 Advanced Visualizer Engines (Patterns 0 to 36):**
  * **Classic Equalizer Modes:** Floor-anchored bars, ceiling-hung inverted bars, symmetrical center-out bars, edge-to-center converging bars, and floating peak dots with independent ballistic timers.
  * **Kinetic & Procedural Generators:** Sweeping multi-caldera volcanic magma cannons (up to 18 calderas and 160 embers), ballistic popcorn cannons (up to 80 gravity-simulated particles with high-frequency boost and 3 sizing profiles), 40 reactive bioluminescent floating bubbles, 4-way spectrogram waterfall stream (Left, Right, Down, Up), and undulating plasma aurora flame beds (Floor, Ceiling, Center-Out, Edge-to-Center).
  * **Harmonic & Sacred Geometric Engines:** Resonant Cymatic kaleidoscopes (direction-reversing 8-fold Chladni resonance), infinite hypnotic warp tunnels, multi-knot Lissajous harmonograph laser ribbons, liquid silk harmonic waves with Gaussian additive color blending, 2D psychedelic fluid noise meshes, multi-orbital sacred lotus mandalas (up to 50+ LEDs wide), kaleidoscopic resonant vector lines, orbital liquid silk vortexes, orbital warp tunnels, and floating sweeping cymatics plates.
  * **Negative-Space Silhouette Cutouts:** Cutout equalizer bars carved out of ambient background shaders with black projectile cannon sparks.
  * **Intelligent Negative-Space Protection:** Automatically engages an active flow canvas whenever negative-space or dots-only patterns are selected while the background is set to pitch black, preventing displays from ever sitting in total darkness.

---

### 🛋️ Ambient Relaxation Lamp Mode (`🛋️ Lamp`)
* **Dual-Personality Appliance:** Instantly transforms your spectrum visualizer into a luxury studio mood lamp via a single touch of the `#lampModeBtn` in the top bar.
* **Audio Muted & Bar Suppression:** The digital microphone audio stream is muted, and all equalizer bars, dots, and sparks are suppressed.
* **Silence-Gating Bypassed:** Full-surface continuous illumination allows all 7 procedural relaxation shaders and 120 theme flow canvases to operate without music.
* **Auto-Background Memory:** Entering Lamp Mode preserves your previous auto-background settings and automatically restores them upon returning to Spectrum Mode.

---

### 🌌 Universal 154-Mode Ambient Background Layer
* **154 Total Background Canvases (Modes 0 to 153):**
  * **Mode 0:** Pure Pitch Black (Clean Default).
  * **Modes 1 to 26 (Curated Ambient Shaders):** Cyber Blue Aura, Synthwave Glow, Sunset Horizon, Twinkling Starfield, Ocean Abyss, Digital Rain Streams, Molten Caldera, Caustic Shimmer, Liquid Prismatic Oil Slick, Archimedean Spiral, Precision Vector Grid, and more.
  * **Modes 27 to 33 (7 Procedural Ambient Relaxation Shaders):**
    * *Mode 27: Convective Thermal Fire & Embers Bed:* Roaring multi-octave thermal draft (`nowMs/5`) reaching **75% to 85% of total matrix height**, intense floor embers bed, and zero floating-point latency.
    * *Mode 28: Drifting Winter Blizzard & Snow:* Dual-layer snowflake particle simulation with wind sway and floor frost accumulation.
    * *Mode 29: Bioluminescent Firefly Swarm:* 8 organic wandering fireflies with $3\times$ faster harmonic flight and direct Gaussian radial glow stamping (zero inner-loop CPU cost).
    * *Mode 30: Concentric Water Droplets & Ripples:* Expanding caustics wave propagation with pre-calculated droplet centers.
    * *Mode 31: Horizontal Prismatic Aurora Waves:* Continuous non-wrapping wave undulation.
    * *Mode 32: Organic Bioluminescent Slime / Mold Flow:* Continuous 16-bit noise drift with pre-calculated trigonometric wobble uniforms.
    * *Mode 33: Neon Cyber Lava Fluid Flow:* High-speed liquid wax convection, molten hot-magenta body, electric-cyan rims, and radiant amber thermal core.
  * **Modes 34 to 153 (120 Dedicated Theme Flow Canvases):** Allows setting any of the 120 color themes as an independent, flowing background layer behind foreground bars ($34 + \text{themeIndex}$).
* **Complete 153-Mode Non-Repeating Shuffle Deck (`bgDeck[153]`):**
  * Shuffles **all 153 illuminated background modes** (Modes 1 to 153) using ESP32 hardware silicon entropy (`esp_random()`).
  * **Every single background in the entire catalog displays once before any can repeat.**
  * Mode 0 (Pure Pitch Black) is strictly excluded from auto-cycling.
  * Anti-clash boundary swap prevents consecutive repeats across cycles.
* **100% Mathematically Decoupled Brightness:** Inversely scales with master brightness so changing the main slider never washes out ambient backdrops.
* **Music-Reactive Gating:** Background automatically illuminates with audio transients and gently fades to black during quiet pauses, or can be toggled to "Always On".

---

### 🌊 24 Flow Directions (0 to 23) & Re-Indexed Static Mode
* **Direction 0: Static / Stationary (No Flow Motion):** Freezes flow coordinates at timer zero, producing a motionless, fixed gradient across any color theme.
* **Directions 1 to 23 (Active Dynamic Flows):** Orthogonal flows (Up, Down, Left, Right), 4-corner diagonals, radial blooms, radial implosions, diamond ripples, corner radials, harmonic cross-collisions, kinetic counter-crossing scanner beams, Archimedean spiral vortexes, quad-wave ripple blooms, and sweeping ceiling spotlights.
* **Auto Flow Architecture:**
  * Toggling Auto Flow **OFF** immediately engages **Direction 0 (Static / Stationary)**.
  * Toggling Auto Flow **ON** automatically advances into dynamic moving flows (1 to 23).
  * The dedicated Flow Shuffle Deck (`flowDeck[23]`) shuffles directions 1 to 23, reserving Static 0 for manual selection.

---

### 🌈 120 Curated Color Themes & Staged Tri-Zone Engine
* **120 Professional Color Themes (Themes 0 to 119):**
  * Grouped into Classic Studio EQs, Neon Cyber Synthwave, Studio Signature Specials, Dynamic Multi-Flow Palettes, Vibrant Atmospherics, Luxury Cyber, and Tri-Zone Frequency Splits.
* **Interactive Color Spectrum Wheel & Pure White Center Core:**
  * Sized for effortless touch control with an illuminated **`WHITE`** center touch target. Tapping the center core instantly engages pure white across all bands or onto a staged acoustic zone.
* **Staged Tri-Zone Palette Customizer (Theme 119):**
  * Stage custom colors across Zone 1 (Bass/Lows), Zone 2 (Midrange/Vocals), and Zone 3 (Treble/Highs) using interactive circle swatches before committing them live to the matrix.

---

### 🎯 120 Peak Dot Palette Modes & Real-Time Auto Match
* **120 Peak Dot Modes (0 to 119):**
  * Direct 1-to-1 parity with the color themes, featuring solids, metallic finishes (Gold, Platinum, Bronze, Rose Gold), neon duos, stroboscopic sweeps, alternating pastel pairs, and chromatic cycles.
* **Real-Time Dynamic Theme Match (Mode 0):**
  * Automatically resolves the exact contrasting peak color defined for whichever theme is playing, updates the live preview ribbon, and scrolls the dropdown to highlight the active applied color.
* **Ballistic Action Modes:** Choose between standard falling gravity dots or explosive projectile cannon sparks.

---

### 🖥️ Studio Console Web Interface & Zero-Scroll Browsing
* **True Desktop PC Mode $\leftrightarrow$ Mobile Phone View Emulation:**
  * **🖥️ PC Mode (Desktop):** All 3 performance columns displayed side-by-side across the monitor with the bottom dock hidden.
  * **📱 Phone View Mode:** Simulates a mobile smartphone interface on a PC monitor, rendering a single centered column ($480\text{px}$ wide) with an active 60px bottom navigation dock.
* **Adaptive Screen-Height Fit:** All 3 desktop columns dynamically stretch to fit 100% of the screen height, terminating at the exact same bottom boundary pixel line with **zero outer page scrolling**.
* **Deselect on Auto-OFF & Zero Scroll Snapping:** Turning Auto OFF for Themes, Patterns, or Backgrounds immediately deselects the list (`selectedIndex = -1`). While browsing manually, background telemetry from other active cycles will **never** snap, reset, or hijack your scroll position.
* **Dynamic Live Gradient Ribbons:** Real-time multi-stop CSS gradient bars positioned directly above the Color Themes, Background Modes, and Peak Dot lists that update instantly during manual selection, auto-cycling, and initial page load.
* **Modular Drawer Modals:** Secondary tuning controls (flow speeds, procedural speeds, volcano calderas, acoustic filters, and ballistics) are organized inside 3 streamlined sub-drawers (`modalThemeControls`, `modalEffectControls`, `modalAcousticControls`).
* **Chunked HTTP Streaming:** High-performance web server delivering the dashboard in modular non-blocking flash chunks with FreeRTOS yields (`vTaskDelay(pdMS_TO_TICKS(5))`), protecting Core 0 TCP memory.

---

### 🎛️ Graphic Equalizer Studio (`/eq`) & Acoustic Profiles
* **Dynamic Band Switching (16, 32, or 64 Bands):** Automatically switches frequency resolution based on display geometry and column widths ($1\text{ to }4\text{ LEDs per band}$).
* **Factory Default Profile ("Vocal Air & Breath"):** Tuned with restrained sub-bass, smooth vocal presence, and an airy high-frequency boost.
* **22 Pre-Calibrated Acoustic Profiles:** 11 vocal & speech profiles (Vocal Clarity Pro, Warm Acoustic, Pop Lead, Speech, De-Esser, Broadcast Radio) and 11 genre profiles (Club Sub-Bass, R&B, Rock, Lo-Fi Chill, EDM, Classical).
* **10 Band-Aware User Custom Presets:** Completely isolated flash storage for 10 custom curves per band resolution, featuring editable slot names and full JSON export/import sharing.
* **Frequency Cutoffs Capped at Bin 216 ($5,062.5\text{ Hz}$):** Guarantees identical energetic spread across 16, 32, and 64 bands without inactive high-frequency columns.

---

### 🎬 Master Show Playlist Sequencer
* **50-Scene Capacity:** Program up to 50 automated showcase scenes stored permanently in flash memory.
* **Complete Parameterization:** Each scene customizes pattern (0–36 or Auto), theme (0–119 or Auto), background (0–153 or Auto), flow direction (0–23), bar width, peak dot behavior, color, thickness, kinetic engine speeds, and duration ($3\text{ to }300\text{ seconds}$).
* **Cold Boot Isolation (`showB`):** Governs whether Master Show launches automatically upon power-on, protecting standalone visualizer setups.

---

### ⚙️ Configuration Hub & Safe Hardware Storage
* **Pinned Sub-Menu Navigation:** Sub-menu tabs are anchored as a fixed header outside the scrollable body so navigation tabs never scroll out of view.
* **4 Dedicated Sub-Pages:**
  * **📶 Wi-Fi & Device:** Station setup (connect to home Wi-Fi), hardware MAC identification, cryptographic licensing.
  * **📐 Matrix & Hardware:** Matrix geometry, dynamic parallel output bus, modular clustering, mounting orientation, LED chipset/color order, microphone profiles, mains power relay, and IR receiver.
  * **🚀 Startup Intro:** Dual-font typography (5x7 standard and 3x5 compact), customizable two-line boot messages, 7 startup animations, and center pause delay timers.
  * **💾 Backup & Storage:** Dedicated flash commit button (`💾 Save General Settings to Flash`), atomic general settings JSON backup/restore (`spectrum_general_config.json`), and factory defaults reset.
* **Guaranteed Hardware Pin Persistence:** Live global RAM variables are committed immediately before NVS flash saves, ensuring `relayPin`, `rMode`, microphone pins, IR pin, and topology routing never revert on reboot.

---

### ℹ️ Appliance Telemetry, Live Diagnostics & Hardware Inspector
* **Live System & Network Diagnostics:**
  * **Hardware MAC ID:** Permanent factory silicon MAC address.
  * **SoftAP Address:** Live gateway address (`192.168.4.1`) for direct AP connection.
  * **Station Network IP:** Shows router-assigned IP (`192.168.1.x`) or `"Not Connected (AP Only)"`.
  * **Wi-Fi Signal (RSSI):** Live signal strength in dBm with color-coded badges (Green $\ge -65\text{ dBm}$, Yellow $\ge -75\text{ dBm}$, Red weak).
  * **Appliance Uptime:** Real-time operational uptime counter formatted dynamically into minutes and seconds (`135m 58s`) or hours (`2h 15m 58s`).
  * **🔄 Restart Appliance Button:** Direct, safe software reboot button with confirmation dialog.
  * **Wireless OTA Updater:** One-touch access to `/update` for browser-based wireless firmware flashing.
* **Hardware GPIO Conflict Inspector:** Actively cross-references all assigned pins across the 8-channel bus, digital mic, IR receiver, and mains relay, highlighting in-use pins and emitting conflict warnings.

---

## 🔌 Hardware Connections & Matrix Layout

### 1. Coordinate Mapping & 4-Way Spatial Orientation

The graphics and DSP engine renders to a virtual canvas where **(0, 0) is always the physical Bottom-Left origin**. Frequency bars rise vertically from Y=0 towards the top.

* **4-Way Spatial Mounting Orientation:**
  * `0`: **Normal** (Standard floor-standing Bottom-Left origin).
  * `1`: **Flip Vertical** (Ceiling-hung mounting with inverted Y axis).
  * `2`: **Flip Horizontal** (Mirrored / rear-projection display).
  * `3`: **Rotate 180°** (Dual-axis inverted mounting).

---

### 2. Monolithic Custom Strip Wiring (Vertical Serpentine)

For custom frames wired from continuous addressable LED tape, wire columns in **Vertical Serpentine (Zigzag)** format starting at LED 0 (Bottom-Left):

```text
┌─────────────────────────────────────────────────────────────┐
│                 FRONT VIEW OF THE LED MATRIX                │
├─────────────────────────────────────────────────────────────┤
│                                                             │
│   (Top-Left)                                    (Top-Right) │
│     (15) ───▶ (16)     (47) ───▶ (48)                       │
│      ▲         │        ▲         │                         │
│      │         │        │         │   ... (Zigzag continues │
│      │         ▼        │         ▼        across columns)  │
│     (0)       (31) ───▶ (32)     (63)                       │
│   [Col 0]   [Col 1]   [Col 2]   [Col 3]                     │
│                                                             │
│    [LED 0]                                  (Bottom-Right)  │
│ (Bottom-Left)                                               │
│   DATA IN ──►                                               │
└─────────────────────────────────────────────────────────────┘
```

---

### 3. Modular 16×16 Panel Cluster Architecture

Commercial 16×16 addressable LED panels (256 LEDs per panel) can be tiled seamlessly to assemble large studio-grade displays:
* **Supported Modular Sizes:** $16\times16$ (256 LEDs), $16\times32$ (512 LEDs), $16\times48$ (768 LEDs), $32\times64$ (2,048 LEDs), $48\times64$ (3,072 LEDs), $64\times64$ (4,096 LEDs), $32\times128$ (4,096 LEDs).
* **Macro Chaining (`panelChaining`):**
  * `0`: **Horizontal Snake** (Row 0 runs L $\to$ R, loop up to Row 1 running R $\to$ L).
  * `1`: **Horizontal Progressive** (Every row runs L $\to$ R).
  * `2`: **Vertical Snake** (Col 0 runs Bottom $\to$ Top, Col 1 runs Top $\to$ Bottom).
* **Micro Wiring (`panelWiring`):**
  * `0`: **Horizontal Serpentine** (Standard panel internal zigzag).
  * `1`: **Vertical Serpentine** (Columns alternate internally).

```text
Row 1 (Top):     [Panel 7] ◀── [Panel 6] ◀── [Panel 5] ◀── [Panel 4]
                                                              ▲
                                                              │ (Daisy-chain loop up)
Row 0 (Bottom):  [Panel 0] ──▶ [Panel 1] ──▶ [Panel 2] ──▶ [Panel 3]
                    ▲
                   DIN (From ESP32 GPIO)
```

---

### 4. Dynamic 8-Channel Parallel Output Bus

Supports **1 to 8 hardware parallel output lines** driven concurrently via the ESP32 hardware RMT peripheral:
* **Per-Channel Pin Allocation:** Configurable GPIO pins (`ledPins[8]`) across 20 safe ESP32 GPIOs (`0, 2, 4, 5, 12, 13, 14, 15, 16, 17, 18, 19, 21, 22, 23, 25, 26, 27, 32, 33`).
* **Per-Channel Length Allocation:** Custom strip lengths (`ledLengths[8]`) dynamically sliced across contiguous memory.
* **Auto-Balance Fallback:** Auto-splits total LEDs equally across all active channels if unconfigured.

---

### 5. Smart LED Chipset Pinouts & Backup Data Lines

* **3-Wire Standard (WS2812B / SK6812 / WS2811):** Pins are `VCC`, `DIN`, `GND`. Color order is typically **GRB** (5V) or **RGB** (12V).
* **4-Wire Dual-Data Backup (WS2813 / WS2815):** Features an auxiliary backup data line (`BIN` / `BOUT`) that bypasses individual dead pixels so remaining LEDs stay lit.

```text
ESP32 GPIO ────▶ [DIN] Panel 1 [DOUT] ────────▶ [DIN] Panel 2 [DOUT] ──▶ ...
GND ───────────▶ [BIN] Panel 1 [BOUT] ──┬─────▶ [BIN] Panel 2 [BOUT] ──▶ ...
                                        │
                       (Backup Data Jump)
```
* **First Pixel Rule:** Connect `BIN` on the very first strip/panel directly to **GND**. Connect `DOUT` to `DIN`, and `BOUT` to `BIN` for all subsequent panels.
* ⚠️ **Voltage Warning:** WS2815 and 12V WS2811 require **12V DC** connected to VCC. Connecting 12V directly to the ESP32 will permanently damage the microcontroller. Always share a common Ground (GND).

---

### 6. High-Current 5V Parallel Power Distribution Rules

```text
           ┌──────────────────────────────────────────────┐
  +5V ─────┼───────┬──────────────┬──────────────┬────────┤ (+5V Parallel Bus Bar)
           │       │ +5V          │ +5V          │ +5V    │
        [ESP32] [Panel 0]      [Panel 1]      [Panel 2]  ...
           │       │ GND          │ GND          │ GND    │
  GND ─────┼───────┴──────────────┴──────────────┴────────┤ (GND Parallel Bus Bar)
           └──────────────────────────────────────────────┘
```
* ⚠️ **Mandatory Rule:** Never route high-current 5V DC power in series through thin matrix copper traces. Run heavy-gauge wire (14–16 AWG) directly from your power supply to a parallel distribution bus bar, tapping 5V and GND directly to every single panel.

---

### 7. Unified 3-State Hardware Mains Relay Wiring

The hardware relay cuts AC/DC mains power to external LED power supplies when the visualizer is placed in standby, eliminating idle power draw and power supply coil whine:

```text
  ESP32 GPIO 18 ─────────▶ Relay IN
  ESP32 3.3V / 5V ───────▶ Relay VCC
  ESP32 GND ─────────────▶ Relay GND

  Relay COM / NO ────────▶ Switches Live 120V/240V AC to LED Power Supplies
```
* **Mode 0:** Disabled (Pin driven LOW/idle).
* **Mode 1: Active HIGH:** Direct NPN/MOSFET-driven relay boards (3.3V logic closes relay).
* **Mode 2: Active LOW:** Optically isolated relay boards (0V ground logic closes relay).

---

### 8. Audio Microphone Interface (Digital I2S)
| Microphone Pin | Connects to ESP32 | Notes |
| :--- | :--- | :--- |
| **VDD** | **3.3V** | Do NOT connect to 5V |
| **GND** | **GND** | Common Ground |
| **SD** | **GPIO 26** (or 32 / 25) | Serial Data Input (Configurable in UI) |
| **WS** | **GPIO 5** (or 15) | Word Select / Clock (Configurable in UI) |
| **SCK** | **GPIO 21** (or 14) | Bit Clock (Configurable in UI) |
| **L/R** | **GND** | Left Audio Channel |

---

### 9. Optional IR Remote Receiver (VS1838B / KY-022)
| Sensor Pin | Connects to ESP32 | Notes |
| :--- | :--- | :--- |
| **VCC (+)** | **3.3V** | Power |
| **GND (-)** | **GND** | Ground |
| **OUT (S)** | **GPIO 33** | Demodulated Signal (Configurable in UI) |

---

## 📱 Getting Started & First Connection

1. Flash your board using the **[Web Serial Installer](https://wilson3682.github.io/esp32-visualizer/)** or upload the pre-compiled firmware binary via the **`/update`** page.
2. Connect your smartphone, tablet, or PC to the visualizer's Wi-Fi hotspot:
   * **Network Name (SSID):** `ESP32_VU_METER`
   * **Password:** `password123`
3. Open any modern browser and navigate to:
   * **Main Dashboard:** `http://192.168.4.1` or `http://vumeter.local`
   * **Equalizer Studio:** `http://vumeter.local/eq`
   * **Wireless OTA Update:** `http://vumeter.local/update`
4. Open the **⚙️ Config** hub:
   * Select the **📐 Matrix & Hardware** tab to configure your matrix width, height, power limiter, and output channels.
   * Switch to the **📶 Wi-Fi & Device** tab to optionally enter your home Wi-Fi network credentials.
   * Click **💾 Save Configuration & Reboot**.

---

## 🔑 License Activation & Pricing

This software includes a **free 2-minute demonstration mode** on every boot, allowing you to test all visual patterns, themes, backgrounds, relaxation lamp modes, microphone sensitivity, and web controls before activating.

After 2 minutes of active audio visualization, the display enters standby with a red indicator prompt. Each microcontroller contains a unique, factory-burned hardware MAC address.

### How to Activate Your Device:
1. Open the dashboard and click the **⚙️ Config** button.
2. Under the **📶 Wi-Fi & Device** tab, locate the **Device Hardware MAC** and click **📋 Copy**.
3. Visit the licensing page to obtain your permanent activation key.
4. Paste your activation key into the activation box and click **🔑 Activate Device**.

Once activated, your visualizer is permanently unlocked across all reboots, power cuts, and future wireless OTA updates!

### 📩 Contact & License Generation
* **Developer / Commercial Sales:** *Wilson*
* **Purchase Your License Key:** **[https://willpeter67.gumroad.com/l/tqffir](https://willpeter67.gumroad.com/l/tqffir)**
* **Direct Support Email:** *[willpeter67sales@gmail.com](mailto:willpeter67sales@gmail.com)*

---

## 🎥 Video Demonstration

Check out the spectrum visualizer in action on dual-panel and large studio matrix installations:

▶️ **[Watch Spectrum Visualizer Demo Part 1 (Color Themes & Bars)](https://github.com/wilson3682/esp32-visualizer)**  
▶️ **[Watch Spectrum Visualizer Demo Part 2 (Cymatics, Mandalas & Plasma)](https://github.com/wilson3682/esp32-visualizer)**

---

*Professional LED Audio Spectrum Visualizer • Commercial Equalizer Display Appliance Firmware*
