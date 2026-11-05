# Low-Latency Wireless Trigger System

**Custom Electronics Development | Analog Signal Processing | Wireless Communication | PCB Design | 3D Product Design**

## Project Overview

This project involved the development of a custom electronic triggering system designed for precise synchronization between an audio-based starting signal and an athletics photo-finish camera.

The main challenge was to detect an analog audio signal and activate a visual indicator with extremely low latency and minimal timing variation, while supporting both wired and wireless configurations.

The project covered the complete engineering process, from initial requirements analysis and feasibility studies to electronic circuit development, component selection, prototype testing, PCB design, mechanical CAD modeling, and production cost estimation.

**All electronic design, prototype development, testing, and product design work presented here was carried out independently.**

<img width="4648" height="2329" alt="COMBO" src="https://github.com/user-attachments/assets/0b319ee4-7470-4d13-a621-89b353086aba" />

<br>
<br>

## Project Requirements

The main technical requirements included:

- Sub-millisecond trigger latency, with minimal jitter.
- Reliable detection of different audio starting signals.
- Electrical isolation between the audio source and the external electronics.
- Wireless communication suitable for outdoor sporting events.
- High-visibility LED indication for camera synchronization.
- Battery-powered operation for extended sporting events.
- Compact, weather-resistant enclosures.
- Practical mounting, charging, and status indication features.

Three configurations were considered:

**1. Optical Beacon**

A standalone device that detects an audio starting signal and activates a high-power LED, allowing a distant camera to capture the starting event.

<p align="center">
  <img width="650" alt="BEACON INFO" src="https://github.com/user-attachments/assets/ce617b3a-61b2-4e8a-990d-884d4ec76a77" />
</p>

<br>

**2. Wireless Trigger**

A transmitter and receiver system that detects the audio signal and activates a remote LED positioned within the camera's field of view.

<p align="center">
  <img width="650" alt="WIRELESS TRIGGER INFO" src="https://github.com/user-attachments/assets/8e077cb0-110b-4b35-9190-d9e9affa6c4c" />
</p>

<br>

**3. Hybrid System**

A combined configuration integrating the optical beacon and wireless transmission, allowing simultaneous local and remote visual indication.

<p align="center">
  <img width="650" alt="COMBO INFO" src="https://github.com/user-attachments/assets/9e2d3242-bbf5-4dfa-b9f9-56d1b82c09ff" />
</p>

<br>

## Engineering Development

### 1. Requirements Analysis and Feasibility Study

The first stage involved evaluating the technical requirements and identifying the main challenges associated with low-latency audio detection, wireless transmission, electrical isolation, and power management.

Particular attention was given to the trade-offs between transmission speed, reliability, power consumption, and system complexity.

Different electronic approaches and wireless communication technologies were investigated to identify a suitable architecture for the required timing performance.

### 2. Electronic Circuit Development

Custom electronic circuits were designed and experimentally evaluated for analog signal detection, trigger generation, electrical isolation, and LED control.

The development included:

- Analog signal conditioning and detection.
- Low-latency electronic switching.
- Galvanic isolation.
- Wireless transmitter and receiver integration.
- LED driver circuitry.
- Battery-powered system architecture.

Circuit configurations were evaluated experimentally and refined based on oscilloscope measurements.


<p align="center">
  <img width="500" alt="Electronics Prototype" src="https://github.com/user-attachments/assets/cbdc5262-9df3-47b7-8025-cb3753fd0fce" />
</p>

<br>

### 3. Audio Waveform Analysis

One of the main challenges was understanding how different audio waveforms affected trigger response time.

Several starting sounds were investigated using an oscilloscope, revealing significant differences in their initial waveform characteristics.

Signals with sharp initial rising edges produced considerably faster triggering, while signals with gradual amplitude increases or low-amplitude initial regions introduced additional detection delays.

This analysis demonstrated that system performance depends not only on the electronic hardware but also on the characteristics of the input signal.

<table>
  <tr>
    <td width="50%">
      <img width="560" height="311" alt="image" src="https://github.com/user-attachments/assets/53ecbb32-dae7-4032-828c-fc68943e1b70" />
    </td>
    <td width="50%">
      <img width="562" height="314" alt="image" src="https://github.com/user-attachments/assets/dedeb6f0-ef4b-490a-9709-f9d829ba76fe" />
    </td>
  </tr>
</table>

<br>

<table>
  <tr>
    <td width="50%">
      <img width="560" height="311" alt="image" src="https://github.com/user-attachments/assets/87ba6b69-d379-402f-bc9c-97cc0ae83058" />
    </td>
    <td width="50%">
      <img width="560" height="311" alt="image" src="https://github.com/user-attachments/assets/65a417e2-3ea3-429c-8170-9c063d90b9b7" />
    </td>
  </tr>
