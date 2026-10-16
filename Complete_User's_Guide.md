### Tab 1: 📶 Wi-Fi & Device
* **Connection Mode:** Access Point Only (`ESP32_VU_METER`) or Connect to Home Wi-Fi (AP + Station mode).
* **Home Wi-Fi Credentials:** Network SSID and Password fields.
* **Network Status:** Displays the local IP address assigned by your home router.
* **Hardware Identity & Activation:** Displays the permanent factory silicon MAC address with a **📋 Copy** button, license activation status, and cryptographic activation key input box.

### Tab 2: 📐 Matrix & Hardware
* **Matrix Geometry:** Physical Columns (16, 32, 48, 64, or 128) and Row Height (8 to 64 rows). Displays live total LED count.
* **Smart 5V Power Limiter:** Sets maximum current budget from **500 mA (0.5A)** up to **20,000 mA (20A)** in 250 mA increments to protect USB ports and power supplies.
* **Panel Architecture & 4-Way Mounting Orientation:**
  * *Panel Structure:* Monolithic Sheet / Continuous Strip vs. Modular $16\times16$ Panel Cluster.
  * *Mounting Orientation:* Normal (Floor), Flip Vertical (Ceiling), Flip Horizontal (Mirrored), Rotate 180° (Dual-axis inverted).
  * *Modular Panel Cluster Settings (when enabled):*
    * Panel Interconnect: Horizontal Snake, Horizontal Progressive, Vertical Snake.
    * Internal 16×16 Wiring: Horizontal Serpentine, Vertical Serpentine.
* **LED Chipset Protocol & Color Order:**
  * *Chipset Models:* WS2812B/SK6812 (5V 3-Wire), WS2813 (5V 4-Wire Dual-Data), WS2815 (12V 4-Wire Dual-Data), WS2811 (12V/5V 3-Wire External IC).
  * *Color Order Dispatcher:* GRB, RGB, BGR, RBG, BRG, GBR. Auto-presets to GRB for WS2812B/13 and RGB for WS2815/11.
* **Dynamic 8-Channel Parallel Output Bus:**
  * Add 1 to 8 hardware parallel output lines.
  * Assign dedicated GPIO pins and custom strip lengths per channel.
  * **⚖️ Auto-Split Lengths Button:** Automatically balances total matrix LEDs evenly across all active channels.
* **Digital Audio Microphone Interface:**
  * *Profile 1 — Standard I2S (INMP441 / Prototype):* WS: 15, SD: 32, SCK: 14.
  * *Profile 2 — Commercial Controller Unit:* WS: 5, SD: 26, SCK: 21.
  * *Custom Definition:* Manually assign any safe ESP32 GPIO.
* **Mains Power Relay:** Configurable GPIO pin (Default GPIO 18) and 3-state control mode (Disabled, Active HIGH 3.3V, Active LOW 0V ground trigger).
* **IR Remote Receiver:** Configurable sensor pin (Default GPIO 33) and enable/disable toggle.

### Tab 3: 🚀 Startup Intro & Typography
* **Typography:** Select between Standard (5×7 Font) for 64/128 columns or Compact (3×5 Micro Font) for 16/32 columns.
* **Custom Greeting Messages:** Line 1 (Top) and Line 2 (Bottom) text fields (up to 32 characters each).
* **Text Scroll Mode:** Scroll Left, Scroll Right, Scroll Up, Scroll Down, or Static Centered.
* **Intro Animation Effects (7 Styles):** *Circular Radial Bloom, Matrix Digital Rain, Dual Laser Sweep, Hyperspace Warp Jump, Plasma Spiral Vortex, Diamond Prism Shutter, Firework Mortar Explosion.*
* **Toggles & Timers:** Text inverted flip, text enable, visual animation enable, center pause enable, pause duration (1–5s), text speed, and animation speed.
* **Preview Intro Now:** Triggers the opening startup sequence live on the matrix without rebooting.

### Tab 4: 💾 Backup & Storage (`cfgBackup`)
* **General Settings Flash Storage:** Prominent **`💾 Save General Settings to Flash`** button that permanently commits live visualizer adjustments (sensitivity, noise gate, bleed, active pattern, theme, speeds, timers, and auto-cycle preferences) to NVS flash memory immediately without restarting.
* **Appliance Configuration Backup (.json):**
  * **💾 Export Backup (.json):** Downloads a clean `spectrum_general_config.json` backup containing all live visualizer parameters, display options, and auto-cycle states.
  * **📁 Import Backup (.json):** Transmits an atomic configuration payload directly to the microcontroller in RAM without toggle inversions or side-effect cancellations.
* **Factory Defaults Reset:** The red **`🔴 Reset All to Factory Defaults`** button restores all general spectrum parameters, timers, and auto-cycle settings to factory defaults.

### Context-Aware Reboot Button (`#cfgRebootBtn`)
* The **`💾 Save Configuration & Reboot`** button is displayed strictly on tabs that alter physical hardware (*Wi-Fi & Device* and *Matrix & Hardware*), and is automatically hidden on *Startup Intro* and *Backup & Storage*.
* **Guaranteed Pin Persistence:** Commits all modified hardware variables directly to global RAM before NVS commit, ensuring `relayPin`, `rMode`, mic pins, IR pin, orientation, and bus routing never revert to old defaults on restart.

---

## 10. Appliance Telemetry, Live Diagnostics & Hardware Inspector

Accessible via the top bar **`ℹ️ Info`** button, this centered drawer provides complete real-time diagnostics:
