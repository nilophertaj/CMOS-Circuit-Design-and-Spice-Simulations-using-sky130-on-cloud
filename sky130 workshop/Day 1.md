# Day 1 – Introduction to CMOS, MOSFET Operation and NGSpice

## Objectives

* Understand the basics of CMOS technology.
* Learn the structure and operation of an NMOS transistor.
* Study threshold voltage and body effect.
* Understand MOSFET operating regions.
* Introduction to NGSpice and SPICE circuit description.
* Perform the first SPICE simulation (Lab).

---

# 1. CMOS Buffer Characterization

The delay of a CMOS gate depends mainly on:

* Input Slew
* Output Load Capacitance

Each standard cell is characterized using **SPICE simulations**, producing lookup tables used during timing analysis.

### Key Points

* Delay is obtained from characterization tables.
* Current and threshold voltage are extracted using SPICE.
* Transistor performance is optimized by tuning the **W/L ratio**.

---

# 2. NMOS Transistor Structure

An NMOS is a **four-terminal device** consisting of:

* Gate (G)
* Drain (D)
* Source (S)
* Body (B)

### Structure

* P-type substrate
* Two heavily doped N+ regions
* Thin SiO₂ oxide layer
* Polysilicon/Metal gate

![nmos](https://github.com/nilophertaj/CMOS-Circuit-Design-and-Spice-Simulations-using-sky130-on-cloud/blob/a1b2e939d5d850a9c5db664442cf5e50ae45a386/github/first%20sim/nmos.jpg)
---

# 3. Threshold Voltage (VTH)

Threshold voltage is the minimum gate voltage required to form an inversion layer between source and drain.

Initially,

* VGS = 0 V
* Source and Body are connected together.
* Source-body and Drain-body junctions remain reverse biased.

As VGS increases,

1. Accumulation
2. Depletion
3. Inversion
4. Strong inversion

At strong inversion,

```
VGS = VTH
```

A conductive channel is formed between source and drain.

---

# 4. Body Effect

Increasing the source-to-body voltage (**VSB**) increases the threshold voltage.
Body Effect Coefficient:
γ = √(2qεsiNA) / Cox

Threshold voltage equation:
```
Vₜ = Vₜ₀ + γ ( √(2ϕF + VSB) − √(2ϕF) )
```

Where

* Vₜ = Threshold Voltage
* Vₜ₀ = Threshold Voltage at VSB = 0
* γ = Body effect coefficient
* ϕF = Fermi potential
* VSB = Source-to-Body Voltage

![body](https://github.com/nilophertaj/CMOS-Circuit-Design-and-Spice-Simulations-using-sky130-on-cloud/blob/a1b2e939d5d850a9c5db664442cf5e50ae45a386/github/first%20sim/body%20effect.jpg)

### Observation

* Higher VSB
* Larger depletion region
* Higher threshold voltage

---

# 5. Resistive (Linear) Region

The MOSFET behaves like a voltage-controlled resistor.

### Conditions

```
VGS > VTH

VDS < VGS − VTH
```
![line](https://github.com/nilophertaj/CMOS-Circuit-Design-and-Spice-Simulations-using-sky130-on-cloud/blob/a1b2e939d5d850a9c5db664442cf5e50ae45a386/github/first%20sim/lsat%20reg.jpg)

### Characteristics

* Channel exists from source to drain.
* Current increases almost linearly with VDS.
* Used for switching applications.

---

# 6. Drift Current Theory

Electrons move due to the electric field created by the drain voltage.

This movement of charge carriers is called **Drift Current**.

Current increases with

* Higher electric field
* Larger channel width
* Higher carrier mobility

---

# 7. Drain Current Model (Linear Region)

The drain current is
```
ID = μn Cox (W/L) [ (VGS − VTH)VDS − (VDS²/2) ]
```
Where

* μₙ = Electron mobility
* Cox = Oxide capacitance
* W = Channel width
* L = Channel length

---

# 8. SPICE Conclusion for Resistive Operation

SPICE simulations verify that:

* Drain current increases almost linearly with VDS.
* NMOS behaves like a resistor in the linear region.
* Device resistance decreases as VGS increases.

---

# 9. Pinch-off Condition

Pinch-off occurs when

```
VDS = VGS − VTH
```
![pinch](https://github.com/nilophertaj/CMOS-Circuit-Design-and-Spice-Simulations-using-sky130-on-cloud/blob/a1b2e939d5d850a9c5db664442cf5e50ae45a386/github/first%20sim/pinch%20off.jpg)

At this point,

* Channel disappears near the drain.
* Current no longer increases linearly.
* Device enters saturation.
* 
---

# 10. Saturation Region

### Conditions

```
VGS > VTH

VDS ≥ VGS − VTH
```

### Characteristics

* Pinch-off occurs near the drain.
* Current becomes nearly constant.
* Current is mainly controlled by VGS.

---

# 11. Drain Current Model (Saturation Region)

Ignoring channel-length modulation,
```
ID = (1/2) μn Cox (W/L) (VGS − VTH)²
```

This is the square-law equation of an NMOS transistor.

---

# 12. Introduction to NGSpice

NGSpice is an open-source circuit simulator used to analyze electronic circuits.

It supports

* DC Analysis
* AC Analysis
* Transient Analysis
* Parameter Sweeps

It is widely used for transistor-level CMOS circuit simulations.

---

# 13. SPICE Circuit Description

A SPICE netlist consists of

* Circuit title
* Components
* Voltage sources
* Simulation commands
* End statement

Example:

```spice
* Inverter Example

VDD vdd 0 1.8
VIN in 0 PULSE(0 1.8 0 1n 1n 5n 10n)

.include sky130.lib.spice

.tran 0.1n 20n

.end
```

---

# 14. Technology Parameters

Technology libraries define transistor characteristics such as

* Threshold voltage
* Oxide thickness
* Channel length
* Mobility
* Capacitance
* Process corners

These parameters are loaded through the SKY130 technology files.

---

# 15. First SPICE Simulation (Lab)

In this session, the first transistor-level simulation is performed using NGSpice.
![pic](https://github.com/nilophertaj/CMOS-Circuit-Design-and-Spice-Simulations-using-sky130-on-cloud/blob/e3849c1fd4ed4fbe19dc3ba9ffab222ddf4c04cc/github/first%20spice/1st%20sim1.png)

![pic](https://github.com/nilophertaj/CMOS-Circuit-Design-and-Spice-Simulations-using-sky130-on-cloud/blob/e3849c1fd4ed4fbe19dc3ba9ffab222ddf4c04cc/github/first%20spice/1st%20sim2.png)

```
vim day1_nfet_idvds_L2_W5.spice
```
![pic](https://github.com/nilophertaj/CMOS-Circuit-Design-and-Spice-Simulations-using-sky130-on-cloud/blob/e3849c1fd4ed4fbe19dc3ba9ffab222ddf4c04cc/github/first%20spice/1st%20sim3.png)

![pic](https://github.com/nilophertaj/CMOS-Circuit-Design-and-Spice-Simulations-using-sky130-on-cloud/blob/e3849c1fd4ed4fbe19dc3ba9ffab222ddf4c04cc/github/first%20spice/day1.png)

According to the n type characterization, the corners can be divided as
tt- typical 
ss- slow slow 
sf- slow fast

In the netlist description, the transistor level syntax is:
drain gate source bulk

```
ngspice day1_nfet_idvds_L2_W5.spice
plot -vdd#branch
```

![pic](https://github.com/nilophertaj/CMOS-Circuit-Design-and-Spice-Simulations-using-sky130-on-cloud/blob/e3849c1fd4ed4fbe19dc3ba9ffab222ddf4c04cc/github/first%20spice/idvds.png)

---

# Summary

* Learned CMOS gate characterization.
* Studied NMOS structure and operation.
* Understood threshold voltage and body effect.
* Explored linear and saturation regions.
* Derived drain current equations.
* Learned pinch-off condition.
* Introduced NGSpice and SPICE netlists.
* Performed the first SPICE simulation.

---