</table>

<br>

### 4. Latency and Jitter Evaluation

The electronic prototype was evaluated through repeated oscilloscope measurements to characterize trigger latency and timing consistency.

Two configurations were tested: the standalone trigger circuit and the complete wireless triggering system.

| Parameter | Trigger Circuit | Wireless System |
|---|---:|---:|
| Average latency | 97 µs | 217 µs |
| Jitter (standard deviation) | 4 µs | 11 µs |
| Minimum latency | 85 µs | 191 µs |
| Maximum latency | 103 µs | 244 µs |
| Measurements | 39 | 55 |

These prototype measurements demonstrated sub-millisecond response times with low timing variation under the evaluated test conditions. In the oscilloscope measurements below, the yellow trace (A) represents the audio trigger signal, while the blue trace (B) represents the LED activation signal.

<img width="563" height="316" alt="image" src="https://github.com/user-attachments/assets/8d8684b4-40dc-465e-b924-1f84969496a1" />

<br>
<br>

### 5. Signal Optimization

Further experiments demonstrated the importance of input waveform characteristics.

An initial electronic starting sound produced approximately 4.5 ms of latency due to its gradual initial amplitude increase.

After an improved audio waveform was provided for evaluation, the measured latency decreased to approximately **232 µs**, meeting the sub-millisecond timing requirement under the tested conditions.

This result highlighted the importance of analyzing the complete signal chain rather than focusing exclusively on the electronic circuit. In the *Fixed Eshot* audio file, the initial low-amplitude, noisy portion of the waveform was removed, allowing the trigger circuit to detect the first peak more reliably and reducing the latency from approximately 4.5 ms to 232 µs.

**Adjustable Trigger Sensitivity:** The circuit also includes a potentiometer for adjusting the trigger sensitivity, allowing it to accommodate different types of audio signals and waveform characteristics.

<table>
  <tr>
    <td width="50%">
      <img width="671" height="374" alt="image" src="https://github.com/user-attachments/assets/f3f57b40-0c2f-4efd-aa08-2d17af2d8c96" />
    </td>
    <td width="50%">
      <img width="672" height="379" alt="image" src="https://github.com/user-attachments/assets/55039975-0f78-43f7-86d0-8f41da26a29a" />
    </td>
  </tr>
</table>

<br>

The oscilloscope measurement below clearly shows the **232 µs latency** between the onset of the audio signal (A) and the corresponding LED trigger activation (B).

<p align="center">
  <img width="671" height="376" alt="image" src="https://github.com/user-attachments/assets/cc0d743b-6a1f-4b3c-9828-45b6b34d6151" />
</p>

<br>
<br>

### 6. PCB and Electronic Product Design

Following the experimental investigations, PCB layouts and electronic integration concepts were developed for the proposed configurations.

The design process considered component placement, electrical connections, enclosure integration, power distribution, and practical assembly requirements.

<table>
  <tr>
    <td width="50%">
      <img width="937" height="661" alt="Desfoque circuito" src="https://github.com/user-attachments/assets/3701b6b8-88f2-4753-bedf-c996151ec69f" />
    </td>
    <td width="50%">
      <img width="473" height="349" alt="image" src="https://github.com/user-attachments/assets/cf823571-a32b-4df9-9878-a3187c4fd62c" />
    </td>
  </tr>
</table>

<br>
<br>

### 7. Mechanical Design and Enclosure Integration

The mechanical development involved 3D CAD modeling of the device configurations, considering:

- Weather-resistant enclosures.
- Electronic component positioning.
- LED placement and optical visibility.
- External connections and charging access.
- Battery accommodation.
- Status indicators and user controls.
- Tripod mounting and installation requirements.

The CAD models were developed to evaluate the physical arrangement, accessibility, and integration of the electronic components.

<img width="459" height="380" alt="image" src="https://github.com/user-attachments/assets/c708c95e-6da6-4918-871d-d4372bdff264" />

<br>
<br>

### 8. Technical Documentation and Cost Estimation

The project also included preparation of technical documentation and individual cost estimates for the three proposed configurations.

This stage involved evaluating component requirements, manufacturing considerations, assembly work, and the relationship between different product variants.

The work demonstrated the transition from experimental electronic development toward a structured product design proposal.

<br>

## Project Documentation and Confidentiality

This repository presents a selected technical overview of an independently developed project.

To protect the original design and associated commercial interests, complete schematics, PCB manufacturing files, firmware source code, component specifications, and detailed implementation information are not publicly available.

The images and experimental results are provided to demonstrate the engineering methodology, technical development, and practical skills involved in the project.

---

**Developed by Gilberto Coelho | 2026**

Electronics Development | Embedded Systems | Instrumentation | Product Design
