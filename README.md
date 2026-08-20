# Transient-Perfect Comp

Transient-Perfect Comp is a transparent dynamic processor for REAPER, designed by Kamen Yanev. It provides precise dynamic control and level management while preserving original transient punch and clarity without introducing artificial harshness.


## Overview

Transient-Perfect Comp is designed to smooth out volume inconsistencies and manage dynamic peaks across your audio without sacrificing the natural attack and punch of your sound.

Unlike standard compressors that can dull the initial hit of a drum or transient instrument, this plugin isolates and preserves initial transient edges while gently controlling the sustaining signal body.


## How It Works

- **Transient Detection**: The plugin analyzes incoming signal envelopes in real time to differentiate between initial transient attacks and sustaining body audio.

- **Dynamic Gain Reduction**: Compression is applied intelligently to the body of the sound, allowing the transient peak to pass through clean and uncompressed.

- **Envelope Control**: Precise Attack and Release controls allow you to tailor exactly how quickly the processor responds to incoming signal spikes and recovers.

- **Makeup Gain & PDC**: Integrated makeup gain balances the processed output level, while built-in Plugin Delay Compensation (PDC) aligns the signal perfectly with the rest of your project in REAPER.


## Features

- **Transient Preservation Engine**: Clean dynamic reduction without rounding off crucial attack edges.

- **Intuitive Visual Interface**: Clear visual graph showing input levels and real-time gain reduction.

- **Precision Controls**: Independent Threshold, Ratio, Attack, Release, and Knee adjustments.

- **Workflow Shortcuts**: Full mouse wheel support and Ctrl + Double Click reset to default settings.

- **Automatic PDC**: Built-in Plugin Delay Compensation for perfect sample alignment in REAPER.


## Controls Overview

- **Threshold**: Sets the level at which compression begins (-60.0 dB to 0.0 dB).

- **Ratio**: Controls the amount of gain reduction applied once the signal exceeds threshold.

- **Attack**: Sets how quickly gain reduction engages (0.01 ms to 100 ms).

- **Release**: Controls recovery speed back to uncompressed levels (1 ms to 1000 ms).

- **Makeup Gain**: Adjusts overall output signal level (-24.0 dB to +24.0 dB).


## Mouse Gestures & Shortcuts

- **Click & Drag Knobs / Sliders**: Adjust parameter values vertically.

- **Mouse Wheel over Controls**: Fine-tune parameter values.

- **Ctrl + Double Click**: Reset control to factory default setting.
