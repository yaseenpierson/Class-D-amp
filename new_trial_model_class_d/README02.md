# Audio Amplifier Simulation — 4 Ω Speaker Load

## Simulation Overview

Simulated a **4 Ω, 10 W speaker** as a resistive load in LTspice. The circuit was evaluated using a **24 V supply** and a **1 kHz input signal at 1.2 Vpp**.

## Simulation Results

| Parameter | Simulated Result |
|---|---:|
| Average supply current | 1.72 A |
| Peak instantaneous supply current | 6.78 A |
| Output voltage (peak-to-peak) | 16.58 Vpp |
| Average useful audio power | 8.42 W |
| Voltage gain | 13.68 V/V (22.72 dB) |
| Useful audio efficiency | 20.46% |
| Total load dissipation, including DC | 39.05 W |

![Project Preview](images/project.png)
![Alternative text](path/to/image.png)

## Critical Finding: Excessive DC Offset

The simulated output has a **DC offset of 11.07 V**, which causes approximately **30.63 W of additional heating** in the 4 Ω load.

The total load dissipation is therefore:

- Useful audio power: **8.42 W**
- DC-related heating: **30.63 W**
- Total dissipation: **39.05 W**

This exceeds the speaker's **10 W power rating**. The circuit should not be connected directly to a real speaker in this condition.

**A suitable DC-blocking stage or amplifier output redesign is required** before connecting the speaker. A coupling capacitor must be appropriately sized for the load and intended low-frequency response; it should not be treated as a complete fix without checking the amplifier topology and output conditions.

## Efficiency Interpretation

The useful audio efficiency is approximately **20.46%**. The approximately **94.86% total load-power ratio** includes unwanted DC power and therefore does not represent useful audio efficiency.

These efficiency figures are estimates based on the simplified simulation models. Controller, regulator, and other implementation losses may be incomplete.

## Conclusion

The simulation demonstrates that acceptable AC output power does not necessarily imply safe speaker operation. The large DC offset dominates load heating and must be addressed before practical use.