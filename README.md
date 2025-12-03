# DSBSC-using-python
## Aim:

To generate and analyze a Double Sideband Suppressed Carrier (DSB-SC) modulated signal using Python and determine its amplitude, time period, and frequency from the waveform.

## EQUIPMENTS Needed:

•	Computer with i3 Processor
•	SCI LAB

## THEORY:
In DSB-SC modulation, the carrier is suppressed, and only the two sidebands carry the information.

The mathematical representation is:
s(t) = Am * Ac * cos(2πfmt) * cos(2πfct)

Using the trigonometric identity:
cosA * cosB = ½[cos(A−B) + cos(A+B)]

Therefore,
s(t) = (Am * Ac / 2) [cos 2π(fc − fm)t + cos 2π(fc + fm)t]

Thus, the modulated signal contains two sidebands (Upper and Lower) and no carrier component.

## ⚙️ ALGORITHM
1. Start the program.
2. Import the required libraries: `numpy` and `matplotlib`.
3. Define the constants:  
   - Am = 4.6  
   - Ac = 9.2  
   - fm = 354 Hz  
   - fc = 3540 Hz
4. Generate the time vector `t`.
5. Generate the message signal: `x1 = Am * cos(2πfmt)`.
6. Generate the carrier signal: `x2 = Ac * cos(2πfct)`.
7. Multiply both to get the DSB-SC modulated signal: `s = x1 * x2`.
8. Plot the message, carrier, and modulated signals.
9. Measure the time period `T = x2 − x1` and compute `f = 1/T`.
10. Stop the program.

## PROCEDURE:
1. Open **Python / Jupyter Notebook**.
2. Enter the given code and run it.
3. Observe the message, carrier, and DSB-SC waveforms.
4. Measure the time difference between two similar peaks (`x2 − x1`).
5. Calculate frequency using `f = 1/T`.
6. Compare theoretical and practical results.

## PROGRAM:
```
import numpy as np
import matplotlib.pyplot as plt

Am = 4.6
Ac = 9.2
fm = 354
fc = 3540
fs = 10 * fc
t = np.arange(0, 0.01, 1/fs)

x1 = Am * np.cos(2 * np.pi * fm * t)
x2 = Ac * np.cos(2 * np.pi * fc * t)
s = x1 * x2

plt.figure(figsize=(10,6))
plt.subplot(3,1,1)
plt.plot(t, x1)
plt.title('Message Signal')
plt.xlabel('Time (s)')
plt.ylabel('Amplitude')

plt.subplot(3,1,2)
plt.plot(t, x2)
plt.title('Carrier Signal')
plt.xlabel('Time (s)')
plt.ylabel('Amplitude')

plt.subplot(3,1,3)
plt.plot(t, s)
plt.title('DSB-SC Modulated Signal')
plt.xlabel('Time (s)')
plt.ylabel('Amplitude')

plt.tight_layout()
plt.show()
```
## Output Waveform:

<img width="1217" height="727" alt="image" src="https://github.com/user-attachments/assets/e3fc8634-e5a5-4ce3-b369-476f82caa805" />

## Table:

![WhatsApp Image 2025-12-03 at 13 30 08_7154eec3](https://github.com/user-attachments/assets/4e74ce58-b0fc-4a04-877f-3392a02d1ac5)

## Result:
The DSB-SC modulated signal was successfully generated and analyzed using Python.
The practical frequency values closely matched the theoretical ones, verifying the concept of DSB-SC modulation.
