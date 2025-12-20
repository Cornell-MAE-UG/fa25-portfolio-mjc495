---
layout: project
title: Thermofluids Device Analysis - Car Radiator
description: Car Radiator
image: /assets/images/Screenshot 2025-12-19 180227.png
---


As a typical combustion engine operates, excess heat transfers from the engine block to coolant that circulates through and aroung the engine, raising the coolant's temperature. A car radiator functions as a liquid-to-air heat exchanger that removes heat from coolant to air that flows into the radiator by use of a fan and vehicle motion. Heat transfer from the hot coolant to cool air across a finite temperature difference makes this process irreversible, and thus it generates entropy. The coolant that exits the radiator goes back into the engine, continuing the cycle, while the air exits to the surroundings. This process prevents overheating from continuously increasing temperature of the coolant. 

---
### Realistic Radiator Profile:
<p style="text-align:center;">
</p>
<p style="text-align:center;">
  <img src="{{ '/assets/images/realistic_radiator.png' | relative_url }}"
       alt="realistic radiator"
       style="width: 300px; height: auto;">
</p>
---
## Radiator Control-Volume Model

### Assumptions
- Steady-state, steady-flow
- Two streams: pure coolant and pure air 
- Negligible kinetic and potential energy changes, reasonable for an ideal heat exchanger, since it should have no impact on flow speed or significant change in altitude
- Radiator produces no work, also reasonable since a heat exchanger is not designed to do mechanical work
- Radiator is well insulated (no external heat transfer), this may not be true in real scenarios but it is an appropriate modeling assumption because ideally a heat exchanger has minimal heat transfer to or from the surroundings


Below is an symbolic analysis of a car radiator using this model

---

### Mass balances 
The 'c' subscript denotes coolant, while the 'a' subscript denotes air

For each stream: 

$$
\dot m_{c,in}=\dot m_{c,out}=\dot m_c
$$


$$
\dot m_{a,in}=\dot m_{a,out}=\dot m_a
$$

---

### Energy balance 
General steady-state energy equation:
$$
\frac{dE}{dt}_{CV} = 0
$$

$$
\dot Q_{CV}-\dot W_{CV}+\sum_{in}\dot m\left(h+\frac{V^2}{2}+gz\right)
-\sum_{out}\dot m\left(h+\frac{V^2}{2}+gz\right)=0
$$

Considering change in KE, PE, and W are negligible, and the model heat exchanger is well insulated:

$$
\dot m_{in}\frac{V^2_{in}}{2}-\dot m_{out}\frac{V^2_{out}}{2}\approx 0
$$

$$
\dot Q_{CV}+\dot m_c h_{c,in}+\dot m_a h_{a,in}
-\dot m_c h_{c,out}-\dot m_a h_{a,out}=0
$$


$$
\dot m_c\left(h_{c,in}-h_{c,out}\right)\approx
\dot m_a\left(h_{a,out}-h_{a,in}\right)
$$

Assuming constant specific heats:
$$
\dot m_c c_{p,c}\left(T_{c,in}-T_{c,out}\right)\approx
\dot m_a c_{p,a}\left(T_{a,out}-T_{a,in}\right)
$$

Define the radiator heat rejection rate (coolant side):
$$
\dot Q_{rej}\equiv \dot m_c c_{p,c}\left(T_{c,in}-T_{c,out}\right)
$$

---

### Entropy balance
General steady-flow entropy balance:
$$
0=\sum_{in}\dot m s_{in}-\sum_{out}\dot m s_{out}+\sum_k\frac{\dot Q_k}{T_k}+\dot S_{gen}
$$

For a two-stream radiator:
$$
\dot S_{gen}=
\dot m_c\left(s_{c,out}-s_{c,in}\right)+
\dot m_a\left(s_{a,out}-s_{a,in}\right)
-\sum_k\frac{\dot Q_k}{T_k}
$$

If the radiator is externally adiabatic:
$$
\dot S_{gen}=
\dot m_c\left(s_{c,out}-s_{c,in}\right)+
\dot m_a\left(s_{a,out}-s_{a,in}\right)\ge 0
$$

**Interpretation:** Heat transfer occurs across a finite temperature difference (and there are pressure drops), so the process is irreversible and generates entropy.

---



