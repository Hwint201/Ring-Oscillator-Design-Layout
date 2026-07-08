# Ring-Oscillator-Design-Layout
A ring oscillator is a simple oscillator circuit comprised of an odd number (N) of cascaded inverters forming a closed loop, where the output of the final stage is fed back into the input of the first. Each inverter introduces a propagation delay, and the accumulated loop delay establishes the condition for self-sustaining oscillation.

<img width="480" height="300" alt="image" src="https://github.com/user-attachments/assets/bbace77a-8fdf-494b-81a1-c96fd525aa06" />

Calculation Formula: $$f = \frac{1}{T} = \frac{1}{2Nt_{pd}}$$ 

# Schematic Ring-Oscillator

<img width="1299" height="521" alt="schematic_RING OSCILLATOR" src="https://github.com/user-attachments/assets/8a4ff2b8-97c4-49cc-a0e6-f97e2fc551f6" />

## Technology & Design Specifications

Technology: Generic 250 nm CMOS Process

Design Tool: Siemens Tanner EDA

Architecture: 9-Stage CMOS Ring Oscillator

PMOS Width ($W_p$): 6 µm

NMOS Width ($W_n$): 3 µm

Channel Length ($L$): 0.5 µm

## Pre_layout

<img width="2874" height="1331" alt="pre_layout" src="https://github.com/user-attachments/assets/09aa7529-cb0f-440c-aad3-35b3565c1dc9" />

# Layout 

<img width="2905" height="1350" alt="layout" src="https://github.com/user-attachments/assets/ac1799d6-91d7-4959-ae5a-767733bab2bd" />

## DRC 

<img width="2742" height="1348" alt="DRC" src="https://github.com/user-attachments/assets/09668151-1529-4337-ac81-e8844ae8024f" />

## LVS

<img width="2687" height="1267" alt="LVS" src="https://github.com/user-attachments/assets/bee69b42-68e3-4702-b8e3-a4fb60befec9" />

## RC parasitics 

<img width="2838" height="1320" alt="Thành phần RC" src="https://github.com/user-attachments/assets/e7bf98f6-f7b3-45d1-b322-6f02073d1324" />

## Post_layout

<img width="1322" height="772" alt="Post_layout" src="https://github.com/user-attachments/assets/1a978707-79a2-46ce-aedb-cc4c6c6c46bd" />

# General Observations 

| Varying Parameter | Observed Trend | Remarks |
| :--- | :--- | :--- |
| **Vdd** | - Larger voltage swing (approaching 0 – Vdd)<br>- Steeper rising/falling edges (decreased rise/fall time)<br>- Increased oscillation frequency | More square-like waveform with fuller amplitude. However, power consumption increases. |
| **Number of Stages (N)** | - Increased period ($T \approx 2 \cdot N \cdot t_{pd}$)<br>- Decreased frequency | More stages $\rightarrow$ transistors have more time to charge/discharge $\rightarrow$ less distorted, more square-like waveform, but slower overall speed. |
| **Wp (W/L of PMOS)** | Stronger PMOS $\rightarrow$ faster rising edge.<br>If Wp is too large compared to Wn $\rightarrow$ imbalance (rise time $\neq$ fall time). | Choose an optimal Wp/Wn ratio to balance the rising and falling edges, resulting in a nearly square wave. |
| **Without Load Capacitance** | - High-frequency oscillation<br>- Waveform tends to be distorted or rounded if transistors cannot charge/discharge in time. | Fast operating speed, but the waveform is not a true square wave. |
| **With Load Capacitance (CL)** | - Decreased frequency (due to larger RC parasitics)<br>- Slower rising/falling edges | Helps the waveform become smoother and more square-like, but reduces the oscillation speed. |




