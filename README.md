# Spectral Dynamic Compressor

A real-time, low-latency spectral dynamic processor built with C++ and the JUCE framework. This plugin splits incoming audio using FFT-based processing, applies independent time-smoothed gain reduction across customizable frequency bands, and reconstructs the signal with accurate stereo detection.

---

## Features

* **Dual-Channel Detector:** Peak magnitude tracking across Left and Right channels ensures symmetrical gain reduction for stereo material.
* **4-Band Dynamic Control:** Independent frequency, threshold, Q factor, attack, and release parameters for each band.
* **Band Types:** Supports Bell, Low Shelf, and High Shelf filtering shapes per band.
* **Spectral Tilt Adjustment:** Control overall spectral balance from -12 dB/oct to +12 dB/oct.
* **Overlap-Add FFT Pipeline:** Smooth spectral reconstruction using Hanning windowing and overlap-add processing.
* **Full Automation Support:** Integrated with `juce::AudioProcessorValueTreeState` (APVTS) for seamless DAW automation and parameter persistence.

---

## Plugin Parameters

| Parameter | Range | Default | Description |
| :--- | :--- | :--- | :--- |
| **Detector Gain** | -30.0 dB to +60.0 dB | 0.0 dB | Adjusts signal sensitivity entering the detection stage. |
| **Intensity** | 50% to 300% | 100% | Scales the overall strength of gain reduction applied. |
| **Spectral Tilt** | -12.0 to +12.0 dB/oct | +3.0 dB/oct | Tilts the frequency balance before detection. |
| **Output Gain** | -24.0 dB to +24.0 dB | 0.0 dB | Final makeup gain applied to the output signal. |

### Per-Band Parameters (Bands 1–4)

* **Type:** Off, Bell, Low Shelf, High Shelf
* **Frequency:** 20 Hz to 20,000 Hz
* **Threshold:** -60.0 dB to 0.0 dB
* **Q:** 0.1 to 10.0
* **Attack:** 0.01 ms to 50.0 ms
* **Release:** 1.0 ms to 100.0 ms
