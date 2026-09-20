# 📖 ESP32 Audio Spectrum Visualizer — Complete Web Dashboard Guide

Welcome to the comprehensive user manual for the **ESP32 Professional Audio Spectrum Visualizer** web dashboard. This document details the purpose and behavior of every tab, button, slider, and menu option available in the system.

---

## 📑 Table of Contents
1. [Global Header & Top Action Bar](#-global-header--top-action-bar)
2. [Tab 1: 🎨 Visuals](#-tab-1--visuals)
3. [Tab 2: 🎚️ Acoustics](#-tab-2--acoustics)
4. [Tab 3: 🎯 Peaks & Ballistics](#-tab-3--peaks--ballistics)
5. [Tab 4: 🎛️ Parametric Equalizer Studio](#-tab-4--parametric-equalizer-studio)
6. [Tab 5: 🎬 Master Show Playlist Engine](#-tab-5--master-show-playlist-engine)
7. [Tab 6: 🚀 Startup Intro & Typography](#-tab-6--startup-intro--typography)
8. [Tab 7: 📐 Matrix Configuration & Power](#-tab-7--matrix-configuration--power)
9. [💡 Quick Tips & Best Practices](#-quick-tips--best-practices)

---

## 🧭 Global Header & Top Action Bar

Located at the very top of the dashboard and visible across all tabs:

* **Header Title & Version Badge:** Displays the project title and active firmware build version (e.g. `ver. 1.1`).
* **Active Grid Configuration Subtitle:** Displays your active matrix hardware status in real time:
  * Total Columns × Total Rows (e.g. `64×24 Grid`).
  * FastLED Pin Count (`1-Pin`, `2-Pin`, or `4-Pin`).
  * Active Frequency Bands (`16 Bands` or `32 Bands`).
  * Active Column Width (`1`, `2`, `3`, or `4 LED/Band`).
* **Status Bar:** Provides instant feedback whenever a slider is moved, audio is calibrated, or settings are committed to flash.
* **💾 Save to Memory:** **Crucial button.** Live slider movements and menu selections modify parameters in high-speed RAM only (zero flash memory wear). Clicking this button permanently commits all current visualizer settings to non-volatile NVS flash memory so your custom setup survives power cuts and reboots.
* **🎯 Calibrate Floor:** Takes a 32-frame digital sample of your room's ambient background noise and sets a customized noise-floor cutoff for every individual band. Run this while the room is quiet to keep the equalizer bars flat when no music is playing.

---

## 🎨 Tab 1: Visuals

Controls the appearance, rendering patterns, color themes, and ambient background layers of the display.

### 1. Main Dropdowns
* **Visual Pattern / Effect (25 Options):** Selects the active pattern (Patterns 0–24). Selecting **"⚡ Auto Cycle All Patterns/Effects"** (`255`) continuously rotates through all patterns automatically.
* **Color Theme (105 Categorized Options):** Changes the color palette across bars and effects. Divided into organized groups:
  * *Classic & Studio Equalizers* (Themes 0–15)
  * *Neon Cyber & Synthwave* (Themes 16–29)
  * *Scott Marley Specials* (Themes 30–34)
  * *Dynamic Flow Palettes* (Themes 35–54)
  * *Vibrant & Atmospheric* (Themes 55–69)
  * *Tri-Zone Frequency Splits (Part 1)* (Themes 70–80)
  * *Modern Luxury & Cyber Vibe* (Themes 81–95)
  * *Tri-Zone Frequency Splits (Part 2)* (Themes 96–104)
  * Selecting **"⚡ Auto Cycle All Themes"** (`255`) continuously cycles themes.
* **Universal Background Layer (23 Ambient Styles):** Renders an ambient backdrop behind the equalizer bars (Modes 0–22). Modes 21 and 22 (*Random Theme Flow* and *Random Static Theme*) automatically shift through different random color themes on a timer. Selecting **"⚡ Auto Cycle Background Themes"** (`255`) cycles through background modes.
* **Number of LEDs per Band (Live Width):** Changes how many physical LED columns make up a single frequency band (1, 2, 3, or 4 LEDs wide). Adjusting this dynamically reconfigures the audio engine between **16 bands** and **32 bands** with automatic centering.

### 2. Matrix & Background Brightness (100% Decoupled)
* **Main Matrix Brightness (0–255):** Controls the brightness of the foreground equalizer bars, peaks, and particles only.
* **Background Brightness (1–50):** Controls the ambient background brightness independently. Setting it to `1` produces a faint moonlight whisper without washing out the visualizer, and changing the main brightness has zero effect on the background.

### 3. Auto-Cycle & Shuffling Controls
* **Auto Effects:** Toggles automatic pattern rotation ON or OFF.
* **Pattern Order (Linear / Random):** Sets pattern auto-cycling to advance sequentially (`0 → 1 → 2...`) or shuffle randomly.
* **Auto Themes:** Toggles automatic color theme rotation ON or OFF.
* **Theme Order (Linear / Random):** Sets theme cycling to advance sequentially or shuffle randomly.
* **Auto Bgrn:** Toggles automatic background mode rotation ON or OFF.
* **Bgrn Order (Linear / Random):** Sets background cycling to advance sequentially or shuffle randomly.
* **Auto Flow:** Automatically cycles through all 18 flow directions.
* **Bgrnd (Music Active / Always On):** 
  * *Music Active (Default):* The background illuminates only when music is playing and smoothly fades to pitch black when music stops.
  * *Always On:* Keeps the background lit continuously regardless of audio.

### 4. Independent Auto-Cycle Timers
* **Pattern Auto-Cycle Time (3s–60s):** How long each visual pattern displays before switching.
* **Color Theme Auto-Cycle Time (3s–60s):** How long each color theme displays before switching.
* **Background Auto-Cycle Time (3s–60s):** How long each background mode displays before switching (also controls how often Modes 21 and 22 pick a new random color theme).

### 5. Color Flow & Direction (18 Flow Directions)
* **Flow Direction:** Determines which direction colors move across dynamic palettes (Up, Down, Left, Right, 4-corner Diagonals, Radial Bloom, Radial Implosion, Diamond Ripples, 4-Corner Radials, Wave Collisions, and Knight Rider Scanners).
* **Diagonal Angle (30°–60°):** Adjusts the angle of the 4 diagonal flow directions.
* **Theme Flow Speed (0–10):** Sets the speed of dynamic palette motion (`0` pauses color movement).

### 6. Scrolling Wave Bars Controls (Patterns 16 & 17)
* **Wave Scroll Speed (1–10):** Controls the horizontal scrolling rate of wave bars independently from the theme flow speed.
* **Wave Scroll Direction:** Scrolls the frequency wave to the Left or to the Right.

### 7. Procedural Effects Customizers
* **Swaying Orbit Speed (1–10):** Sets the orbital sweep speed of Pattern 10 (Swaying Radial Pulse).
* **Waterfall Stream Speed & Direction:** Controls Pattern 11 (Spectrogram stream speed and 4-way flow: Left, Right, Down, or Up).
* **Floating Bubbles (Pattern 12):** Adjusts speed (1–10), size scale (1–5), and the total number of floating bioluminescent orbs (2–16).
* **Popcorn Cannon (Pattern 13):** Adjusts total kernel count (8–48) and particle size mix (Small 1×1, Mixed, or Large 2×2).
* **Plasma Flame (Patterns 14 & 15):** Adjusts upward flame flicker speed (1–10) and horizontal drift direction (Left or Right).
* **Volcano Multi-Caldera (Pattern 22):** Sets sweeping speed (1–10), caldera count (3, 6, or 9 across Bass, Mids, Highs), and magma ember particle size (Small, Mixed, or Large).

---

## 🎚️ Tab 2: Acoustics

Fine-tunes digital audio reception, sound filtering, and automatic display sleeping.

* **Master Sensitivity (10–100):** Digital pre-amplifier gain. Increase this for quiet rooms or low-volume listening; decrease it for high-volume concert setups to prevent clipping.
* **Band Fill (Bleed) (0%–80%):** Controls frequency smoothing between adjacent columns. A higher percentage fills gaps between bands for a fuller visual curve; a lower percentage gives sharp, isolated needle spikes.
* **Noise Filter (0–80):** Digital noise-gate threshold. Cuts out low-level room noise, computer fans, and microphone hiss so equalizer bars remain completely flat during silence.
* **Auto-Standby / Silence Detection:**
  * **Auto-Standby Button:** Turns automatic sleep monitoring ON or OFF.
  * **Silence Timeout (1–30m):** Sets how many minutes of continuous silence must pass before the LEDs power off to save energy.
  * **Sleep Display / Wake Display:** Instantly toggles the display into or out of standby mode manually.
* **3-Band Macro Equalizer (0.20–2.40):**
  * **Bass Level (Lows):** Amplifies or cuts sub-bass and kick-drum response.
  * **Mids Level (Vocals):** Amplifies or cuts snare, guitar, and vocal frequencies.
  * **Treble (Highs):** Amplifies or cuts hi-hats, cymbals, and upper harmonic frequencies.

---

## 🎯 Tab 3: Peaks & Ballistics

Customizes the physics and behavior of the floating peak indicator dots.

* **Peak Dot Action:**
  * **Falling Dot:** Peak dots hang momentarily at the top of a volume spike, then drop smoothly with gravity.
  * **Shooting Dot (Cannon Sparks):** Loud percussive hits launch projectile sparks upward (or outward depending on pattern orientation) at high speed.
* **Peak Dot Color (85 Options):** Selects peak color behavior (auto-matching the active theme, pure white, neon colors, multi-zone splits, cycles, or sparkles).
* **Peak Dot Size (Thickness):** 1 LED Thin (pinpoint), 2 LEDs Medium (bold), or 3 LEDs Chunky (block).
* **Peak Dots Button:** Toggles peak dots ON or OFF globally.
* **Shooting Dot Speed (1–10):** Sets the launch velocity of cannon sparks.
* **Bar Drop Speed (1–5):** Controls how fast the main equalizer bars drop after hitting a peak (lower = slower decay; higher = snappy drop).
* **Standard Peak Hang Time (0–30 frames):** How long peak dots hover at maximum height before gravity kicks in.
* **Standard Peak Fall Delay (1–10):** Controls the falling speed of standard peak dots.
* **Dedicated "Dots Only" Timers (Patterns 1, 2, 18, 19):** Separate hang time and fall delay controls specifically for dots-only modes, allowing you to create slow, floating constellation effects without affecting standard bar modes.

---

## 🎛️ Tab 4: Equalizer Studio

A complete parametric equalizer studio for professional acoustic calibration.

### 1. Action Bar
* **💾 Save EQ Settings to Flash:** Permanently stores your active 16/32 band EQ curves and frequency cutoff tables to NVS flash.
* **🎯 Calibrate Noise Floor:** Analyzes room acoustics and sets individual noise thresholds for each frequency band.
* **🟡 Revert Unsaved Changes:** Restores curves to the last saved flash state.
* **🔴 Reset to Factory Defaults:** Restores the visualizer to the factory `"video"` equalization profile.

### 2. Acoustic Presets (22 Options)
* **11 Vocal & Speech Profiles:** *Vocal Clarity Pro, Warm Vocal & Acoustic, Pop Diva / Lead Vocal, Crisp Speech / Podcast, Vocal Air & Breath, Punchy Vocal / Rap, Soprano / Female Lead, Baritone / Male Vocal, Intimate Whisper / ASMR, Broadcast Radio Voice, Sibilance Tamer (De-Ess).*
* **11 Music & Genre Profiles:** *Video Match (Default), Flat Tone Sweep (1.0), Club / Deep Bass, R&B & 808 Hip-Hop, Rock & Metal Attack, Lo-Fi Chill & Warmth, Acoustic & Classical, EDM & Synthwave, Acoustic Fingerstyle, Sub-Bass Monster (30–90Hz), Vintage Tube Warmth.*

### 3. Sub-Tabs & Vertical Sliders
* **1. Acoustic EQ (`bandEQ`):** Individual gain sliders (0.2× to 3.0×) for each of the 16 or 32 bands. Shows the exact frequency span (e.g. `24-48Hz`) and color-coded acoustic zones (Red = Lows, Yellow = Mids, Cyan = Highs).
* **2. Ceilings (`minBandCeilings`):** Sets the dynamic range ceiling (2k to 28k) for each band to balance quiet and loud frequencies.
* **3. Frequency Cutoffs (`bandCutoffs`):** Adjusts the FFT frequency boundaries separating each band.

---

## 🎬 Tab 5: Master Show

An automation engine capable of running a multi-scene showcase of up to 50 scenes.

* **Master Show (ON / OFF):** Starts or stops automated playlist playback.
* **▶️ Resume Show:** Appears when the show is temporarily paused due to manual slider interaction, allowing you to jump back into the sequence.
* **Boot: Show (ON / OFF):** Automatically starts the Master Show sequence as soon as the ESP32 powers on.
* **Playlist Length Slider (1–50 Scenes):** Expands or shrinks the active playlist length.
* **Scene Cards (Dynamic & Context-Aware):**
  * **Header:** Displays Scene number, live status tag (`▶️ Playing` / `⏸️ Paused`), **▶️ Test** (instantly previews this scene on the matrix), and **🗑️ Delete** (removes the scene).
  * **Pattern / Effect:** Selects any of the 25 patterns or choose `⚡ Auto Cycle All Patterns`.
  * **Color Theme:** Selects any of the 105 themes or choose `⚡ Auto Cycle All Themes`.
  * **Background Layer:** Selects any of the 23 backgrounds or choose `⚡ Auto Cycle Background Themes`.
  * **Adaptive Controls:** Changing the pattern automatically adapts the card to display only the controls relevant to that effect (e.g. Bar Width, Peak options, Wave Speed, Bubble Count, or Volcano Calderas).
  * **Duration (3s–180s):** How long this scene runs before smoothly transitioning to the next.
* **➕ Add New Scene:** Appends a new scene to the end of the playlist.
* **💾 Save Show to Flash:** Commits your entire custom playlist to flash memory.
* **🔴 Restore Factory Showcase:** Restores the original 8 curated showcase scenes.

---

## 🚀 Tab 6: Startup Intro

Configures the opening boot sequence, typography, and on-matrix text messages.

* **Intro Typography / Font Size:**
  * *Standard (5×7 Font):* Full-height font recommended for 64-column matrices.
  * *Compact (3×5 Micro Font):* Compact font designed to fit 16 and 32-column displays.
* **Line 1 Message (Top) & Line 2 Message (Bottom):** Enter custom greeting text (up to 32 characters each). Leave Line 2 blank for a single centered line. Click **Set** or press Enter to apply.
* **Intro Text Scroll Direction:** Scroll Left, Scroll Right, Scroll Up, Scroll Down, or Static Centered.
* **Intro Animation Effect (7 Styles):** *Circular Radial Bloom, Matrix Digital Rain, Dual Laser Sweep, Hyperspace Warp Jump, Plasma Spiral Vortex, Diamond Prism Shutter, Firework Mortar Explosion.*
* **Buttons:**
  * **Text: Normal / Upside Down:** Flips text orientation by 180° for upside-down ceiling matrix mounts.
  * **Intro Text: ON / OFF:** Enables or disables startup text banners.
  * **Intro Visual: ON / OFF:** Enables or disables opening graphic animations.
  * **Pause in Center: ON / OFF:** Pauses scrolling text when it reaches the center of the display.
* **Sliders:**
  * **Pause Duration (1–5s):** How long text holds in the center before resuming scroll.
  * **Text Scroll Speed (1–20):** Animation speed for scrolling text.
  * **Intro Visual Speed (1–20):** Animation speed for the intro graphic effect.
* **Preview Intro Now:** Immediately triggers the startup animation and text sequence on your matrix without needing to reboot.
* **🔴 Reset All Settings to Default:** Restores every setting in the visualizer to factory defaults.

---

## 📐 Tab 7: Matrix Configuration & Power

Configures hardware panel layout, power management, Wi-Fi networking, and licensing.

* **Matrix Width (Columns):** Select 16, 32, or 64 columns.
* **Matrix Height (Rows):** Adjust row height from 8 up to 64 rows.
* **FastLED Output Channels (Parallel Pins):**
  * *1 Pin (GPIO 0):* Standard single-line output.
  * *2 Pins (GPIO 0 & 4):* Splits the matrix into left and right halves (2× framerate).
  * *4 Pins (GPIO 0, 4, 16, 17):* Splits the matrix into four quadrants (4× framerate).
* **FastLED Power Management (5V Current Limiter):**
  * Sets the maximum power supply current from **500 mA (0.5A)** up to **15,000 mA (15A)** in 250 mA increments.
  * Dynamically calculates LED power draw per frame to prevent tripping USB ports or overheating power supplies.
* **Home Wi-Fi Setup (Station Mode):**
  * *Wi-Fi Connection Mode:* Choose between Access Point Only (`ESP32_VU_METER`) or Connect to Home Wi-Fi (runs AP and Station mode simultaneously).
  * *SSID & Password:* Enter your home network credentials.
  * *Network Status:* Displays the IP address assigned by your home router.
* **Hardware Identity & Activation:**
  * *Permanent Device ID (MAC Address):* Unique factory silicon hardware address. Click **📋 Copy** to copy it.
  * *License Status Badge:* Shows whether the firmware is currently in **2-Minute Demo Mode** or **Permanently Activated**.
  * *Activation Key Input:* Paste your cryptographic activation key and click **🔑 Activate Device** to unlock permanently.
* **Firmware Management:**
  * **Open Firmware OTA Updater:** Direct link to `/update` for flashing pre-compiled `.bin` files wirelessly through your browser.
* **💾 Save Geometry, Power & Network (Restart ESP32):** Saves matrix dimensions, parallel pin assignments, 5V power limiter, and network credentials to flash, then restarts the ESP32 to reallocate display memory.

---

## 💡 Quick Tips & Best Practices

1. **Saving Your Look:** When experimenting with colors, patterns, or peak speeds, your changes apply instantly in RAM. Once you find a look you love, click **💾 Save to Memory** on the top action bar so it persists after rebooting.
2. **First-Time Audio Setup:** If your bars bounce when the room is silent, go to **Tab 2 (Acoustics)** and raise the **Noise Filter** slightly, or click **🎯 Calibrate Floor** while the room is quiet.
3. **Running on USB Power:** If powering your matrix from a computer USB port or phone charger, go to **Tab 7 (Matrix)** and set the **Max 5V Current** to **1000 mA (1.0A)** or lower to prevent the port from shutting down.
4. **Instant Standby:** You can quickly turn the display off by pressing the power button on an IR remote or clicking **Sleep Display** under **Tab 2 (Acoustics)**. The microphone will continue listening and will wake up automatically when music plays if Auto-Standby is enabled.
