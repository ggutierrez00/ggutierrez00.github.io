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
My primary responsibility was the design and implementation of the function that generates the octave-based bandpass filters used throughout the project. This function parameterizes filter cutoff frequencies and sampling rate to produce a consistent and reusable filter bank.

In addition to filter design, I authored the project README, which required a comprehensive understanding of the entire DSP pipeline. This included documenting filter theory, signal flow, normalization strategies, and classification logic, as well as generating figures that connect theoretical expectations to observed behavior.

---

## Bandpass Filter Design
The filter bank was implemented using FIR bandpass filters designed via standard windowing techniques. Octave band cutoff frequencies were defined based on musical pitch ranges, and filters were generated programmatically to ensure consistency and scalability.

Design considerations included:
- selection of filter length to balance frequency resolution and computational cost
- window choice to control sidelobe behavior
- normalization to ensure comparable passband gain across filters
- avoidance of excessive overlap between adjacent octave bands

<p align="center">
  <img src="fig_bpf_mag_response.png" alt="Bandpass filter magnitude response" width="420">
</p>

**Figure:** Magnitude response of a representative octave bandpass filter, illustrating passband isolation and attenuation of adjacent frequencies.

---

## Filter Bank Behavior
When combined, the set of bandpass filters forms a filter bank covering the frequency range of interest. Normalized frequency responses demonstrate clear separation between octave bands, enabling reliable identification of dominant spectral components.

<p align="center">
  <img src="fig_octave_normalized_responses.png" alt="Normalized octave band responses" width="420">
</p>

**Figure:** Normalized magnitude responses of the octave filter bank, showing frequency partitioning across bands.

---

## Signal Classification and Validation
The output of the filter bank was analyzed to determine which octave contained the highest energy for a given input signal. Test signals were used to validate correct octave identification, with results examined in both transient and steady-state regimes.

<p align="center">
  <img src="fig_filter_output_example.png" alt="Filter bank output example" width="420">
</p>

**Figure:** Example filter bank output demonstrating correct octave classification for a test input signal.

To ensure meaningful interpretation, transient effects were examined separately from steady-state behavior.

<p align="center">
  <img src="fig_transient_vs_steady.png" alt="Transient versus steady-state response" width="420">
</p>

**Figure:** Comparison of transient and steady-state filter responses, highlighting the importance of steady-state analysis for classification.

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
