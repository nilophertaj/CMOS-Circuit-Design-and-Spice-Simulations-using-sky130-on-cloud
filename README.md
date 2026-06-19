# CMOS Circuit Design and SPICE Simulations using SKY130 on Cloud

This repository documents my learning journey through the **VLSI System Design (VSD)** Workshop on **CMOS Circuit Design and SPICE Simulations using the SKY130 on Cloud**.

Throughout this workshop, I will be uploading my daily work, notes, simulations, circuit designs, and observations from **Day 1 to Day 5**.

---

# Environment Setup

## Step 1: Launch GitHub Codespace

The VSD workshop provides a pre-configured cloud development environment through **GitHub Codespaces**.

1. Open the official **VSD CMOS Workshop** repository.
2. Click **Code → Codespaces → Create codespace on main**.
3. Wait a few minutes for the environment to finish loading.

![Codespace Launch](https://github.com/nilophertaj/CMOS-Circuit-Design-and-Spice-Simulations-using-sky130-on-cloud/blob/3086731aab82034744b3ebd4a6da076187bff670/github/codespace.png)

---

## Step 2: Verify NGSpice Installation

Once the Codespace is ready, open the **Terminal** and type:

```bash
ngspice
exit
```

If installed correctly, you’ll see the ngspice version banner confirming installation.

![NGSpice Version](https://github.com/nilophertaj/CMOS-Circuit-Design-and-Spice-Simulations-using-sky130-on-cloud/blob/3086731aab82034744b3ebd4a6da076187bff670/github/ngspice1.png
)

---

## Step 3: Open the Linux Desktop (noVNC)

To visualize simulation plots and waveforms graphically:

1. Open the **Ports** tab in VS Code.
2. Locate **Port 6080** under **Forwarded Address**.
3. Click the forwarded URL.
4. Select **`vnc_lite.html`**.

![Ports](https://github.com/nilophertaj/CMOS-Circuit-Design-and-Spice-Simulations-using-sky130-on-cloud/blob/3086731aab82034744b3ebd4a6da076187bff670/github/port.png
)

![vnc\_lite](https://github.com/nilophertaj/CMOS-Circuit-Design-and-Spice-Simulations-using-sky130-on-cloud/blob/3086731aab82034744b3ebd4a6da076187bff670/github/vnc_lite.png)

This opens a Linux desktop directly in your browser.

The Linux desktop allows you to:

* View NGSpice plots
* Analyze voltage and current waveforms
* Run GUI-based EDA tools
* Interact with graphical simulation windows

---

---

# Tools Used

* GitHub Codespaces
* Visual Studio Code
* NGSpice
* SKY130 PDK
* Linux Desktop (noVNC)

---
I would like to express my sincere gratitude to Kunal Ghosh Sir and the VLSI System Design (VSD) team for making this workshop with excellent video quality, well-structured content, and continuous dedication. Their efforts have made learning VLSI concepts practical, engaging, and accessible to aspiring engineers.
