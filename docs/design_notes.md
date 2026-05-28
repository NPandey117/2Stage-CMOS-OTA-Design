# Design Notes – 2-Stage CMOS OTA (TSMC 180nm)

## Objective

The objective of this project was to design and simulate a two-stage CMOS Operational Transconductance Amplifier (OTA) using TSMC 180nm technology and verify its operation as a non-inverting amplifier with closed-loop gain of 2.

---

# Design Specifications

| Parameter        | Target     |
| ---------------- | ---------- |
| Supply Voltage   | 1.8V       |
| Technology       | TSMC 180nm |
| Minimum DC Gain  | 40 dB      |
| Closed Loop Gain | 2          |
| Input Step       | 0.2V       |

---

# Design Approach

The OTA was designed using a conventional two-stage architecture:

1. Differential input stage
2. Current mirror active load
3. Common-source second gain stage
4. Current source biasing

An initial MOSFET overdrive voltage of 200mV was assumed for hand calculations.

---

# Initial Hand Calculations

The design process started with estimating:

* Bias currents
* Transconductance (gm)
* Output resistance (ro)
* Gain contribution of each stage
* MOSFET W/L ratios

The calculations were later refined using simulation-derived operating point parameters.

---

# First Stage

The first stage consists of:

* NMOS differential pair (M1, M2)
* PMOS current mirror load (M3, M4)
* Tail current source (M0)

This stage primarily provides:

* Differential amplification
* High input impedance
* Initial voltage gain

---

# Second Stage

The second stage uses:

* Common-source amplifier transistor (M5)
* Current source load (M6)

This stage improves:

* Overall voltage gain
* Output swing

---

# Stability Considerations

AC analysis was performed to verify amplifier stability.

Simulation results:

* Open-loop gain: 56.6 dB
* Phase margin: 88.3°

The obtained phase margin indicates stable closed-loop operation.

---

# Closed-Loop Verification

The OTA was connected as a non-inverting amplifier with gain = 2.

A transient analysis was performed using a 0.2V input step.

Observed behavior:

* Input: 0.9V → 1.1V
* Output: 0.9V → 1.3V

This verified the expected closed-loop gain.

---

# Challenges Faced

Some challenges during the design process included:

* Achieving sufficient gain while maintaining stability
* Selecting suitable bias currents
* Proper transistor sizing
* Balancing gain and phase margin
* Tuning the second stage for better transient response

---

# Learning Outcomes

Through this project, I learned:

* CMOS analog circuit design fundamentals
* Differential amplifier operation
* Current mirror biasing
* Two-stage OTA architecture
* Frequency response analysis
* Phase margin and stability concepts
* LTspice simulation workflow
* Practical transistor sizing techniques

---

# Future Improvements

Possible future improvements include:

* Miller compensation optimization
* Slew rate enhancement
* Noise analysis
* Power optimization

---

# Tools Used

* LTspice
* TSMC 180nm CMOS parameters
* Analog small-signal analysis techniques

