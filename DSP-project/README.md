# Octave Band Filter Bank for Audio Signal Classification

---

## Overview
This project involved the design and implementation of a digital signal processing system for octave-based audio analysis. A bank of FIR bandpass filters was used to isolate frequency bands corresponding to piano octaves, enabling classification of input signals based on their dominant spectral content.

The work combined analytical DSP theory with MATLAB-based implementation, visualization, and validation. The project was completed as a team effort for a graduate-level DSP course, with modular responsibilities distributed across filter design, signal analysis, and system integration.

The complete implementation and documentation are available in the GitHub repository:  
[Octave Band Filtering — DSP Final Project](https://github.com/DLN2003/DSP-Final-Project)

---

## System Description
The system operates by passing an input audio signal through a bank of FIR bandpass filters, each tuned to a specific octave frequency range. The output of each filter is analyzed to determine which octave contains the dominant energy, allowing the input signal to be classified accordingly.

Key system components include:
- octave band definition and frequency partitioning
- FIR bandpass filter generation
- normalization and gain consistency across filters
- signal analysis for octave classification
- visualization of frequency-domain and time-domain behavior

---

## My Role — Filter Design and System Documentation
My primary responsibility was to design and test a MATLAB function that generates bandpass filters used throughout the project. This function parameterizes filter cutoff frequencies and sampling rate to produce a consistent and reusable filter bank.

In addition to filter design, I authored the project README, which required a comprehensive understanding of the entire DSP pipeline. This included documenting filter theory, signal flow, normalization strategies, and classification logic, as well as generating figures that connect theoretical expectations to observed behavior.

---

## Implementation Notes
The system was implemented entirely in MATLAB, leveraging built-in signal processing functions while maintaining explicit control over filter parameters and signal flow. Emphasis was placed on clarity, reproducibility, and alignment between theoretical expectations and numerical results.

The project structure and documentation were designed to make the DSP pipeline understandable to readers with a signal processing background, reinforcing the connection between theory, implementation, and observed performance.

---

## What This Project Demonstrates
- Practical FIR bandpass filter design using windowing methods
- Construction and validation of an octave-based filter bank
- Frequency-domain and time-domain signal analysis
- Understanding of normalization and gain consistency in filter banks
- System-level DSP thinking beyond individual filter blocks
- Clear technical documentation and communication of DSP concepts

