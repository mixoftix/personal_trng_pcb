# Personal TRNG — PCB Hardware (v1.0)

**Single-Sided & Double-Sided PCB Designs for the Personal True Random Number Generator (TRNG)**

## Overview

`personal_trng_pcb` provides the hardware layouts and Bills of Materials (BOM) for the **Personal TRNG** platform. Designed around easy-to-source through-hole components (with a single-sided edition tailored for home etching and DIY assembly), this board pairs an **ATmega328 / ATmega328P** microcontroller with a multi-crystal Pierce oscillator entropy source (`74HC04` + four independent `8 MHz` crystals) and dual D flip-flop jitter capture (`74HC74`).

### Hardware Editions Included (`src/`)

* **Single-Sided Edition (`personal_trng_single_sided`):** Optimized for DIY home fabrication, single-layer milling, or toner-transfer etching using a standard USB-C breakout module and solderable jumper wires.
* **Double-Sided Edition (`personal_trng_double_sided`):** Compact factory-ready two-layer layout featuring an onboard 6-pin SMD USB-C power receptacle (`5.1 kΩ` CC pull-down resistors) and direct trace routing.

---

## Key Hardware Architecture

* **Microcontroller:** ATmega328 / ATmega328P (DIP-28 Narrow, internal `8 MHz` RC clock)
* **Entropy Source ("Shutter System"):** 4x independent `8 MHz` crystals driven by a `74HC04` hex inverter with `10 MΩ` feedback resistors
* **Jitter Capture:** `74HC74` dual D flip-flop feeding hardware external interrupts (`INT0` / `INT1`)
* **User Interface:** 0.56" Common-Anode 7-segment display, mode selection headers, and a 6-pin DPDT momentary push-button switch
* **Serial Output:** UART TX/RX (`115200` baud)

---

## Bill of Materials (BOM)

Full component lists in both Markdown (`.md`) and plain-text (`.txt`) formats are located inside each edition's `docs/` folder under `src/`:

* **Single-Sided BOM:** `src/personal_trng_single_sided/docs/personal_trng_single_sided_1_0_bom.md`
* **Double-Sided BOM:** `src/personal_trng_double_sided/docs/`

---

## Firmware & Licensing

* **Official Firmware (v1.19):** [mixoftix/personal_trng_firmware](https://github.com/mixoftix/personal_trng_firmware)
* **License:** This firmware is distributed under an Audit-Only license (see LICENSE for full terms). Source code inspection is permitted for security auditing; however, commercial or operational deployment requires a valid firmware license.
