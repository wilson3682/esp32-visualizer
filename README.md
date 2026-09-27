# 🎛️ ESP32 Professional Audio Spectrum Visualizer

[![Web Installer](https://img.shields.io/badge/Web%20Installer-Flash%20Online-0284c7?style=for-the-badge&logo=googlechrome&logoColor=white)](https://wilson3682.github.io/esp32-visualizer/)
[![Platform](https://img.shields.io/badge/Platform-ESP32%20Hardware-38bdf8?style=for-the-badge)]()
[![Status](https://img.shields.io/badge/Status-Commercial%20Firmware%20v1.1-green?style=for-the-badge)]()

An ultra-responsive, studio-grade sound-reactive spectrum analyzer and LED music visualizer engineered for custom audio racks, commercial equalizer displays, karaoke stages, home theaters, and high-density LED matrix installations.

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

### 🚀 High-Precision Acoustic Response & Transient Snap
* **Digital I2S Audio Pipeline:** High-speed 32-bit digital audio acquisition operating at a locked 12.0 kHz sampling rate for razor-sharp response to kick drums, sub-bass transients, snares, and vocal harmonics.
* **Continuous Real-Time Physics ($\Delta t$):** Frame-rate independent physics engine calculating true delta-time gravity, ballistic bar drops, and floating peak dot hang/fall decay times.
* **Deep Noise Gate Filter:** Configurable noise suppression filter ($0\text{ to }5,000\text{ units}$) rejecting ambient room hum and air conditioning noise while preserving delicate musical passages.

---

### 🎨 Massive Visual Effects Portfolio
* **37 Advanced Visualizer Engines (Patterns 0 to 36):**
  * **Classic Equalizer Modes:** Floor-anchored bars, ceiling-hung inverted bars, symmetrical center-out bars, edge-to-center converging bars, and floating peak dots with dedicated hang/fall timers.
  * **Kinetic & Procedural Generators:** Sweeping multi-caldera volcanic magma cannons (up to 18 calderas and 160 embers), ballistic popcorn cannons (up to 80 gravity-simulated particles with high-frequency boost), 40 reactive bioluminescent floating bubbles, 4-way spectrogram waterfall stream (Left, Right, Up, Down), and undulating plasma aurora flame beds (Floor, Ceiling, Center-Out, Edge-to-Center).
  * **Sacred & Resonant Geometric Engines:** Resonant Cymatic kaleidoscopes (direction-reversing 8-fold Chladni resonance), infinite hypnotic warp tunnels, multi-knot Lissajous harmonograph laser ribbons, liquid silk harmonic waves with Gaussian additive color blending, 2D psychedelic fluid noise meshes, multi-orbital sacred lotus mandalas (up to 50+ LEDs wide), kaleidoscopic resonant vector lines, and roaming liquid silk vortexes.
  * **Negative-Space Silhouette Cutouts:** Cutout equalizer bars carved out of ambient background shaders with black projectile cannon sparks.
  * **Intelligent Negative-Space Protection:** Automatically engages an active flow canvas whenever negative-space or dots-only patterns are active, preventing displays from ever sitting in pitch black.

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
  * When in Auto Match mode, the system dynamically resolves the exact contrasting peak color for whichever theme is playing, updates the live preview ribbon, and scrolls the dropdown to highlight the active applied color.
* **Ballistic Action Modes:** Choose between standard falling gravity dots or explosive projectile cannon sparks.

---

### 🌌 Universal 147-Mode Ambient Background Layer
* **147 Total Background Canvases (Modes 0 to 146):**
  * **Mode 0:** Pure Pitch Black (Clean Default).
  * **Modes 1 to 26 (Curated Ambient Shaders):** Cyber Blue Aura, Synthwave Glow, Sunset Horizon, Twinkling Starfield, Ocean Abyss, Digital Rain Streams, Molten Caldera, Caustic Shimmer, Liquid Prismatic Oil Slick, Archimedean Spiral, and Precision Vector Grid.
  * **Modes 27 to 146 (Theme Canvases):** Allows setting any of the 120 color themes as an independent, flowing background layer behind foreground bars.
* **Front-Panel Brightness Slider:** Positioned directly on the main console for instant one-touch adjustment of background intensity.
* **Mathematically Decoupled Brightness Engine:** Inverse compensation isolates background brightness from the master matrix brightness slider.
* **Music-Reactive Gating:** Background automatically illuminates with audio transients and gently fades to black during quiet pauses, or can be set to "Always On".

---

### 🌊 23 Flow Directions & Hardware TRNG Shuffle Engine
* **23 Directional Flow Dynamics:** Orthogonal flows (Up, Down, Left, Right), 4-corner diagonals, radial blooms, radial implosions, diamond ripples, corner radials, harmonic cross-collisions, kinetic counter-crossing scanner beams, Archimedean spiral vortexes, quad-wave ripple blooms, and sweeping ceiling spotlights.
* **Silicon Entropy Fisher-Yates Shuffle Decks:**
  * Powered by the ESP32's native true random number generator (`esp_random()`).
  * Features anti-clash swap protection ensuring that no pattern, theme, background, or flow direction ever repeats twice in a row.

---

### 🖥️ Studio Console Web Interface & Dual Display Modes
* **True Desktop PC Mode $\leftrightarrow$ Mobile Phone View Emulation:**
  * **🖥️ PC Mode (Desktop):** All 3 performance columns displayed side-by-side across the monitor with the bottom dock hidden.
  * **📱 Phone View Mode:** Simulates a mobile smartphone interface on a PC monitor, rendering a single centered column ($480\text{px}$ wide) with an active bottom navigation dock.
* **Adaptive Screen-Height Fit:** All 3 desktop columns dynamically stretch to fit 100% of the screen height, terminating at the exact same bottom boundary pixel line with **zero outer page scrolling**.
* **Dynamic Live Gradient Ribbons:** Real-time multi-stop CSS gradient bars positioned directly above the Color Themes, Background Modes, and Peak Dot lists that update instantly during manual selection, auto-cycling, and initial page load.
* **Modular Drawer Modals:** Secondary tuning controls (flow speeds, procedural speeds, volcano calderas, acoustic filters, and ballistics) are organized inside 3 streamlined sub-drawers (`modalThemeControls`, `modalEffectControls`, `modalAcousticControls`).
* **5-Stage Chunked HTTP Streaming:** High-performance web server delivering the dashboard in 5 non-blocking flash chunks with FreeRTOS yields, preventing TCP buffer congestion.

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
* **Complete Parameterization:** Each scene customizes pattern (0–36 or Auto), theme (0–119 or Auto), background (0–146 or Auto), bar width, peak dot behavior, color, thickness, kinetic engine speeds, and duration ($3\text{ to }300\text{ seconds}$).
* **Decoupled DOM Card Builder:** Scene parameter updates modify only extra controls without destroying dropdowns, preserving keyboard and touch navigation.

---

### ⚙️ Configuration Hub & Safe Storage Management
* **Pinned Sub-Menu Navigation:** Sub-menu tabs are anchored as a fixed header outside the scrollable body so navigation tabs never scroll out of view.
* **4 Dedicated Sub-Pages:**
  * **📶 Wi-Fi & Device:** Station setup (connect to home Wi-Fi), hardware MAC identification, licensing.
  * **📐 Matrix & Hardware:** Matrix geometry, parallel output channels, microphone profiles, mains power relay, and IR receiver.
  * **🚀 Startup Intro:** Dual-font typography (5x7 standard and 3x5 compact), customizable two-line boot messages, 7 startup animations, and center pause delay timers.
  * **💾 Backup & Storage:** Dedicated flash commit button (`💾 Save General Settings to Flash`), atomic general settings JSON backup/restore (`spectrum_general_config.json`), and factory defaults reset.
* **Context-Aware Hardware Reboot Button:** The hardware restart button is displayed strictly on tabs that alter physical hardware (Wi-Fi and Matrix geometry), removing confusion on general setting tabs.
* **Hardware Mains Power Relay Support:** Active-HIGH relay control that automatically energizes on power-on and drops on standby to disconnect AC mains power from external LED power supplies, eliminating coil whine and idle power draw.

---

## 📱 Getting Started & First Connection

1. Flash your board using the **[Web Serial Installer](https://wilson3682.github.io/esp32-visualizer/)** or upload the firmware binary via the **`/update`** page.
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

This software includes a **free 2-minute demonstration mode** on every boot, allowing you to test all visual patterns, themes, backgrounds, microphone sensitivity, and web controls before activating.

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

Check out the spectrum visualizer in action:

▶️ https://www.youtube.com/watch?v=FW67ffeyo0Y

▶️ https://www.youtube.com/watch?v=BLfNkWLkR30

---

*Professional LED Audio Spectrum Visualizer • Commercial Appliance Firmware*
