# 📖 Audio Spectrum Visualizer — Complete Web Dashboard Guide

Welcome to the comprehensive user manual for the **Professional Audio Spectrum Visualizer & Commercial Equalizer Display Appliance** web dashboard. This guide details the purpose, operation, and best practices for every button, slider, performance column, modal drawer, and configuration menu available in the system.

---

## 📑 Table of Contents
1. [Global Header & Navigation Bar](#1-global-header--navigation-bar)
2. [Studio Console Layout & Operating Modes (Desktop vs. Mobile View)](#2-studio-console-layout--operating-modes)
3. [Column 1: 🎨 Color Themes & Flow Dynamics](#3-column-1--color-themes--flow-dynamics)
4. [Column 2: ✨ Visual Effects & Kinetic Engines](#4-column-2--visual-effects--kinetic-engines)
5. [Column 3: 🌌 Backdrop, Peak Dots & Live Acoustics](#5-column-3--backdrop-peak-dots--live-acoustics)
6. [🎛️ Equalizer Studio & Frequency Tuner (`/eq`)](#6-equalizer-studio--frequency-tuner)
7. [🎬 Master Show Playlist Sequencer](#7-master-show-playlist-sequencer)
8. [⚙️ Configuration Hub & Safe Storage Management](#8-configuration-hub--safe-storage-management)
9. [ℹ️ Appliance Telemetry, Hardware Specs & OTA Updates](#9-appliance-telemetry-hardware-specs--ota-updates)
10. [💡 Quick Tips, Best Practices & Acoustic Setup](#10-quick-tips-best-practices--acoustic-setup)

---

## 1. Global Header & Navigation Bar

Located at the very top of the interface, the header provides instant access to master system controls, live telemetry, and brightness adjustments across all devices.

```
┌────────────────────────────────────────────────────────────────────────────────────────┐
│ [⏻]  [🌙 Sleep] [🎛️ EQ] [🎬 Show] [🎯 Calib] [⚙️ Config] [ℹ️ Info] [🖥️ PC]   [💾 Save] [☀️ ────] │
└────────────────────────────────────────────────────────────────────────────────────────┘
```

* **⏻ Master Power Button:** An enlarged circular power toggle. Automatically illuminates in glowing emerald green when the visualizer is active and crimson when in standby. Toggling power instantly blanks all LED pixels, pauses animation physics, and de-energizes the hardware mains relay to cut AC power to external power supplies.
* **🌙 Sleep / Standby:** Opens the **Auto-Standby & Silence Detection** drawer to configure automatic sleep timers or manually toggle display sleep.
* **🎛️ Equalizer Studio:** (Visible on desktop monitors) Opens the wide 1100px **Graphic Equalizer Studio** for 16, 32, and 64-band frequency tuning.
* **🎬 Master Show:** Opens the automated **Showcase Playlist Sequencer** capable of scheduling up to 50 automated scenes.
* **🎯 Calib (Noise Floor Calibration):** Instantly captures a 32-frame digital acoustic sample of your room's ambient background noise (HVAC hum, computer fans, street noise) and sets calibrated cutoff thresholds across every individual frequency band. Run this while the room is quiet to keep bars flat during silence.
* **⚙️ Config (Configuration Hub):** Opens the 4-tab hardware management hub (*Wi-Fi & Device*, *Matrix & Hardware*, *Startup Intro*, and *Backup & Storage*).
* **ℹ️ Info (Appliance Telemetry):** Displays hardware architecture, active grid status, firmware version, and contiguous free memory, along with a link to the browser-based wireless firmware flasher.
* **🖥️ PC Mode / 📱 Phone View Toggle:** (Visible on desktop screens) Switches the browser interface between **Multi-Column Desktop Mode** (3 columns side-by-side) and **Simulated Mobile Phone View** (single centered column with an active bottom navigation dock).
* **💾 Save Config Button:** **Crucial action.** Live adjustments to sliders, themes, patterns, speeds, and auto-cycle timers modify parameters in high-speed RAM only (zero flash memory wear). Clicking this button permanently commits all current visualizer settings to non-volatile NVS flash memory so your setup persists across reboots and power cuts.
* **☀️ Master Matrix Brightness Slider (0–255):** Controls foreground equalizer bar and particle brightness. Features an extended 300px slider on desktop monitors for precise luminance adjustments, and a dedicated full-width control bar on mobile phones.
* **Status Ribbon:** Positioned directly below the top bar, displaying real-time feedback whenever sliders move, presets change, or memory operations complete.

---

## 2. Studio Console Layout & Operating Modes

The web dashboard is engineered to provide a true zero-scroll, high-speed appliance experience across both desktop computer monitors and smartphones.

```
┌───────────────────────────────┬───────────────────────────────┬───────────────────────────────┐
│ COLUMN 1: THEMES & FLOW       │ COLUMN 2: EFFECTS & KINETICS  │ COLUMN 3: BACKDROP & PEAKS    │
├───────────────────────────────┼───────────────────────────────┼───────────────────────────────┤
│ • Interactive Color Wheel     │ • Visual Patterns Pill-List   │ • Front Backdrop Brightness   │
│ • Staged Tri-Zone Swatches    │ • 3-Button Control Ribbon:    │ • Background Modes Pill-List  │
│ • Live Theme Gradient Ribbon  │   [Auto] [⚙️ Kinetics] [Rnd]  │ • Live Peak Dot Ribbon        │
│ • Color Themes Pill-List      │                               │ • Peak Dot Colors Pill-List   │
│ • 3-Button Control Ribbon:    │                               │ • 3-Button Control Ribbon:    │
│   [Auto] [⚙️ Flow] [Rnd]      │                               │   [Auto] [⚙️ Tuning] [Rnd]    │
└───────────────────────────────┴───────────────────────────────┴───────────────────────────────┘
```

### Desktop Multi-Column Mode (`🖥️ PC Mode`)
* Renders all 3 performance columns simultaneously side-by-side.
* Locked to 100% of the viewport height with adaptive flex-height lists—**zero outer page scrollbars**. All columns terminate at the exact same bottom pixel line.
* The mobile bottom navigation dock is automatically hidden to maximize screen workspace.

### Mobile Phone View Simulation (`📱 Phone View`)
* When activated on a desktop browser (or viewed on a smartphone), the console displays a **single centered active column** (480px max-width) and illuminates the **enlarged 60px bottom navigation dock**.
* Clicking the bottom navigation buttons (**🎨 Themes**, **✨ Effects**, **🌌 Backdrop**, and **🎛️ Equalizer**) smoothly switches the visible column without page reloads.

---

## 3. Column 1: 🎨 Color Themes & Flow Dynamics

Controls color palettes, staged multi-zone coloring, and directional color flow motion across the display.

### 1. Interactive Color Wheel & Center Pure White Hub
* **160px Chromatic Spectrum Ring:** Touch or drag anywhere along the 360° outer spectrum ring to immediately adjust the primary visualizer theme and automatically assign a randomized, contrasting peak dot color.
* **Illuminated Pure White Center Core (`WHITE`):** The center circle is an interactive touch target. Tapping the center core instantly sets the primary display bars to pure white (or sets a staged acoustic zone to crisp white).
* **Staged Tri-Zone Swatches:** Three circular swatches representing **Zone 1 (Bass/Lows)**, **Zone 2 (Mids/Vocals)**, and **Zone 3 (Highs/Treble)**.
  * *Staging Workflow:* Tap a zone circle to select it (indicated by a glowing white ring). Touch the wheel or center white core to stage color onto that circle.
  * **⚡ Apply Button:** Commits all three staged colors simultaneously to the visualizer as **Theme 119 (Custom Tri-Zone)**, assigns a contrasting peak color, and returns the wheel to direct effect control.
  * **✖ Cancel Button:** Deselects all zone circles without applying changes.

### 2. Live Theme Gradient Ribbon (`#themeGradientRibbon`)
* Positioned directly above the Color Themes list.
* Dynamically calculates and renders the multi-stop linear gradient matching the active theme in real time. Updates instantly during manual theme selection, auto-cycling playback, and initial page load.

### 3. Color Themes List (120 Total Options)
* **Search Filter:** Type keywords into the search box to instantly filter themes by name.
* **Pill-List Selection:** Features 120 curated color themes (Themes 0–119) divided into distinct stylistic families:
  * *Classic & Studio Equalizers* (Themes 0–15)
  * *Neon Cyber & Synthwave* (Themes 16–29)
  * *Studio Signature Specials* (Themes 30–34)
  * *Dynamic Flow Palettes* (Themes 35–54)
  * *Vibrant & Atmospheric* (Themes 55–69)
  * *Tri-Zone Frequency Splits (Part 1)* (Themes 70–80)
  * *Modern Luxury & Cyber Vibe* (Themes 81–95)
  * *Tri-Zone Frequency Splits (Part 2)* (Themes 96–104)
  * *Psychedelic, Double-Flow & Prismatic* (Themes 105–118)
  * *Custom Tri-Zone Live Palette* (Theme 119)
* **Control Ribbon:**
  * **Auto Themes:** Toggles automatic theme rotation ON or OFF.
  * **⚙️ Flow Settings:** Opens the dedicated `modalThemeControls` drawer.
  * **Order (Linear / Random):** Toggles theme auto-cycling between sequential progression and non-repeating hardware TRNG shuffle.

### 4. Dedicated Flow Settings Drawer (`modalThemeControls`)
* **Theme Cycle Time (3s–60s):** How long each color theme displays before advancing.
* **Flow Direction Picker (23 Directions):** Directional color motion:
  * *Orthogonal:* Up, Down, Left, Right (Directions 0–3).
  * *Diagonal:* 4-corner diagonal sweeps (Directions 4–7).
  * *Radials & Ripples:* Radial Bloom, Radial Implosion, Diamond Ripple, 4-Corner Radials (Directions 8–14).
  * *Harmonics & Beams:* Dual In-and-Out Wave Harmonics, Single Scanner Beam, Counter-Crossing Beams, Vortex Swirl Flow, Dual Cross-Collision, Quad-Wave Ripple Bloom, Triple Counter-Beams, and Sweeping Ceiling Spotlights (Directions 15–22).
* **Flow Speed (0–10):** Velocity of traveling color waves (`0` freezes palette movement).
* **Diagonal Angle (30°–60°):** Angular tilt of diagonal flow directions.
* **Flow Cycle Time (3s–60s):** Rotation interval when Auto Flow is engaged.
* **Auto Flow & Flow Order Buttons:** Toggles automated flow direction cycling and linear/random shuffling.

---

## 4. Column 2: ✨ Visual Effects & Kinetic Engines

Houses the visual pattern portfolio and kinetic particle generator controls.

### 1. Visual Patterns List (37 Advanced Patterns)
* **Search Filter:** Quickly filter through all 37 visual patterns.
* **Adaptive Pill-List:** Features patterns 0 to 36, including:
  * *Equalizer Bars:* Standard floor bars, inverted ceiling bars, center-out bars, inward-surging bars, scrolling wave bars, and negative-space silhouette cutouts.
  * *Floating Dots-Only:* Normal up, inverted down, center-out, and inward-surging peak dots with dedicated ballistic timing.
  * *Procedural Kinetics:* Sweeping volcanic magma cannons, ballistic popcorn cannons, bioluminescent floating bubbles, 4-way spectrogram waterfall streams, and multi-sine plasma aurora flame beds.
  * *Harmonic Sacred Geometry:* Resonant Cymatic kaleidoscopes, infinite hypnotic warp tunnels, Lissajous harmonograph laser ribbons, liquid silk harmonic waves, psychedelic fluid noise meshes, sacred lotus mandalas, resonant vector line networks, and orbital liquid silk vortexes.
* **Intelligent Negative-Space Fallback:** Automatically switches to an active theme flow canvas if a silhouette or dots-only pattern is selected while the background is set to pitch black, ensuring the matrix is always illuminated.
* **Control Ribbon:**
  * **Auto Effects:** Toggles automatic visual pattern rotation ON or OFF.
  * **⚙️ Effect Kinetics:** Opens the dedicated `modalEffectControls` drawer.
  * **Pattern (Linear / Random):** Toggles pattern cycling between sequential order and non-repeating hardware TRNG shuffle.

### 2. Dedicated Effect Kinetics Drawer (`modalEffectControls`)
* **Matrix Spoke & Column Geometry:**
  * *LEDs per Band (Column Width):* Sets physical bar width (1, 2, 3, or 4 LEDs per band), dynamically recalculating the audio DSP between **16, 32, and 64 bands** with automatic centering.
  * *Radial Pulse Spokes (Patterns 6 & 10):* Sets radial spoke resolution independently from bar width (1: 64 spokes, 2: 32 spokes, 3: 21 spokes, 4: 16 spokes).
  * *Effect Cycle Time (3s–60s):* Display duration for each pattern during auto-cycle playback.
* **Procedural & Harmonic Engine Sliders:**
  * *Sway Orbit Speed & Centers Count:* Governs orbital motion and 1–5 independent orbital centers for Pattern 10.
  * *Cymatics Rotation Speed (1–10):* Clockwise/counter-clockwise spin velocity for Chladni resonance patterns.
  * *Harmonograph Knots & Laser Speed:* Controls 1–5 roving figure-8 laser ribbon knots and travel rate.
  * *Sacred Mandalas Count & Speed:* Controls 1–5 multi-orbital mandalas roaming across the panel.
  * *Vector Hubs & Spoke Speed:* Configures 1–5 roaming geometric vector line laser hubs.
  * *Warp Tunnel Speed & Vortex Orbit Speed:* Sets progression velocity for tunnel zoom and vortex arms.
  * *Wave Scroll Speed & Direction:* Controls horizontal scroll rate and Left/Right direction for wave bars.
* **Particle & Flame Generator Sliders:**
  * *Spectrogram Waterfall Speed & Flow Direction:* Sets waterfall stream rate and 4-way direction (Left, Right, Down, Up).
  * *Floating Bubbles Speed, Size & Quantity:* Controls up to 40 bioluminescent orbs glowing to audio energy.
  * *Popcorn Cannon Count & Size:* Controls up to 80 gravity-simulated particles with 3 size options (Pinpoint 1×1, Mixed Variety, Large Fluffy 2×2).
  * *Plasma Flame Speed & Drift Direction:* Sets aurora flame ripple rate and horizontal drift direction.
  * *Volcano Sweep Speed, Caldera Count & Ember Size:* Configures 3, 6, 9, 12, or 18 sweeping calderas and up to 160 ballistic magma embers.

---

## 5. Column 3: 🌌 Backdrop, Peak Dots & Live Acoustics

Controls ambient background shaders, peak indicator styling, and live acoustic filters.

### 1. Front-Panel Backdrop Brightness Slider (1–50)
* Located directly beneath the Column 3 header on the main console for **instant single-touch access**.
* 100% mathematically decoupled from main matrix brightness—setting it to `1` produces a faint moonlight glow that never washes out foreground bars.

### 2. Universal Background Layer (147 Total Modes)
* **Background Gradient Ribbon (`#bgGradientRibbon`):** Real-time multi-stop CSS gradient previewing the active ambient shader or theme canvas.
* **Background Modes Pill-List (Modes 0 to 146):**
  * *Mode 0:* Pure Pitch Black (Clean Default).
  * *Modes 1–26 (Curated Ambient Shaders):* Active Theme Flow, Static Theme, Cyber Blue Aura, Synthwave Glow, Sunset Horizon, Starfield Sky, Ocean Abyss, Nebula Dust, Volume Pulse, Cyber Matrix Floor, Emerald Digital Rain, Molten Caldera, Electric Lavender, Harmonic Ripples, Knight Rider Scanners, Liquid Oil Slick, Archimedean Spiral, Caustic Shimmer, and Vector Grid.
  * *Modes 27–146 (Dedicated Theme Flow Canvases):* Selects any of the 120 color themes as an independent flowing background layer.
* **Auto-Background Pitch-Black Protection:** Firmware safeguards prevent Auto-Background from ever lingering on Mode 0 during auto-cycle playback.

### 3. Peak Dot Palette (120 Modes) & Real-Time Auto Match
* **Peak Dot Ribbon (`#peakGradientRibbon`):** Real-time preview of the applied peak dot color, alternating duo, tri-zone split, or chromatic sweep.
* **Live Mode Indicator Sub-Label (`#peakColorSubLabel`):** Dynamically displays the resolved color name in Auto mode (*e.g., `Auto Match: Electric Yellow (#2)`*) or the manual mode name.
* **Peak Colors Pill-List (Modes 0 to 119):** Complete 1-to-1 parity with the 120 color themes.
* **Control Buttons:**
  * **Auto Bgrn:** Toggles automatic background layer cycling.
  * **⚙️ Tuning & Peaks:** Opens the dedicated `modalAcousticControls` drawer.
  * **Order (Linear / Random):** Toggles background cycling between sequential order and non-repeating TRNG shuffle.
  * **Peak Dots (ON / OFF):** Globally enables or disables peak indicator dots.
  * **✓ Match Theme: ON Button:** Dedicated button that turns active emerald green when in Auto Match mode (Mode 0). Selecting any manual color ($1 \to 119$) turns the button dark; clicking it instantly re-engages dynamic auto-theme matching.

### 4. Dedicated Tuning & Peaks Drawer (`modalAcousticControls`)
* **Live Acoustic Sensitivity & Macro Filters:**
  * *Master Sensitivity (10–100):* Digital pre-amplifier gain. Increase for quiet rooms; decrease for loud audio to prevent clipping.
  * *Noise Gate Filter (0–100):* Scaled via a `* 50.0f` multiplier ($0 \to 5,000\text{ units}$) to completely reject background room hum and air conditioning noise while preserving musical dynamics.
  * *Band Bleed (Fill) (0%–100%):* Frequency smoothing between adjacent columns. Higher values create full, natural curves; lower values yield isolated, razor-sharp needle spikes.
  * *3-Band Macro Equalizer (0.20×–2.40×):* Instant gain adjustment across **Bass (Lows)**, **Mids (Vocals)**, and **Treble (Highs)**.
* **Background Layer Tuning:**
  * *Background Cycle Time (3s–60s):* Display interval for background modes.
  * *Music Active / Always On Toggle:* 
    * *Music Active (Default):* Background illuminates with audio transients and gently fades to pitch black when music stops.
    * *Always On:* Keeps the background lit continuously regardless of audio.
* **Peak Dot Ballistics & Timing:**
  * *Peak Dot Size (Thickness):* 1 LED Thin (pinpoint), 2 LEDs Medium (bold), or 3 LEDs Chunky (block).
  * *Peak Action:* Choose between standard **Falling Gravity Dots** or high-speed **Shooting Cannon Sparks**.
  * *Cannon Sparks Launch Speed (1–10):* Velocity of projectile spark launches.
  * *Bar Drop Speed (1–5):* Decay rate of main equalizer bars after hitting a peak.
  * *Standard Peak Hang Time (0–30 frames):* How long peak dots hover at maximum height before falling.
  * *Standard Peak Fall Delay (1–10):* Descent speed of standard peak dots.
  * *Dedicated Dots-Only Timers:* Independent hang time and fall delay sliders specifically for Dots-Only patterns (1, 2, 18, 19), allowing slow, floating constellation effects without affecting standard bar modes.

---

## 6. Equalizer Studio & Frequency Tuner (`/eq`)

Accessible via the top bar `🎛️ Equalizer` button or direct URL (`/eq`), this wide 1100px studio rack provides laboratory-grade acoustic tuning.

```
┌────────────────────────────────────────────────────────────────────────────────────────┐
│ [💾 Save to Flash]  [🎯 Calibrate]  [🟡 Revert]  [🔴 Reset]  │ Active: 32 Bands │ Saved: vocal_air │
├────────────────────────────────────────────────────────────────────────────────────────┤
│ 🎤 VOCAL PROFILES: [Vocal Clarity Pro] [Warm Acoustic] [Pop Lead] [Vocal Air & Breath] ... │
│ 🎵 GENRE PROFILES: [Club Deep Bass] [R&B/808s] [Rock Attack] [Lo-Fi Chill] [EDM Synth] ... │
├────────────────────────────────────────────────────────────────────────────────────────┤
│ ⭐ USER CUSTOM PRESETS: [⭐ Custom 1] [⭐ Custom 2] [☆ Custom 3] ... [💾 Save Slot] [Export] │
├────────────────────────────────────────────────────────────────────────────────────────┤
│ GRAPHICAL FREQUENCY SLIDERS: [1. bandEQ] [2. minBandCeilings] [3. bandCutoffs]         │
└────────────────────────────────────────────────────────────────────────────────────────┘
```

### 1. Action Bar & Telemetry
* **💾 Save to Flash:** Commits active EQ curves to band-specific NVS flash memory (`bEQ_<bands>`, `bCeil_<bands>`, `bCut_<bands>`).
* **🎯 Calibrate Noise Floor:** Analyzes room acoustics across 32 frames and sets individual noise floors per band.
* **🟡 Revert:** Restores live sliders to the last saved flash memory state.
* **🔴 Reset:** Restores the equalizer to the factory calibrated `"vocal_air"` profile.
* **Active Band Badge:** Displays whether the system is currently tuning 16, 32, or 64 bands.

### 2. Pre-Calibrated Acoustic Profiles (22 Presets)
* **11 Vocal & Speech Profiles:** *Vocal Clarity Pro, Warm Acoustic, Pop Diva Lead, Crisp Speech, Vocal Air & Breath (Factory Default), Punchy Rap, Female Lead, Baritone Male, Intimate Whisper, Broadcast Radio, De-Esser.*
* **11 Music & Genre Profiles:** *Video Match, Flat Sweep (1.0), Club Deep Bass, R&B / 808s, Rock & Metal, Lo-Fi Chill, Classical, EDM Synthwave, Fingerstyle, Sub Monster, Tube Warmth.*

### 3. ⭐ Band-Aware User Custom Presets (10 Slots per Band Tier)
* **Isolated Resolution Memory:** Stores 10 custom curves independently for 16-band, 32-band, and 64-band modes. Changing column width automatically loads that resolution's custom presets without cross-overwriting.
* **Editable Slot Names:** Select a slot (1–10), type a custom name (e.g. `"Acoustic Live"`), and click **💾 Save to Slot**. Active saved slots display a filled star (`⭐`), while empty slots show an outline (`☆`).
* **💾 Export Presets (.json):** Downloads all 10 custom presets for the active band count into `custom_presets_<bands>bands.json`.
* **📁 Import Presets (.json):** Restores saved presets directly into flash memory from a backup file.

### 4. Graphical Frequency Slider Matrix
* **Sub-Tab 1: Acoustic EQ Gains (`bandEQ`):** Individual gain sliders ($0.2\times\text{ to }3.0\times$) per band with live frequency span readouts (e.g., `24-48Hz`) and color-coded acoustic zones (**Red = Lows**, **Yellow = Mids**, **Cyan = Highs**).
* **Sub-Tab 2: Dynamic Ceilings (`minBandCeilings`):** Sets dynamic range ceilings ($2\text{k to }28\text{k}$) per band to balance quiet and loud frequencies.
* **Sub-Tab 3: Frequency Cutoffs (`bandCutoffs`):** Adjusts FFT bin boundaries separating each band. All cutoffs are strictly increasing and capped at **Bin 216 ($5,062.5\text{ Hz}$)** for energetic balance across all band counts. Real-time dragging uses throttled updates without DOM rebuilding, preserving pointer capture.

---

## 7. Master Show Playlist Sequencer

Accessible via the top bar `🎬 Show` button, the 1100px wide sequencer automates multi-scene presentations for commercial displays and stage setups.

* **Master Show Toggle (ON / OFF):** Starts or stops automated playlist cycling.
* **▶️ Resume Show:** Appears when the show is temporarily paused due to manual slider interaction, allowing one-click return to the playlist.
* **Boot: Show Toggle (ON / OFF):** Automatically launches Master Show playback immediately upon power-on.
* **Playlist Length Slider (1–50 Scenes):** Expands or shrinks the active scene count (factory preloaded with 10 showcase scenes).
* **Context-Aware Scene Cards:**
  * **Header:** Displays Scene number, live status tag (`▶️ Playing` / `⏸️ Paused`), **▶️ Test** (instantly previews this scene live on the matrix), and **🗑️ Delete**.
  * **Pattern / Effect:** Selects any of the 37 patterns or choose `⚡ Auto Cycle Patterns` (`255`).
  * **Color Theme:** Selects any of the 120 themes or choose `⚡ Auto Cycle Themes` (`255`).
  * **Background Layer:** Selects any of the 147 backgrounds or choose `⚡ Auto Cycle Backgrounds` (`255`).
  * **Adaptive Extra Controls:** Dynamically adapts based on pattern (Bar Width, Peak Dot behavior/color/size, Wave Scroll speed/direction, Radial Spoke resolution, Procedural engine speeds, Bubble/Popcorn/Volcano quantities and sizes).
  * **Duration (3s–180s):** How long the scene runs before advancing to the next.
* **➕ Add New Scene:** Appends a new scene card (up to 50 scenes).
* **💾 Save Show to Flash & 🔴 Restore Defaults:** Commits custom playlists to NVS flash or restores the factory curated 10-scene showcase.

---

## 8. Configuration Hub & Safe Storage Management

Accessible via the top bar `⚙️ Config` button, the hub organizes hardware setup, network credentials, startup typography, and flash backup into 4 sub-menus. Sub-menu tabs are anchored as a **fixed, pinned sub-header** that never scrolls away.

```
┌────────────────────────────────────────────────────────────────────────────────────────┐
│ [📶 Wi-Fi & Device]    [📐 Matrix & Hardware]    [🚀 Startup Intro]    [💾 Backup & Storage]   │
└────────────────────────────────────────────────────────────────────────────────────────┘
```

### Tab 1: 📶 Wi-Fi & Device
* **Connection Mode:** Access Point Only (`ESP32_VU_METER`) or Connect to Home Wi-Fi (AP + Station mode).
* **Home Wi-Fi Credentials:** Network SSID and Password fields.
* **Network Status:** Displays the local IP address assigned by your home router.
* **Hardware Identity & Activation:** Displays the permanent factory silicon MAC address with a **📋 Copy** button, license activation status, and cryptographic activation key input box.

### Tab 2: 📐 Matrix & Hardware
* **Matrix Geometry:** Physical Columns (16, 32, 64, or 128) and Row Height (8 to 64 rows). Displays live total LED count.
* **Smart 5V Power Limiter:** Sets maximum current budget from **500 mA (0.5A)** up to **20,000 mA (20A)** in 250 mA increments to protect USB ports and power supplies.
* **Parallel LED Output Channels:** Selects 1 Pin (Serial stream), 2 Pins (Split left/right, 2× FPS), or 4 Pins (4 quadrants, 4× FPS). Configurable data pins (`ledPin1` to `ledPin4`).
* **Digital Audio Microphone Interface:**
  * *Profile 1 — Standard I2S (INMP441 / Prototype):* WS: 15, SD: 32, SCK: 14.
  * *Profile 2 — Commercial Controller Unit:* WS: 5, SD: 26, SCK: 21.
  * *Custom Definition:* Manually assign any safe ESP32 GPIO.
* **Mains Power Relay:** Configurable active-HIGH GPIO pin (Default GPIO 18) and enable toggle. Automatically cuts AC power to LED power supplies in standby.
* **IR Remote Receiver:** Configurable sensor pin (Default GPIO 33) and enable/disable toggle to bypass ISR overhead when unused.

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
  * **💾 Export Backup (.json):** Downloads a clean `spectrum_general_config.json` backup containing all live visualizer parameters, display options, and auto-cycle states. *(Equalizer profiles and Master Show playlists are maintained in their respective studios).*
  * **📁 Import Backup (.json):** Transmits an atomic configuration payload directly to the microcontroller in RAM without toggle inversions or side-effect cancellations.
* **Factory Defaults Reset:** The red **`🔴 Reset All to Factory Defaults`** button restores all general spectrum parameters, timers, and auto-cycle settings to factory defaults.

### Context-Aware Reboot Button (`#cfgRebootBtn`)
* The **`💾 Save Configuration & Reboot`** button is displayed strictly on tabs that alter physical hardware (*Wi-Fi & Device* and *Matrix & Hardware*), and is automatically hidden on *Startup Intro* and *Backup & Storage* to eliminate confusion.

---

## 9. Appliance Telemetry, Hardware Specs & OTA Updates

Accessible via the top bar `ℹ️ Info` button, the 560px wide centered drawer displays hardware specifications and firmware management:

* **Firmware Version:** Displays active release build (e.g. `ver. 1.1`).
* **Active Matrix Grid:** Confirms physical dimensions, channel configuration, active band count, and column width.
* **Processor Architecture:** Confirms hardware execution: `Dual-Core 32-Bit High-Performance Processor (240 MHz)`.
* **Flash Storage:** `1.9MB Flash Memory (Wireless OTA Active)`.
* **Dynamic Runtime Memory:** Displays contiguous free heap headroom ($\sim175\text{KB}$).
* **mDNS Network Address:** Direct network link at `http://vumeter.local`.
* **OTA Update Button:** Standardized console button providing immediate access to `/update` for flashing pre-compiled firmware binaries wirelessly through your web browser.

---

## 10. Quick Tips, Best Practices & Acoustic Setup

1. **Commit Your Look to Flash:** When exploring patterns, themes, or speeds, changes preview instantly in high-speed RAM. Once you find a look you love, click **💾 Save Config** on the top action bar (or **💾 Save General Settings to Flash** under Settings) so it persists across power cycles.
2. **Room Acoustic Calibration:** If equalizer bars bounce when the room is silent, click **🎯 Calib** while the room is quiet to automatically map ambient room noise floors across all bands. Alternatively, open **Column 3 $\to$ ⚙️ Tuning & Peaks** and raise the **Noise Gate Filter** slightly.
3. **USB Power Safety:** When powering your display from a computer USB port or phone charger, open **⚙️ Config $\to$ 📐 Matrix & Hardware** and set the **Max 5V Current** to **1000 mA (1.0A)** or lower to prevent power supply brownouts.
4. **Instant Standby & Relay Sleep:** Press the power button on an IR remote or click the circular **⏻** power button in the web header to enter standby. The display blanks instantly, and the hardware relay cuts mains power to eliminate coil whine and idle energy consumption.
5. **Simulated Mobile View on Desktop:** If you are operating the visualizer from a laptop or desktop monitor and prefer the compact single-column app layout with the bottom navigation dock, click **🖥️ PC Mode** in the top bar to switch into **📱 Phone View**.

---
