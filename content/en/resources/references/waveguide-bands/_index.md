---
title:        "Waveguide Bands"
linkTitle:    "Waveguide Bands"
description:  "General information about rectangular waveguides used in EPR spectroscopy."
type:         docs
weight:       10
draft:        False
---
Rectangular waveguides are used throughout EPR spectrometers to guide microwave power between components. Each waveguide band is designated by a WR (Waveguide Rectangular) number, where the number is approximately ten times the inner width of the waveguide in inches.

## Standard Waveguide Bands Used in EPR Spectroscopy

The table below lists the waveguide bands most commonly encountered in EPR instrumentation, along with their key parameters. The TE₁₀ cutoff frequency is the lowest frequency that can propagate in the waveguide. In practice, waveguides are used well above their cutoff frequency to avoid excessive dispersion and loss.

| Band | WR Designation | Inner Width (mm) | Inner Height (mm) | TE₁₀ Cutoff (GHz) | Recommended Freq. Range (GHz) | Typical EPR Use |
|------|---------------|-----------------|------------------|-------------------|-------------------------------|-----------------|
| L    | WR-650        | 165.1           | 82.6             | 0.91              | 1.12 – 1.70                   | In-vivo / low-field EPR |
| S    | WR-284        | 72.14           | 34.04            | 2.08              | 2.60 – 3.95                   | S-Band EPR (~3 GHz) |
| C    | WR-187        | 47.55           | 22.15            | 3.15              | 3.95 – 5.85                   | C-Band |
| X    | WR-90         | 22.86           | 10.16            | 6.56              | 8.20 – 12.40                  | X-Band EPR (~9–10 GHz) |
| Ku   | WR-62         | 15.80           | 7.90             | 9.49              | 12.40 – 18.00                 | Ku-Band |
| K    | WR-42         | 10.67           | 4.32             | 14.05             | 18.00 – 26.50                 | K-Band |
| Ka   | WR-28         | 7.11            | 3.56             | 21.10             | 26.50 – 40.00                 | Q-Band EPR (~34–36 GHz) |
| Q    | WR-22         | 5.69            | 2.84             | 26.35             | 33.00 – 50.00                 | Q-Band (alternative) |
| V    | WR-15         | 3.76            | 1.88             | 39.90             | 50.00 – 75.00                 | V-Band |
| W    | WR-10         | 2.54            | 1.27             | 59.01             | 75.00 – 110.0                 | W-Band EPR (~94 GHz) |
| D    | WR-6          | 1.65            | 0.83             | 90.85             | 110.0 – 170.0                 | High-field EPR (~130 GHz) |

## Notes on Waveguide Loss

Waveguide attenuation increases with frequency. For precise loss values, consult the waveguide manufacturer's datasheet for the specific material (typically brass, aluminum, or copper) and surface finish. At Q-Band (WR-28), typical attenuation is on the order of 0.5–1 dB/m for standard brass waveguide. At W-Band (WR-10), attenuation is significantly higher, often 3–5 dB/m, making it important to minimize the total waveguide run length in W-Band EPR systems.

## Connector Standards

| Band | Common Connector Type |
|------|-----------------------|
| X-Band | SMA (f ≤ 18 GHz), 3.5 mm, 2.92 mm (K-connector) |
| Q-Band | 2.92 mm (K-connector), WR-28 flange |
| W-Band | WR-10 flange, 1.0 mm coaxial |
