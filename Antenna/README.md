# Antenna Theory and Electromagnetic Radiation

---

## Overview
This represents advanced coursework in antenna theory and applied electromagnetics, with emphasis on radiation mechanisms, near and far-field behavior, array synthesis, beam steering, and system-level performance considerations. Coursework combined analytical derivations with numerical modeling to explore how EM fields are generated, how antennas radiate and store energy, and how array configurations influence directivity and signal quality.

MATLAB and analytical EM theory were used extensively to visualize fields, radiation patterns, array factors, and performance metrics such as received power and signal-to-noise ratio.

---

## Radiated Fields from Current Elements
Using small current elements I was able to simulate the electrical field behavior of transmission lines and antennas. This was achived by using analytical expressions for the electric field produced by small current elements. Last, MATLAB was used to visualized the spatial structure of the radiated field in three dimensions. 

These simulations highlight the distinction between radiating and non-radiating configurations, showing how current orientation and geometry directly affect field strength and spatial distribution.

<p align="center">
  <img src="fig_current_elements_field.png" alt="Radiated field from current elements" width="420">
</p>

**Figure:** Electric field magnitude produced by two current elements equidistant from eachother with opposing polarity. This is representative of transmission line field characteristics.

---

## Near-Field Energy Storage and Reactive Power
Beyond radiation, antennas store energy in their near fields. To investigate this behavior, I analyzed the complex Poynting vector and evaluated power flow through closed integration surfaces surrounding radiating structures.

This analysis demonstrates that, in the near field, power flow can be purely reactive, corresponding to energy storage rather than radiation. This distinction is critical for understanding antenna efficiency, bandwidth limitations, and electrically small antennas (particularly in CMOS integrations).

<p align="center">
  <img src="fig_reactive_power_surface.png" alt="Reactive power flow surface" width="420">
</p>

**Figure:** Closed integration surface used to evaluate complex power flow of a particular geometry. This exercise demonstrated reactive energy storage in the near field of a radiating structure.  


---

## Antenna Arrays and Beam Steering
The coursework also focused on antenna arrays and their ability to shape and steer radiation patterns through controlled phase and spacing. Using analytical array factor expressions, I modeled how relative phase shifts alter beam direction and sidelobe structure.

These results demonstrate the fundamental principles behind beam steering and array directivity, which are central to modern radar, wireless communication, and sensing systems.

<p align="center">
  <img src="fig_array_factor_polar.png" alt="Array factor beam steering" width="420">
</p>

**Figure:** Normalized array factor for a two-element antenna array, demonstrating beam steering as a function of relative phase shift.  


---

## System-Level Performance: Power and Noise
Antennas were also analyzed as system components rather than isolated radiators. Using frequency-domain models, I examined received power and signal-to-noise ratio (SNR) as functions of frequency, antenna parameters, and thermal noise. Analysis at varying temperatures illustrated robust practical reasoning for specific design considerations.

This work connects electromagnetic theory to practical RF system design, emphasizing how antenna behavior directly impacts communication performance. 

<p align="center">
  <img src="fig_power_snr_vs_freq.png" alt="Power and SNR versus frequency" width="420">
</p>

**Figure:** Received power versus frequency, illustrating the impact of antenna characteristics on system performance. 

---

## Beam Separation and Array Optimization
Later on in the course, numerical methods were used to explore beam separation and array behavior under varying phase and spacing parameters. Random sampling and visualization techniques were applied to identify configurations that minimize beam separation and reveal array symmetry.

This analysis reinforces the sensitivity of array performance to design parameters and highlights tradeoffs encountered in practical array synthesis.

<p align="center">
  <img src="fig_beam_separation.png" alt="Beam separation visualization" width="420">
</p>

**Figure:** Beam separation analysis for array configurations, qualitatively showing how phase and spacing influence angular resolution.  

---

## What This Work Demonstrates
- Strong foundation in electromagnetic field theory and antenna radiation
- Ability to derive and interpret analytical field expressions
- Numerical modeling and visualization of EM phenomena using MATLAB
- Understanding of near-field vs far-field behavior and reactive power
- Antenna array synthesis, beam steering, and performance tradeoffs
- System-level reasoning behind antennas noise and communication performance


