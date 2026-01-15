# Audio Tuning w/ Room EQ Wizard

Download & Install: [Room EQ Wizard (REW)](https://www.roomeqwizard.com)

## Preferences

- **Output:** System audio output feeding the PA (verify no OS EQ or processing)  
- **Input:** UMIK-1 USB Microphone  
- **Calibration:** 90-degree calibration file loaded  
- **Sweep Level:** –12 dBFS  

## Measurement Process

1. **Set up reference microphone:**

  - Orientation: **90 degrees (vertical)**  
  - Height: **Ear level**  
  - Location: **Primary listening area**

2. **Open the following REW tools:**

  - SPL Meter  
  - Signal Generator (Noise tab)  
  - Levels Meter

3. **Turn down the PA system first**, then connect the REW audio output to the system input.

4. **In the Signal Generator:**

  - Select **Pink Noise**  
  - Level: **–12 dBFS**  
  - Press **Play**

5. Slowly raise the PA system level until the SPL Meter reads:

  - **76–80 dB(C)**  
  - Confirm no clipping on the Levels Meter

6. Stop playback and close:

  - Signal Generator  
  - SPL Meter  
  - Levels Meter

## Measurement Sweeps

1. Click **Measure** (top left) to open the Measurements Window and configure:

  - **Type:** SPL  
  - **Method:** Sweep  
  - **Length:** 512k  
  - **Iterations:** 2  
  - **Frequency Range:**  
      - Preferred: **20–18,000 Hz**  
      - Optional: 15–20,000 Hz  
  - **Level:** –12 dBFS  
  - **Output:** Line Out  
  - Measure channels separately when possible:  
      - Left only  
      - Right only  
      - Left + Right (summed)

2. Press **Start** to begin the sweep and capture measurements.

## Analysis & Interpretation

### 1. SPL Response

- **Graph smoothing:** 1/6 octave  
- Shows frequencies that are over- or under-emphasized at the listening position  
- Optional: Enable **Phase** display to examine crossover behavior  
- Target response:
    - Broad trends within **±5 dB**  
    - Avoid correcting narrow dips (often position-dependent nulls)  

### 2. Waterfall (Decay)

- Displays decay time of frequencies (“ringing” or lingering energy)  
- Recommended focus for auditorium tuning:
  - **Frequency limits:** 20–300 Hz  
  - **Window:** ~30 ms  
  - **Time range:** 300–500 ms  
- Look for:
  - Low-frequency energy lingering >250 ms  
  - Improvements after delay or crossover adjustments  

### 3. Spectrogram

- Top-down view of frequency decay over time  
- **Color scale:** SPL  
- **Axis:** Time (decay) vs frequency  
- Useful for:
  - Visualizing low-frequency buildup  
  - Comparing before/after system changes  

## Multiple Measurement Positions

- Repeat measurements at additional listener locations:
  - 1 position: **1/2 back, center**  
  - 1 position: **2/3 back, center**  
  - 1 position: **2/3 back, slight left/right**  

> Use multiple positions to identify **consistent trends**.  
> Act on broad peaks seen across measurements, not isolated nulls.  

## Notes & Best Practices

- Always complete **speaker aiming and delay alignment** before applying EQ.  
- Use EQ only to address **broad, repeatable response issues**.  
- Save and archive:
  - REW measurement files  
  - Before/after screenshots (SPL, Waterfall, Spectrogram)  
- Document **why** changes were made, not just what was changed.

