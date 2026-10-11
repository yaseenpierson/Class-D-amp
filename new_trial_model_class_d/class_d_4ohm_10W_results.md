# 4 ohm / 10 W speaker trial

Speaker represented by a 4 ohm resistor. Its 10 W rating is a comparison
limit, not a power clamp. Real speaker impedance varies with frequency.
Original circuit preserved in class_d_image_trial.cir.
Inherited approximations are documented in class_d_image_trial_README.md.

Conditions: 24 V bus, 1 kHz sine input, 0.6 V peak (1.2 Vpp).
LTspice transient measurements: 8-12 ms after startup.

24 V supply current: 1.71525 A average; 6.77655 A instantaneous peak.
Modeled input power: 41.16671 W including ideal auxiliary supplies.
Output: 16.57743 Vpp including switching ripple, 11.06827 V DC.
1 kHz fundamental: 16.41877 Vpp, 8.42425 W average audio power.
Fundamental instantaneous peak power, calculated: 16.84849 W.
Voltage gain: 13.68230 V/V, 22.72319 dB relative to audio input.
Speaker total RMS current: 3.12459 A; DC current: 2.76707 A.
Total speaker power: 39.05223 W, including 30.62663 W from DC.
Useful audio efficiency: 100 * audio power / modeled input power = 20.46374%.
Total load power / modeled input power = 94.86363%, including DC heating.

The directly connected speaker exceeds its 10 W rating by about 3.9 times.
DC blocking or another output topology is required before using a real speaker.
No physical measurements were supplied. These are simplified simulated results.
Efficiency is not a hardware rating: behavioral controller and gate sources do
not model their own supply draw, and regulator/device losses are incomplete.
