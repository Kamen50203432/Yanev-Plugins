# Transient Accent

**Transient Accent** is a zero-latency JSFX audio plugin for Cockos REAPER created by Kamen Yanev. It provides precision transient shaping and reactive normalization with frequency-selective sidechain detection and a real-time oscilloscope display.

---

## Features

* **Zero-Latency Processing:** Pure zero-latency path suitable for live monitoring and tracking.
* **Frequency-Selective Sidechain:** Independent high-pass and low-pass filters allow you to isolate specific frequency ranges (e.g., snare snaps or kick clicks) to drive the transient detector.
* **Peak-Hold Lock Normalization:** Captures the peak of the transient hit and applies proportional boost dynamically during the transient window.
* **Re-arm Hysteresis:** Prevents chattering and false re-triggers by requiring the signal to drop a set amount below threshold before resetting.
* **Built-in Visualizer:** A live graphical interface displays incoming signal envelopes and real-time gain reduction/boost activity.

---

## Parameter Controls

| Parameter | Range | Default | Description |
| :--- | :--- | :--- | :--- |
| **Detection Min Freq (Hz)** | 20 to 20,000 Hz | 20 Hz | High-pass filter cutoff for the sidechain detection path. |
| **Detection Max Freq (Hz)** | 20 to 20,000 Hz | 20,000 Hz | Low-pass filter cutoff for the sidechain detection path. |
| **Attack Time (ms)** | 0.01 to 2.5 ms | 0.1 ms | Micro-smoothed attack time to prevent 1-sample gain-jump clicks. |
| **Threshold (dB)** | -60.0 to 0.0 dB | -20.0 dB | Level required to trigger the transient accent state. |
| **Target Boost Above Thresh (dB)** | 0.0 to 24.0 dB | 6.0 dB | Desired peak boost level relative to the threshold during transients. |
| **Transient Time (ms)** | 0.5 to 100.0 ms | 10.0 ms | Duration of the active accent window per hit. |
| **Re-arm Hysteresis (dB)** | 0.0 to 12.0 dB | 3.0 dB | Level drop below threshold required to reset and re-arm the trigger. |
| **Output Gain (dB)** | -24.0 to +24.0 dB | 0.0 dB | Master output level adjustment post-processing. |

---

## How It Works

1. **Sidechain Filtering:** The input signal is passed through adjustable high-pass and low-pass filters to isolate the frequency band of interest for detection.
2. **State Triggering:** When the filtered detection envelope exceeds the **Threshold**, the plugin enters the accent state, locking onto the peak of the hit.
3. **Reactive Normalization:** During the **Transient Time** window, the plugin calculates the required gain to scale the transient up to the target boost ceiling.
4. **Release & Reset:** Once the transient window expires, the gain smoothly returns to unity ($0\text{ dB}$) using an 8 ms release time, waiting until the signal falls below the **Re-arm Hysteresis** threshold before accepting the next hit.
