# 24V-48V Synchronous Boost Converter for Ebike

# Synchronous Boost Converter

24V→48V DC-DC converter, 250W rated, 97.51% peak efficiency.

🏆 Won "Most Efficient Design" across all teams in Fall '25 class of Power Electronics Lab.

## Overview
Boost converter designed to power 3 phase electric bike motor, which required conversion from 24-48V. Our team optimized efficiency, winning the category, at the cost of size. This was designed for the Fall '25 class of Power Electronics Lab.

## Key Results
- Peak efficiency: 97.51% at 250W.
- Output ripple: 0.905V
- Efficiency across load range:
 <img width="1700" height="800" alt="image" src="https://github.com/user-attachments/assets/cc0c0f16-f66b-4c3a-9337-d64b01e58104" />

## Design
- **Topology:** Synchronous Boost for high efficiency
- **Magnetics:** Custom-wound inductor — 92.16µH, 19 turns, 0.79mm gap, 10 AWG. These specs were chosen using the Kg method on the E cores that were available in the lab, as well as to achieve Vin = 24V, Vout = 48V, ripple = 0.125, and inductor I = 10.417A.
- **Control:** Register-level PWM with dead-time management on TI C2000,
  ADC-based current/voltage sensing
- **PCB:** 4-layer, minimized gating loops and cut ground planes to reduce parasitic capacitance and inductance, seperated sensitive ADC/control signals from high di/dt and high dv/dt areas

## What I'd Change
I would love to have optimized the dead time and switching a bit more. With precise switching, we could have achieved zero voltage switching consistently, which would removes the switching loss from that cycle. We did not have the time to implement this, and also decided that it was too risky as choosing the wrong dead time could result in a short circuit of the switching loop and fry our MOSFETs. If I were to take on this project again outside of the class constraints, I would try different types of cores to allow for a larger inductor which could further increase efficiency and reduce ripple.


## Media
<img width="500" height="400" alt="image" src="https://github.com/user-attachments/assets/99216e9c-8b62-4a30-8d1b-8010899cccee" />
<img width="500" height="400" alt="image" src="https://github.com/user-attachments/assets/e9b10be3-b347-46a4-8075-f6dad529db6e" />

Board 3D model
<br><br><br>

<img width="700" height="500" alt="image" src="https://github.com/user-attachments/assets/fc77c59b-4004-4a4b-95cb-3b864b65329d" />

Peak Efficiency Oscilloscope Capture


## Tools
LTSpice, MATLAB, KiCad, TI C2000 (C)
