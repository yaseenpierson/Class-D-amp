# Class D amplifier image trial

Source: ../Class-D-Audio-Amplifier-Schematic.png
Run: LTspice.exe -b class_d_image_trial.cir

This is a functional approximation, not an exact component-level reproduction.
555 oscillator, LM358 comparator and IR2110 gate driver use behavioral models.
MOSFETs use the explicitly labeled PowerApprox model, not a vendor IRF640 model.
The input resistors, offset pot and inverter are represented by equivalent control signals.
Regulators are represented by ideal 5 V and 12 V supplies.
Actual LM358 speed, propagation delays, regulator headroom, reverse recovery,
bootstrap limits, thermal performance and distortion require exact device models.

Assumptions: 24 V bus, 8 ohm load, 1 kHz audio at 0.6 V peak, offset 2.5 V.
Missing bootstrap values chosen as 100 nF and 10 uF.
Carrier is a triangle at 327.885 kHz, estimated from 2.2 kohm and 1 nF;
the real 555 capacitor waveform is curved. Gate timing is approximated with
30 ns RC filtering and complementary thresholds. LC uses image values 26 uH
and 1 uF; winding resistance assumed 0.05 ohm.

Results measured by LTspice over 8-12 ms:
Output DC: 11.3570 V
Output total RMS including DC: 12.8160 V
1 kHz fundamental: 8.39797 V peak, 4.40787 W in 8 ohms
Total load dissipation including DC: 20.5314 W
Output extrema: 2.9050 V to 19.8695 V
These are simulated values, not physical measurements.

The pictured single half bridge drives the load with substantial DC.
A real speaker should not be connected directly as drawn; the output needs
an appropriate DC-blocking arrangement or a different output topology.

Open class_d_image_trial.raw; plot V(out) for filtered output,
V(vs) for switching, V(carrier)/V(mod) for PWM comparison.
