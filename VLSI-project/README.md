# VLSI Implementation of a Hardware-Level Image Convolution Block Integrated with an RV32E MCU

---

## Overview
This project implements a compact, fully digital system-on-chip (SoC) combining a synthesizable RV32E RISC-V processor with a hardware image signal processing (ISP) block. The design was taken through the complete CMOS VLSI flow—from RTL development and simulation through synthesis, physical design, verification, and final GDSII generation—mirroring industry-standard chip design practices.

Although the chip was not fabricated, the project exercised the full pre-tape-out workflow used in modern digital IC development.

---

## Design Constraints
The system was developed under strict architectural and physical constraints:

- Fully digital design (no analog blocks)
- No use of SRAM macros
- Maximum die area: **2 mm × 2 mm**
- Package limited to **59 I/O pins**
- Target clock frequency: **20 MHz**
- Technology: **TSMC 180 nm CMOS** (NDA-protected)

These constraints significantly influenced architectural decisions, particularly for memory handling and image processing.

---

## System Description
The final design implements a single-cycle RV32E RISC-V processor capable of loading from and writing to external flash memory. Integrated alongside the processor is a 3×3 convolution-based ISP module supporting pass-through, sharpening, Gaussian blur, and edge detection operations on 24-bit pixel data.

The system meets timing and area constraints while fitting entirely within the prescribed die footprint, making it suitable for compact embedded SoC applications.

---

## Project Abstract (From Final Report)

> *This project presents a synthesizable RV32E RISC-V processor implementing a single-cycle datapath that supports loading from and writing to external flash memory. The processor integrates a 3×3 convolution-based image signal processing (ISP) module capable of pass-through, sharpening, Gaussian blur, and edge detection operations on 24-bit pixel data. The final implementation meets a 20 MHz clock target and occupies a 2 × 2 mm layout footprint, making it suitable for integration into compact embedded SoC architectures.*

The abstract above reflects the formal description submitted as part of the final project report. 

---

## Implementation Flow
The complete VLSI design flow included:

- RTL development and verification using **ModelSim / Questa**
- Functional debugging and performance validation at the RTL level
- Course timing optimization using **TCL scripts**
- Logic synthesis, gate-level netlist extraction, and final optimizations using **Cadence Genus**
- Physical layout, seal ring insertion, and padding using **Cadence Virtuoso**
- Design rule checking (DRC) and layout versus schematic (LVS) verification using **Calibre**
- Final **GDSII export** for tape-out submission

This process was used to simulate an end-to-end industry chip design workflow.

---

## My Role — ISP Block Design
I was responsible for the design and verification of the image signal processing (ISP) block and its interface to a VHDL-based display controller.

The ISP performs convolution operations using a **sequential, pixel-by-pixel processing model**, rather than frame-buffered operation. Due to the absence of SRAM macros, memory availability was extremely limited which requiring careful management of image dimensions, clock cycles, and reset behavior.

Unlike modern ISP pipelines that rely on large on-chip memories and the use of Nueral Networks for kernel selection, this design implements fixed 3×3 convolution kernels and processes pixels incrementally, emphasizing deterministic hardware control and minimal resource usage to meet design constraints.

A high-level overview of the ISP architecture and algorithms can be viewed **[here](ISP_support.pdf)**.

---

## Creative Image Handling Due to Hardware Constraints
Because on-chip memory was minimal, image data could not be stored locally. Instead, pixels were streamed into the ISP block sequentially, and convolution operations were computed one pixel at a time. This imposed additional constraints on padding behavior, kernel alignment, and output timing.

Despite these limitations, the design successfully demonstrates correct convolution behavior under realistic hardware constraints for the TSMC18 technology libraries we had to work with.

---

## Results
RTL testing revealed the visual limitations inherent to small kernel sizes and sequential processing, but also confirmed correct functionality of the ISP logic.

Below is an example of a ChatGPT-generated image processed under the **sharpening** mode:

<p align="center">
  <img src="duck.png" alt="original image" width="300">
</p>

<p align="center">
  <img src="convolved.png" alt="sharpened image" width="300">
</p>

While the convolution output is limited by kernel size, need for external padding, color channel handling, and image resolution, the sharpening effect validates the correctness of the convolution logic for the ISP integration. With proper image streaming and external memory support, the block would function as intended in a fabricated system.

---

## Team Collaboration
This project was completed by a four-member team, with each member responsible for a major subsystem. Work was primarily conducted asynchronously, with weekly design reviews used to synchronize progress and resolve integration challenges.

While asynchronous development occasionally led to interface mismatches and redundant work, in-person debugging sessions proved effective in resolving issues quickly and aligning subsystem expectations. Clear task ownership and iterative design reviews were key to meeting deadlines.

---

## What This Project Demonstrates
- End-to-end CMOS VLSI design flow from RTL to GDSII
- Constraint-driven digital design under strict area, memory, and I/O limits
- Hardware implementation of DSP algorithms without SRAM support
- RTL simulation, debugging, and timing closure
- Physical design awareness, including layout, DRC, and LVS
- Effective collaboration on a multi-block SoC design
