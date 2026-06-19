# Day 4 - CMOS Inverter Characteristics and Noise Margin Analysis

## Objectives

* Understand the static behavior of a CMOS inverter.
* Study the Voltage Transfer Characteristic (VTC).
* Analyze CMOS inverter operating regions.
* Learn the concept of Noise Margin.
* Evaluate CMOS inverter robustness.

---

# 1. CMOS Inverter

A CMOS inverter is the fundamental building block of digital integrated circuits. It consists of:

* PMOS transistor connected to VDD
* NMOS transistor connected to Ground
* Common gate as input
* Common drain as output

### Characteristics

* High noise immunity
* Low static power consumption
* Full logic swing
* High switching speed

---

# 2. Static Behavior of CMOS Inverter

The static behavior is obtained by analyzing the output voltage (VOUT) for different input voltages (VIN).

The relationship between VIN and VOUT is known as the **Voltage Transfer Characteristic (VTC)**.

The inverter has two stable operating states:

* VIN = 0 → VOUT = VDD
* VIN = VDD → VOUT = 0

---

# 3. Voltage Transfer Characteristic (VTC)

The VTC curve shows how the output changes as the input voltage increases.

Important points on the VTC:

* VOH – Output High Voltage
* VOL – Output Low Voltage
* VIH – Minimum High Input Voltage
* VIL – Maximum Low Input Voltage
* VM – Switching Threshold

The transition region has a very high voltage gain.

---

# 4. CMOS Inverter Operating Regions

During switching, both transistors operate in different regions.

### Region 1

* VIN = 0
* NMOS : Cutoff
* PMOS : Linear
* VOUT = VDD

---

### Region 2

* NMOS : Saturation
* PMOS : Linear

Output voltage starts decreasing.

---

### Region 3

* NMOS : Saturation
* PMOS : Saturation

Both transistors conduct simultaneously.

Maximum voltage gain occurs near this region.

---

### Region 4

* NMOS : Linear
* PMOS : Saturation

Output approaches logic LOW.

---

### Region 5

* VIN = VDD
* NMOS : Linear
* PMOS : Cutoff
* VOUT = 0

---

# 5. Switching Threshold (VM)

The switching threshold is the point where:

```text
VIN = VOUT
```

At this point,

```text
ID(NMOS) = ID(PMOS)
```

For a symmetrical inverter,

```text
VM ≈ VDD / 2
```

The switching threshold depends on:

* Threshold voltage
* Mobility ratio
* W/L ratio
* Supply voltage

---

# 6. Noise Margin

Noise Margin indicates the maximum noise voltage that can be tolerated without affecting the logic state.

It measures the robustness of a digital circuit.

### Noise Margin High

```text
NMH = VOH − VIH
```

### Noise Margin Low

```text
NML = VIL − VOL
```

Where

* VOH = Output High Voltage
* VOL = Output Low Voltage
* VIH = Minimum High Input Voltage
* VIL = Maximum Low Input Voltage

Larger noise margins indicate better noise immunity.

---

# 7. CMOS Robustness Evaluation

The robustness of a CMOS inverter depends on:

* High voltage gain
* Large Noise Margin
* Proper transistor sizing
* Balanced PMOS/NMOS strength
* Stable switching threshold

A robust inverter provides:

* Reliable logic levels
* Better immunity to noise
* Improved process tolerance
* Stable circuit operation

---

# 8. Static Power Dissipation

In the steady state,

* One transistor is ON
* One transistor is OFF

Therefore,

```text
Static Power ≈ 0
```

Only leakage current contributes to power dissipation.

---

# 9. Voltage Gain

Voltage gain is defined as

```text
Av = − dVOUT / dVIN
```

Near the switching threshold,

```text
|Av| > 1
```

Higher gain leads to:

* Faster switching
* Better Noise Margin
* Improved signal restoration

---

## LAB 
![pic]()

# 10. Key Observations

* CMOS inverter has two stable logic states.
* Transition occurs over a narrow input range.
* High voltage gain improves switching performance.
* Large noise margins increase circuit reliability.
* Static power consumption is almost zero.

---

