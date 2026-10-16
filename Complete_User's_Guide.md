# 📖 Audio Spectrum Visualizer & Commercial Equalizer Appliance — Complete Web Dashboard Guide

Welcome to the comprehensive user manual for the **Professional Audio Spectrum Visualizer & Commercial Equalizer Display Appliance** web dashboard. This guide details the purpose, operation, electrical safeguards, and best practices for every button, slider, performance column, modal drawer, configuration menu, and diagnostic utility built into the system.

---

## 📑 Table of Contents
1. [Global Header & Navigation Bar](#1-global-header--navigation-bar)
2. [Studio Console Layout & Operating Modes (Desktop vs. Mobile View)](#2-studio-console-layout--operating-modes)
3. [Column 1: 🎨 Color Themes & Flow Dynamics](#3-column-1-color-themes--flow-dynamics)
4. [Column 2: ✨ Visual Effects & Kinetic Engines](#4-column-2-visual-effects--kinetic-engines)
5. [Column 3: 🌌 Backdrop, Peak Dots & Live Acoustics](#5-column-3-backdrop-peak-dots--live-acoustics)
6. [🛋️ Ambient Relaxation Lamp Mode Deep Dive](#6-ambient-relaxation-lamp-mode-deep-dive)
7. [🎛️ Equalizer Studio & Frequency Tuner (`/eq`)](#7-equalizer-studio--frequency-tuner)
8. [🎬 Master Show Playlist Sequencer](#8-master-show-playlist-sequencer)
9. [⚙️ Configuration Hub & Safe Storage Management](#9-configuration-hub--safe-storage-management)
10. [ℹ️ Appliance Telemetry, Live Diagnostics & Hardware Inspector](#10-appliance-telemetry-live-diagnostics--hardware-inspector)
11. [📘 Hardware Wiring, Cluster Topology & Relay Guide](#11-hardware-wiring-cluster-topology--relay-guide)
12. [💡 Quick Tips, Best Practices & Acoustic Setup](#12-quick-tips-best-practices--acoustic-setup)

---

## 1. Global Header & Navigation Bar

Located at the very top of the interface, the header provides instant access to master system controls, operating modes, live telemetry, and brightness adjustments across all devices.

```
┌────────────────────────────────────────────────────────────────────────────────────────────────────────┐
│ [⏻] [🛋️ Lamp] [🌙 Sleep] [🎛️ EQ] [🎬 Show] [🎯 Calib] [⚙️ Config] [ℹ️ Info] [🖥️ PC]   [💾 Save] [☀️ ────] │
└────────────────────────────────────────────────────────────────────────────────────────────────────────┘
```

* **⏻ Master Power Button:** An enlarged circular power toggle. Automatically illuminates in glowing emerald green when the visualizer is active and crimson when in standby. Toggling power instantly blanks all LED pixels, pauses animation physics, and de-energizes the hardware mains power relay to physically cut AC mains power to external LED supplies.
* **🛋️ Lamp Mode Toggle (`#lampModeBtn`):** Instantly switches the appliance between **Audio Spectrum Visualizer Mode** and **Ambient Relaxation Lamp Mode**. When engaged, the digital audio stream is muted, equalizer bars and peak dots are hidden, and silence gating is bypassed so the selected ambient shader illuminates the full panel continuously as an atmospheric room lamp. Includes automatic background memory that restores your previous auto-background settings upon returning to spectrum mode.
* **🌙 Sleep / Standby:** Opens the **Auto-Standby & Silence Detection** drawer to configure automatic silence timeout sleep timers (1–30 minutes) or manually toggle display sleep.
* **🎛️ Equalizer Studio:** (Visible on desktop monitors) Opens the wide 1100px **Graphic Equalizer Studio** for laboratory-grade 16, 32, and 64-band frequency tuning and custom preset management.
* **🎬 Master Show:** Opens the automated **Showcase Playlist Sequencer** capable of scheduling up to 50 automated scenes with custom durations and parameters.
* **🎯 Calib (Noise Floor Calibration):** Captures a 32-frame digital acoustic sample of your room's ambient background noise (HVAC hum, computer fans, street noise) after a settling warm-up flush, setting calibrated cutoff thresholds across every individual frequency band. Run this while the room is quiet to keep bars completely flat during silence.
* **⚙️ Config (Configuration Hub):** Opens the 4-tab hardware management hub (*Wi-Fi & Device*, *Matrix & Hardware*, *Startup Intro*, and *Backup & Storage*).
* **ℹ️ Info (Appliance Telemetry & Specs):** Displays live system diagnostics: Hardware MAC ID, SoftAP Gateway, Station Network IP, Wi-Fi Signal Strength (RSSI), Appliance Uptime, firmware version, memory headroom, the Hardware GPIO Conflict Inspector, wireless OTA updates, and a dedicated **Restart Appliance** button.
* **🖥️ PC Mode / 📱 Phone View Toggle:** (Visible on desktop screens) Switches the browser interface between **Multi-Column Desktop Mode** (3 columns side-by-side) and **Simulated Mobile Phone View** (single centered column with an active 60px bottom navigation dock).
* **💾 Save Config Button:** **Crucial action.** Live adjustments to sliders, themes, patterns, speeds, and auto-cycle timers modify parameters in high-speed RAM only (preventing flash memory wear). Clicking this button permanently commits all current visualizer settings to non-volatile NVS flash memory so your setup persists across reboots and power cuts.
* **☀️ Master Matrix Brightness Slider (0–255):** Controls foreground equalizer bar and particle brightness. Features an extended 300px slider on desktop monitors for precise luminance adjustments, and a dedicated full-width control bar on mobile phones.
* **Status Ribbon:** Positioned directly below the top bar, displaying real-time feedback whenever sliders move, presets change, or memory operations complete.

---

## 2. Studio Console Layout & Operating Modes

The web dashboard is engineered to provide a true zero-scroll, high-speed appliance experience across desktop computer monitors, tablets, and smartphones.

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
* Locked to 100% of the viewport height (`100vh` / `100dvh`) with adaptive flex-height lists—**zero outer page scrollbars**. All columns terminate at the exact same bottom line.
* The mobile bottom navigation dock is automatically hidden to maximize screen workspace.

### Mobile Phone View Simulation (`📱 Phone View`)
* When activated on a desktop browser (or viewed natively on a smartphone), the console displays a **single centered active column** (480px max-width) and illuminates the **enlarged 60px bottom navigation dock**.
* Clicking the bottom navigation buttons (**🎨 Themes**, **✨ Effects**, **🌌 Backdrop**, and **🎛️ Equalizer**) smoothly switches the visible column without page reloads.

---

## 3. Column 1: Color Themes & Flow Dynamics

Controls color palettes, staged multi-zone coloring, and directional color flow motion across the display.

### 1. Interactive Color Wheel & Center Pure White Hub
* **160px Chromatic Spectrum Ring:** Touch or drag anywhere along the 360° outer spectrum ring to immediately adjust the primary visualizer theme and automatically assign a contrasting peak dot color.
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
* **Deselect on Auto-OFF & Zero Scroll Snapping:** Turning Auto Themes OFF immediately deselects the theme list (`selectedIndex = -1`). While browsing themes manually, background telemetry from other active cycles will **never** snap, reset, or hijack your scroll position. Tapping any theme locks your selection.

### 4. Flow Directions (24 Directions: 0 to 23)
* **Direction 0: Static / Stationary (No Flow Motion):** Freezes flow coordinates at timer zero, producing a motionless, fixed gradient across any color theme.
* **Directions 1 to 23 (Active Dynamic Flows):**
  * *Orthogonal (1–4):* Bottom to Top (1), Top to Bottom (2), Left to Right (3), Right to Left (4).
  * *Diagonal (5–8):* Diagonal Up-Right [/] (5), Diagonal Down-Right [\\] (6 - Default), Diagonal Up-Left [\\] (7), Diagonal Down-Left [/] (8).
  * *Radials & Ripples (9–15):* Radial Bloom (9), Radial Implosion (10), Diamond Ripple (11), Top-Left Radial (12), Top-Right Radial (13), Bottom-Left Radial (14), Bottom-Right Radial (15).
  * *Harmonics & Beams (16–23):* Dual In-and-Out Wave Harmonics (16), Single Kinetic Scanner Beam (17), Double Counter-Crossing Beams (18), Vortex Swirl Flow (19), Dual Cross-Collision (20), Quad-Wave Ripple Flow (21), Triple Counter-Beams (22), Sweeping Ceiling Spotlights (23).
* **Auto Flow Behavior:** 
  * Toggling Auto Flow **OFF** immediately engages **Direction 0 (Static / Stationary)**.
  * Toggling Auto Flow **ON** automatically advances into dynamic moving flows (1 to 23).
  * The dedicated Flow Shuffle Deck (`flowDeck[23]`) shuffles directions 1 to 23, reserving Static 0 for manual selection.

---

## 4. Column 2: Visual Effects & Kinetic Engines

Houses the visual pattern portfolio and kinetic particle generator controls.

### 1. Visual Patterns List (37 Advanced Patterns: 0 to 36)
* **Search Filter:** Quickly filter through all 37 visual patterns.
* **Adaptive Pill-List:** Features patterns 0 to 36, including:
  * *Equalizer Bars:* Standard floor bars (0), inverted ceiling bars (5), center-out bars (3), edge-to-center bars (4), scrolling wave bars (16, 17), and negative-space silhouette cutouts (20, 21, 23, 24).
  * *Floating Dots-Only:* Normal up (1), inverted down (2), center-out (18), and inward-surging (19) peak dots with dedicated ballistic timing.
  * *Procedural Kinetics:* Sweeping volcanic magma cannons (22), ballistic popcorn cannons (13), bioluminescent floating bubbles (12), 4-way spectrogram waterfall streams (11), and multi-sine plasma aurora flame beds (14, 15, 25, 26).
  * *Harmonic Sacred Geometry:* Resonant Cymatic kaleidoscopes (27), infinite hypnotic warp tunnels (28), Lissajous harmonograph laser ribbons (29), liquid silk harmonic waves (30), psychedelic fluid noise meshes (31), sacred lotus mandalas (32), resonant vector line networks (33), orbital liquid silk vortexes (34), orbital warp tunnels (35), and orbital resonant cymatics (36).
* **Intelligent Negative-Space Fallback:** Automatically renders Mode 1 (*Active Theme Flow Canvas*) if a silhouette (20, 21, 23, 24) or dots-only pattern (1, 2, 18, 19) is selected while the background is set to pitch black, ensuring the matrix is never unilluminated.
* **Deselect on Auto-OFF:** Toggling Auto Effects OFF immediately deselects the pattern list, allowing you to scroll and browse without telemetry resets.
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
  * *Cymatics Rotation Speed (1–10):* Spin velocity for Chladni resonance patterns.
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

## 5. Column 3: Backdrop, Peak Dots & Live Acoustics

Controls ambient background shaders, peak indicator styling, and live acoustic filters.

### 1. Front-Panel Backdrop Brightness Slider (1–50)
* Located directly beneath the Column 3 header on the main console for **instant single-touch access**.
* 100% mathematically decoupled from main matrix brightness—setting it to `1` produces a faint moonlight glow that never washes out foreground bars, even when main brightness is adjusted.

### 2. Universal Background Layer (154 Total Modes: 0 to 153)
* **Background Gradient Ribbon (`#bgGradientRibbon`):** Real-time multi-stop CSS gradient previewing the active ambient shader or theme canvas.
* **Background Modes Pill-List (Modes 0 to 153):**
  * *Mode 0:* Pure Pitch Black (Clean Default).
  * *Modes 1–26 (Curated Ambient Shaders):* Active Theme Flow, Static Theme, Cyber Blue Aura, Synthwave Glow, Sunset Horizon, Starfield Sky, Ocean Abyss, Nebula Dust, Volume Pulse, Cyber Matrix Floor, Emerald Digital Rain, Molten Caldera, Electric Lavender, Harmonic Ripples, Knight Rider Scanners, Liquid Oil Slick, Archimedean Spiral, Caustic Shimmer, and Vector Grid.
  * *Modes 27–33 (New Procedural Ambient Relaxation Shaders):*
    * **Mode 27: Convective Thermal Fire & Embers Bed:** High-speed convective draft (`nowMs/5`) with roaring flames reaching **75% to 85% of total matrix height**, glowing floor embers, and zero floating-point `powf` latency.
    * **Mode 28: Drifting Winter Blizzard & Snow:** Dual-layer falling snowflake particle simulation with gentle wind sway and floor frost accumulation.
    * **Mode 29: Bioluminescent Firefly Swarm:** Lively harmonic wander paths with $3\times$ faster biological flight and direct Gaussian radial glow stamping (zero inner-loop CPU cost).
    * **Mode 30: Concentric Water Droplets & Ripples:** Expanding caustics wave propagation with pre-calculated droplet centers.
    * **Mode 31: Horizontal Prismatic Aurora Waves:** Continuous non-wrapping wave undulation.
    * **Mode 32: Organic Bioluminescent Slime / Mold Flow:** Continuous 16-bit noise drift with pre-calculated trigonometric wobble uniforms.
    * **Mode 33: Neon Cyber Lava Fluid Flow:** High-speed liquid wax convection, molten hot-magenta body, electric-cyan rims, and radiant amber thermal core.
  * *Modes 34–153 (Dedicated Theme Flow Canvases):* Selects any of the 120 color themes as an independent flowing background layer ($34 + \text{themeIndex}$).
* **Complete 153-Mode Non-Repeating Shuffle Deck (`bgDeck[153]`):**
  * Shuffles **all 153 illuminated background modes** (Modes 1 to 153) using ESP32 hardware silicon entropy (`esp_random()`).
  * **Every single background in the entire catalog displays once before any can repeat.**
  * Mode 0 (Pure Pitch Black) is strictly excluded so the display never goes dark in auto mode.
  * Anti-clash swap ensures the first background of a new cycle never duplicates the last background of the previous cycle.
  * Linear mode smoothly steps through `1 → 2 → ... → 153 → 1`.
* **Deselect on Auto-OFF:** Toggling Auto Background OFF immediately deselects the background list, allowing you to scroll through all 154 options without telemetry scroll-snapping.

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
  * *Noise Gate Filter (0–100):* Scaled via a `* 50.0f` multiplier ($0 \to 5,000\text{ units}$) to completely reject background room hum and air conditioning noise while preserving musical dynamics. Default is `6` (300 units).
  * *Band Bleed (Fill) (0%–100%):* Frequency smoothing between adjacent columns. Higher values create full, natural curves; lower values yield isolated, razor-sharp needle spikes. Default is `40%`.
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
  * *Dedicated Dots-Only Timers:* Independent hang time (0–30) and fall delay (1–10) sliders specifically for Dots-Only patterns (1, 2, 18, 19), allowing slow, floating constellation effects without affecting standard bar modes.

---

## 6. Ambient Relaxation Lamp Mode Deep Dive

Engaged via the top bar **`🛋️ Lamp`** button, command `'%'`, or JSON `"toggle_lamp"`.

```
┌────────────────────────────────────────────────────────────────────────────────────────┐
│                        AMBIENT RELAXATION LAMP MODE (🛋️)                               │
├────────────────────────────────────────────────────────────────────────────────────────┤
│ • Digital MEMS Audio Stream Muted & Bypassed                                           │
│ • Equalizer Bars, Peak Dots, and Projectile Sparks Suppressed                          │
│ • Acoustic Silence Gating Bypassed (Full-Panel Continuous Illumination)                │
│ • 7 Procedural Relaxation Shaders: Fire, Snow, Fireflies, Caustics, Aurora, Slime, Lava │
│ • 120 Flowing Theme Canvases Available as Relaxation Light                             │
│ • Auto-Background Memory (Restores Spectrum Setup upon Exiting)                        │
└────────────────────────────────────────────────────────────────────────────────────────┘
```

### Purpose & Experience:
When you are not playing music, Ambient Relaxation Lamp Mode transforms your visualizer into a luxury studio mood lamp. Instead of remaining dark during silence, your addressable LED matrix displays soothing procedural light scenes—ideal for bedroom nightlights, studio backdrops, and relaxation spaces.

### Architectural Features:
1. **Zero Noise Sensitivity:** The I2S audio stream is muted and audio reactivity is disabled. Talking, TV dialogue, or footsteps will never trigger bar spikes.
2. **Silence Gating Bypass:** Standard spectrum backgrounds fade to black when audio stops. Lamp Mode completely bypasses this check, keeping shaders illuminated 100% of the time.
3. **Pitch-Black Protection:** If the background was set to Mode 0 (Pure Black) prior to activating Lamp Mode, the firmware automatically elevates to Mode 1 (or your selected relaxation shader) so the lamp never turns on into darkness.
4. **Auto-Background Memory:** Entering Lamp Mode saves your previous `autoChangeBg` state. When you exit Lamp Mode, your previous visualizer background preferences are automatically restored.

---

<a id="7-equalizer-studio--frequency-tuner"></a>
## 7. Equalizer Studio & Frequency Tuner

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

## 8. Master Show Playlist Sequencer

Accessible via the top bar `🎬 Show` button, the 1100px wide sequencer automates multi-scene presentations for commercial displays and stage setups.

* **Master Show Toggle (ON / OFF):** Starts or stops automated playlist cycling.
* **▶️ Resume Show:** Appears when the show is temporarily paused due to manual slider interaction, allowing one-click return to the playlist.
* **Boot: Show Toggle (ON / OFF):** Automatically launches Master Show playback immediately upon power-on (`showB`).
* **Playlist Length Slider (1–50 Scenes):** Expands or shrinks the active scene count (factory preloaded with 10 showcase scenes).
* **Context-Aware Scene Cards:**
  * **Header:** Displays Scene number, live status tag (`▶️ Playing` / `⏸️ Paused`), **▶️ Test** (instantly previews this scene live on the matrix), and **🗑️ Delete**.
  * **Pattern / Effect:** Selects any of the 37 patterns or choose `⚡ Auto Cycle Patterns` (`255`).
  * **Color Theme:** Selects any of the 120 themes or choose `⚡ Auto Cycle Themes` (`255`).
  * **Background Layer:** Selects any of the 154 backgrounds (0 to 153) or choose `⚡ Auto Cycle Backgrounds` (`255`).
  * **Flow Direction:** Selects any of the 24 flow directions (0 to 23), including Direction 0 (Static).
  * **Adaptive Extra Controls:** Dynamically adapts based on pattern (Bar Width, Peak Dot behavior/color/size, Wave Scroll speed/direction, Radial Spoke resolution, Procedural engine speeds, Bubble/Popcorn/Volcano quantities and sizes).
  * **Duration (3s–180s):** How long the scene runs before advancing to the next.
* **➕ Add New Scene:** Appends a new scene card (up to 50 scenes).
* **💾 Save Show to Flash & 🔴 Restore Defaults:** Commits custom playlists to NVS flash or restores the factory curated 10-scene showcase.

---

## 9. Configuration Hub & Safe Storage Management

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

```
┌────────────────────────────────────────────────────────────────────────────────────────┐
│                        ℹ️ APPLIANCE TELEMETRY & HARDWARE SPECS                         │
├────────────────────────────────────────────────────────────────────────────────────────┤
│ Firmware Version:     ver. 1.2                                                         │
│ Active Matrix Grid:   64×24 Grid (1-Ch Bus) • 64 Bands • 1 LED/Band                    │
│ Processor:            Dual-Core 32-Bit High-Performance Processor (240 MHz)           │
│ Flash Storage:        1.9MB Flash Memory (Wireless OTA Active)                         │
│ Dynamic Memory:       ~175KB Contiguous Free RAM                                       │
│ mDNS Address:         http://vumeter.local                                             │
│ Hardware MAC ID:      E0:72:A1:D5:27:B8                                                │
│ SoftAP Address:       192.168.4.1                                                      │
│ Station Network IP:   192.168.1.75                                                     │
│ Wi-Fi Signal (RSSI):  -64 dBm (Strong)                                                 │
│ Appliance Uptime:     135m 58s (or 2h 15m 58s)                                         │
│                                                                                        │
│                [OTA Update (/update)]      [🔄 Restart Appliance]                     │
├────────────────────────────────────────────────────────────────────────────────────────┤
│ HARDWARE GPIO AVAILABILITY & CONFLICT INSPECTOR:                                       │
│ 🔴 Claimed Pins: GPIO 5 (Mic WS) • GPIO 18 (Relay) • GPIO 21 (Mic SCK) • GPIO 26 (SD) │
│ 🟢 Available Safe GPIOs: GPIO 4 • GPIO 13 • GPIO 14 • GPIO 17 • GPIO 22 • GPIO 23 ...  │
└────────────────────────────────────────────────────────────────────────────────────────┘
```

### New Telemetry & Diagnostic Features:
1. **Hardware MAC ID:** Displays permanent factory silicon MAC address.
2. **SoftAP Address:** Live gateway address (`192.168.4.1`) for direct AP connection.
3. **Station Network IP:** Shows router-assigned IP (`192.168.1.75`) or `"Not Connected (AP Only)"`.
4. **Wi-Fi Signal (RSSI):** Live signal strength in dBm with color-coded badges:
   * **Green ($\ge -65\text{ dBm}$):** Strong signal; optimal for wireless OTA updates.
   * **Yellow ($-66\text{ to } -75\text{ dBm}$):** Moderate signal; reliable telemetry.
   * **Red ($< -75\text{ dBm}$):** Weak signal; recommend moving closer to access point.
5. **Appliance Uptime:** Real-time operational uptime counter formatted dynamically into minutes and seconds (`135m 58s`) or hours (`2h 15m 58s`).
6. **🔄 Restart Appliance Button:** Direct, safe software reboot button with confirmation dialog.
7. **Hardware GPIO Conflict Inspector:** Actively cross-references all assigned pins across the 8-channel bus, digital mic, IR receiver, and mains relay:
   * Highlights in-use pins in red.
   * Displays all available open safe GPIOs in green.
   * Emits an immediate high-priority warning banner if two peripherals are accidentally assigned to the same GPIO.

---

## 11. Hardware Wiring, Cluster Topology & Relay Guide

Accessible from the Configuration Hub via the **`📘 Open Wiring & Cluster Guide`** button.

### 1. Monolithic Continuous Strip Wiring (Vertical Serpentine)
```
[Top]     (15) ───▶ (16)     (47) ───▶ (48)
           ▲         │        ▲         │
           │         │        │         │
           │         ▼        │         ▼
[Bottom]  (0)       (31) ───▶ (32)     (63)
          DIN     [Col 1]   [Col 2]   [Col 3]
         [Col 0]
```

### 2. Modular 16×16 Panel Cluster Assembly (Horizontal Snake Chaining)
```
Row 1 (Top):     [Panel 7] ◀── [Panel 6] ◀── [Panel 5] ◀── [Panel 4]
                                                              ▲
                                                              │ (Daisy-chain loop up)
Row 0 (Bottom):  [Panel 0] ──▶ [Panel 1] ──▶ [Panel 2] ──▶ [Panel 3]
                    ▲
                   DIN (From ESP32 GPIO)
```
* **Supported Modular Sizes:** $16\times16$ (256 LEDs), $16\times32$ (512 LEDs), $16\times48$ (768 LEDs), $32\times64$ (2,048 LEDs), $48\times64$ (3,072 LEDs), $64\times64$ (4,096 LEDs), $32\times128$ (4,096 LEDs).

### 3. High-Current 5V Parallel Power Distribution Rules
```
           ┌──────────────────────────────────────────────┐
  +5V ─────┼───────┬──────────────┬──────────────┬────────┤ (+5V Parallel Bus Bar)
           │       │ +5V          │ +5V          │ +5V    │
        [ESP32] [Panel 0]      [Panel 1]      [Panel 2]  ...
           │       │ GND          │ GND          │ GND    │
  GND ─────┼───────┴──────────────┴──────────────┴────────┤ (GND Parallel Bus Bar)
           └──────────────────────────────────────────────┘
```
* ⚠️ **Mandatory Rule:** Never route high-current 5V DC power in series through thin matrix copper traces. Run heavy-gauge wire (14–16 AWG) directly from your power supply to a parallel distribution bus bar, tapping 5V and GND directly to every single panel.

### 4. Hardware Mains Relay Wiring & Trigger Polarity
```
  ESP32 GPIO 18 ─────────▶ Relay IN
  ESP32 3.3V / 5V ───────▶ Relay VCC
  ESP32 GND ─────────────▶ Relay GND

  Relay COM / NO ────────▶ Switches Live 120V/240V AC to LED Power Supplies
```
* **Active HIGH (Mode 1):** Direct NPN/MOSFET-driven relay boards (3.3V logic closes relay).
* **Active LOW (Mode 2):** Optically isolated relay boards (0V ground logic closes relay).

### 5. Smart LED 4-Wire Dual-Data Backup Wiring (WS2813 / WS2815)
```
ESP32 GPIO ────▶ [DIN] Panel 1 [DOUT] ────────▶ [DIN] Panel 2 [DOUT] ──▶ ...
GND ───────────▶ [BIN] Panel 1 [BOUT] ──┬─────▶ [BIN] Panel 2 [BOUT] ──▶ ...
                                        │
                       (Backup Data Jump)
```
* Connect `BIN` on the very first panel directly to **GND**. For all subsequent panels, connect `DOUT` to `DIN`, and `BOUT` to `BIN`.
* ⚠️ **Voltage Warning:** WS2815 and 12V WS2811 require **12V DC** connected to VCC. Connecting 12V directly to the ESP32 will permanently damage the microcontroller. Always share a common Ground (GND).

---

## 12. Quick Tips, Best Practices & Acoustic Setup

1. **Commit Your Look to Flash:** When exploring patterns, themes, backgrounds, or speeds, changes preview instantly in high-speed RAM. Once you find a look you love, click **💾 Save Config** on the top action bar (or **💾 Save General Settings to Flash** under Settings) so it persists across power cycles.
2. **Room Acoustic Calibration:** If equalizer bars bounce when the room is silent, click **🎯 Calib** while the room is quiet to automatically map ambient room noise floors across all bands. Alternatively, open **Column 3 $\to$ ⚙️ Tuning & Peaks** and raise the **Noise Gate Filter** slightly (default is 6 / 300 units).
3. **USB Power Safety:** When powering your display from a computer USB port or phone charger, open **⚙️ Config $\to$ 📐 Matrix & Hardware** and set the **Max 5V Current** to **1000 mA (1.0A)** or lower to prevent brownouts.
4. **Instant Standby & Relay Sleep:** Press the power button on an IR remote or click the circular **⏻** power button in the web header to enter standby. The display blanks instantly, and the hardware relay cuts mains power to eliminate coil whine and idle energy consumption.
5. **Switching to Lamp Mode:** When listening to podcasts or relaxing without music, tap **`🛋️ Lamp`** in the header. The display will transition into continuous ambient room lighting using your selected relaxation shader without reacting to room noise.
6. **Simulated Mobile View on Desktop:** If you are operating the visualizer from a laptop or desktop monitor and prefer the compact single-column app layout with the bottom navigation dock, click **🖥️ PC Mode** in the top bar to switch into **📱 Phone View**.
```
