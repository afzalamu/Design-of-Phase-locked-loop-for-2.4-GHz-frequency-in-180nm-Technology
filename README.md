# 📡 Design of Phase-Locked Loop (PLL) for 2.4 GHz Frequency in 180nm CMOS Technology
![image](https://github.com/user-attachments/assets/f563299a-dc67-49ca-a251-5bdec448b083)

A comprehensive transistor-level design and simulation of a low-power **Phase-Locked Loop (PLL)** operating at **2.4 GHz**, implemented using **180nm CMOS technology** and verified via **LTspice**. The project aims at building a frequency synthesizer suitable for **ISM band** applications such as **Wi-Fi**, **Bluetooth**, and **ZigBee** transceivers.

---

## 📘 Abstract

This project details the design and simulation of a fully integrated **Phase-Locked Loop (PLL)** that synthesizes a 2.4 GHz output from a 100 MHz reference using a divide-by-24 feedback loop. All sub-circuits including the **LC-based VCO**, **Phase Frequency Detector (PFD)**, **Charge Pump**, **Loop Filter**, and **Frequency Divider** are implemented at the transistor level using the 180nm technology node. The PLL is optimized for **low power consumption (6.36 mW)** and demonstrates stable locking characteristics with a control voltage of ~0.5 V.

---

## 🔧 Technologies Used

- CMOS 180nm Process Technology  
- LTspice for transistor-level simulation  
---

## 📐 PLL Architecture Overview

The PLL is composed of the following blocks:

1. **Phase Frequency Detector (PFD)**: Detects phase and frequency differences between reference and feedback signals using edge-triggered logic.  
2. **Charge Pump (CP)**: Converts digital UP/DN pulses from the PFD into current pulses.  
3. **Loop Filter (LF)**: Smooths the current from CP into a control voltage (Vctrl) using a 2nd order passive RC filter.  
4. **Voltage-Controlled Oscillator (VCO)**: LC-based VCO using cross-coupled NMOS for negative resistance and MOS varactors for tuning.  
5. **Frequency Divider**: MOD-24 divider using cascaded MOD-6 and MOD-4 Johnson counters built with TSPC flip-flops.

---

## 📈 Performance Metrics

| Parameter                  | Value         |
|---------------------------|---------------|
| Technology Node           | 180nm CMOS    |
| Supply Voltage (VDD)      | 1.5 V         |
| Reference Frequency       | 100 MHz       |
| Output Frequency          | 2.4 GHz       |
| Divider Ratio             | 24            |
| Locking Time              | ~12 µs        |
| Control Voltage (Vctrl)   | ~0.5 V        |
| VCO Gain (Kvco)           | 177 MHz/V     |
| Control Voltage Ripple    | ~20 mV        |
| Power Dissipation         | 6.36 mW       |

---


## 🧪 Schematic and Simulation Results

### 🔸 PLL Block Diagram  
![image](https://github.com/user-attachments/assets/f02c6548-e348-4efe-9fbe-d9814df79bdc)


### 🔸DESIGN OF NMOS BASED LC VCO 
- Schematic
![image](https://github.com/user-attachments/assets/3d3ce4d4-bd84-4402-92d0-251004325fa6)
- Transient Analysis
![image](https://github.com/user-attachments/assets/ee31f7a8-3878-4623-b0d5-f5851adf54ec)
![image](https://github.com/user-attachments/assets/f954f7a5-6e34-4095-ab12-39b6d6fdbbfb)

- Obtaining the Gain of the VCO
![image](https://github.com/user-attachments/assets/23335035-66a5-4714-a3cd-e6df3041811c)
- Conversion of the Differential Output from VCO to Digital Clock
- Schematic
![image](https://github.com/user-attachments/assets/72b1eb95-bf0b-468f-b4c3-f24b23e022b4)
- Transient Analyis
![image](https://github.com/user-attachments/assets/e4b0d00e-2b5b-44bc-b7f5-b1221896d132)


### 🔸 DESIGN OF FREQUENCY DIVIDER 
- Transistor level Implementation of TSPC D-Flip Flop
![image](https://github.com/user-attachments/assets/a191cb42-ce97-4608-94f6-2bbffc146452)
- Transient Analysis of DFF
![image](https://github.com/user-attachments/assets/df87f9f0-9ff1-4ca2-b51c-f3904644b004)
- Schematic of Frequency Divider (MOD 24)
![image](https://github.com/user-attachments/assets/c75d0382-e5a7-475a-ae87-ba2add9f73b5)
- Transient Analysis
![image](https://github.com/user-attachments/assets/58553ae1-894c-47e6-8c4f-47e7f2f09bb0)

### 🔸 DESIGN OF PHASE FREQUENCY DETECTOR (NAND GATES BASED PFD)
- Schematic
![image](https://github.com/user-attachments/assets/e9e2edf6-5d48-4f1f-b47b-f0e2226b8c59)
- Transient Analysis
When there is a Phase difference between Fref and Fdiv :
![image](https://github.com/user-attachments/assets/345c4768-924f-4ab9-aed8-f4d76d8d23b9)
When there is a frequnecy difference between Fref and Fdiv:
![image](https://github.com/user-attachments/assets/680ecaa5-8c24-40c4-898a-cd9af60c514f)



---

## 🧠 Design Highlights

### ✅ LC VCO
- LC Tank: 1 nH inductor and ~4.3 pF MOS varactor
- Cross-coupled NMOS pair for negative resistance generation
- Center frequency at 2.4 GHz with Kvco = 177 MHz/V

### ✅ Frequency Divider
- MOD-6 × MOD-4 Johnson counter configuration = MOD-24
- Built using TSPC logic-based D flip-flops for high-speed operation
- Final output: 100 MHz digital signal from 2.4 GHz input

### ✅ PFD & Charge Pump
- NAND-based topology for detecting both phase and frequency differences
- 100 µA charge pump current
- 2nd-order passive loop filter:  
  - Rs = 15 kΩ  
  - Cs = 18 pF  
  - Cp = 1 pF  
  - Bandwidth ≈ 1.76 MHz

---

## 🔭 Future Work

- **Post-layout simulation** with parasitic extraction in Cadence  
- **Jitter optimization** through better CP matching and noise filtering  
- **Clock injection techniques** to enhance locking speed  
- **Power minimization** via bias optimization and advanced CMOS scaling  

---

## 👨‍🎓 Contributors

| Name                        | Roll No.    |
|-----------------------------|-------------|
| Afzal Malik                | 21ELB173    |
| Mohammed Musayyeb Sherwani | 21ELB283    |

**Supervisor:** Prof. Naushad Alam  
Department of Electronics Engineering  
Zakir Husain College of Engineering & Technology  
**Aligarh Muslim University**

---

## 📚 References

1. B. Razavi, *Design of Analog CMOS Integrated Circuits*, McGraw-Hill  
2. Hokrani et al., “PLL Design in 180nm Technology,” IEEE I2CT, 2018  
3. Hamel & Norris, “LC Tank VCO Tutorial,” University of Waterloo  
4. IEEE RFIT 2021: “2.4 GHz Wide-tuning VCO using Switchable IMOS Varactor”  

---

## 📜 License

© 2025 Aligarh Muslim University — All rights reserved.

---

