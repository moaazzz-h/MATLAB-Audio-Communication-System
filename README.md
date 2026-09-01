# MATLAB Audio Communication System

## Description

This project simulates a basic audio communication system using MATLAB. The system demonstrates how an audio signal is affected as it passes through a communication channel, encounters additive noise, and is finally processed using a low-pass filter.

The project also analyzes the signal in both the **time domain** and **frequency domain** at different stages of the communication process.

## System Flow

```text
Audio Signal
     |
     v
Transmitter
     |
     v
Communication Channel
     |
     v
Additive Noise
     |
     v
Low-Pass Filter
     |
     v
Filtered Audio Signal
```

## Main Stages

### 1. Audio Input & Transmitter

The input audio file is loaded using MATLAB's `audioread()` function and converted from stereo to mono.

The original audio signal is then analyzed in:

* Time Domain
* Frequency Domain using FFT

### 2. Communication Channel

Different channel impulse responses can be selected to simulate different channel characteristics.

The audio signal is passed through the selected channel using convolution:

```matlab
y = conv(x,h);
```

The resulting signal is analyzed again in both the time and frequency domains.

### 3. Noise

Additive Gaussian noise is introduced into the received signal.

The noise level is controlled using a user-defined standard deviation:

```matlab
sigma = input('Enter sigma value: ');
NOISE = sigma * randn(length(y),1);
y_n = y + NOISE;
```

This allows the effect of different noise levels on the transmitted audio signal to be investigated.

### 4. Low-Pass Filter

A frequency-domain low-pass filter is applied to reduce high-frequency noise.

The current cutoff frequency is:

```matlab
fc = 3400;
```

The filtered signal is reconstructed back into the time domain using the inverse FFT.

## Signal Analysis

At different stages of the system, the project plots:

* Original audio signal
* Signal after passing through the channel
* Signal after adding noise
* Signal after filtering

For each stage, both the **time-domain waveform** and **frequency spectrum** are displayed.

## Technologies Used

* MATLAB
* Digital Signal Processing
* Fast Fourier Transform (FFT)
* Inverse FFT
* Convolution
* Gaussian Noise
* Frequency-Domain Filtering
* Audio Signal Processing

## Project Structure

```text
MATLAB-Audio-Communication-System/
│
├── FIRE.mp3
├── Audio_Communication_System.m
└── README.md
```

## How to Run

1. Clone or download the repository.
2. Open the project in MATLAB.
3. Make sure `FIRE.mp3` is located in the same directory as the MATLAB script.
4. Run the MATLAB script.
5. Enter the desired noise standard deviation when prompted.
6. Observe the generated plots for each stage of the communication system.

## Output

The project generates plots showing the audio signal and its frequency spectrum at the different stages:

1. Original Audio
2. After Channel
3. After Adding Noise
4. After Low-Pass Filtering

## Learning Objectives

This project provides practical understanding of:

* Audio signal representation
* Time-domain and frequency-domain analysis
* FFT-based signal analysis
* Communication channel modeling
* Additive noise effects
* Digital filtering
* The effect of filtering on a noisy communication signal

## Author

**Moaaz**
