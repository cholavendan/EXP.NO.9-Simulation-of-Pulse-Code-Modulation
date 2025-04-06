# EXP.NO.9-Simulation-of-Pulse-Code-Modulation
9.Simulation of PCM

# AIM
To simulate the Pulse Code Modulation using python.

# SOFTWARE REQUIRED
google colab

# ALGORITHMS
Initialize the sampling rate,frequency,duration and quantization level

Create a Time Vector t using linesapce

Generate sampling rate duration points

Generate the analog message signal using a sine wave

Generate a clock signal, used for sampling

Calculate quantization_step and quantize message signal

Convert quantized_signal to a digital representation

Display the plots.
# PROGRAM
import numpy as np

sampling_rate = 5000

frequency = 50

duration = 0.1

quantization_levels = 16

t = np.linspace(0, duration, int(sampling_rate * duration), endpoint=False)

message_signal = np.sin(2 * np.pi * frequency * t)

clock_signal = np.sign(np.sin(2 * np.pi * 200 * t))

quantization_step = (max(message_signal) - min(message_signal)) / quantization_levels

quantized_signal = np.round(message_signal / quantization_step) * quantization_step

pcm_signal = (quantized_signal - min(quantized_signal)) / quantization_step

pcm_signal = pcm_signal.astype(int)

plt.figure(figsize=(12, 10))

plt.subplot(4, 1, 1)

plt.plot(t, message_signal, label="Message Signal (Analog)", color='blue')

plt.title("Message Signal (Analog)")

plt.xlabel("Time [s]")

plt.ylabel("Amplitude")

plt.grid(True)

plt.subplot(4, 1, 2)

plt.plot(t, clock_signal, label="Clock Signal (Increased Frequency)", color='green')

plt.title("Clock Signal (Increased Frequency)")

plt.xlabel("Time [s]")

plt.ylabel("Amplitude")

plt.grid(True)

plt.subplot(4, 1, 3)

plt.step(t, quantized_signal, label="PCM Modulated Signal", color='red')

plt.title("PCM Modulated Signal (Quantized)")

plt.xlabel("Time [s]")

plt.ylabel("Amplitude")

plt.grid(True)

plt.subplot(4, 1, 4)

plt.plot(t, quantized_signal, label="Signal Demodulation", color='purple', linestyle='--')

plt.title("Signal Without Demodulation")

plt.xlabel("Time [s]")

plt.ylabel("Amplitude")

plt.grid(True)

plt.tight_layout()

plt.show()

# OUTPUT

![PCM](https://github.com/user-attachments/assets/09bf2b1d-1037-440d-9920-5f30a9e6243f)

 
# RESULT / CONCLUSIONS
Hence Pulse Code Modulation verified using python.
