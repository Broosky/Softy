# 💡 Softy

Softy is a project I designed and built to enhance my home stereo system by integrating a 12V supercapacitor for improved transient power response.

## 🔹 Background

In the late 2000s (around 2008), I ran a car head unit (40W × 4) along with a 600W sub amplifier as my primary home stereo. The system was powered by an ATX power supply, with all 12V rails and grounds tied together. The remote turn-on line was connected to 12V, so the system powered up automatically with the supply.

At the time, I purchased a 12V 1.6F supercapacitor to help support high current transients. However, large capacitors initially appear as a near short circuit. The inrush current caused the ATX supply’s protection circuitry to trip, preventing startup. I ultimately abandoned the capacitor and ran the system directly from the ATX supply.

## 🔹 Today

Nearly 20 years later, I still use the same ATX supply (rated for up to 25A on the 12V rail) which has proven more than capable for my listening levels. The head unit has since been removed, and the main amplifier now drives the left and right channels, with a bridged output for the subwoofer.

I revisited the idea of adding the supercapacitor to improve transient response and solved the original startup issue.

## 🔹 The Solution

I designed and built a supercapacitor soft-start circuit to manage inrush current.

- The capacitor charges through an 1156 automotive bulb, which acts as a simple, dynamic current limiter (and is more forgiving than a fixed power resistor).
- An LM393 monitors the capacitor voltage.
- When the capacitor reaches approximately 10V, the circuit latches a power relay.
- The relay then bypasses the bulb and connects the capacitor directly to the supply rails and amplifier.
- At the same time, the remote connection is enabled powering on the amp.

The result is controlled startup, protection of the ATX supply, and improved transient current delivery. The 10 AWG wiring is conservatively rated for ~40A continuous, though the system is fused well below that due to primary steel interconnects and modest listening levels. I used both comparators on the LM393 to isolate states, but a single comparator with carefully chosen resistor values and additional transistors could achieve the same LED and load control.

> If you found this project useful, interesting, or worth keeping an eye on, consider giving it a ⭐️.
> It helps others discover the project and motivates me to keep building and sharing more.

## 🔹 Rev 1 Schematic

![Rev 1](<Schematics/Rev 1.png>)

## 🔹 Rev 1

- Tracking versions.

## 🔹 Ideas & Upcoming Changes

- Copper connecting hardware on the faceplate.
