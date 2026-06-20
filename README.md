# PWM Current Control — One-Quadrant DC-DC Converter

> Design, tuning and stability verification of a closed-loop current regulator for a DC-DC converter.

## Overview

A current-control loop for a one-quadrant DC-DC converter driving an RL load, optimized for step
response. The work goes from analytical modeling of the plant, through PI-controller tuning, to
transient and frequency-domain validation in simulation.

## Design Specifications

<!-- fill in your personalized m, n values and derived data -->
| Parameter | Value |
|-----------|-------|
| Input voltage Vi | 34 V |
| Load inductance L | 2 mH |
| Load resistance R | 4 Ω |
| PWM frequency f_PWM | 22.974 kHz |
| Triangle amplitude Vtr | 10 V |
| Filter time constant Tf | 0.1741 ms |

## Approach

1. **Plant modeling** — derived the transfer functions of converter + load, current transducer and PWM modulator; linearized the non-linear converter around its operating point using averaged state variables.
2. **Controller design** — tuned a **PI regulator with the modulus-optimum criterion** and sized the real component values (R0, R1, C1) and the RC measurement filter.
3. **Transient validation (PSIM)** — step response: settling time and overshoot vs. theory (≈4.72·Tσ, 4.3 %); duty cycle; current ripple measured vs. calculated; error signal.
4. **Robustness** — ±25 % / ±50 % supply variation, ±50 % load step, and a trapezoidal reference (steady-state error for a ramp).
5. **Stability** — AC sweep → Bode plot → **phase margin** measurement.

## Tools

PSIM · control theory · power electronics

## Skills Demonstrated

Closed-loop control design · PI tuning (modulus optimum) · power-electronics modeling and
linearization · frequency-domain stability (phase margin) · simulation-driven validation against
theoretical targets.
