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

---
### Depiction of a Cross Flow Heat Exchanger
<p style="text-align:center;">
</p>
<p style="text-align:center;">
  <img src="{{ '/assets/images/crossflow.png' | relative_url }}"
       alt="realistic radiator"
       style="width: 300px; height: auto;">
</p>
The cross flow heat exchanger is an accurate model for the car radiator

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
\dot m_{in}gz_{in}-\dot m_{out}gz_{out}\approx 0
$$

$$
\dot W_{CV}\approx 0 
$$

$$
\dot Q_{CV}\approx 0
$$

$$
\dot m_c h_{c,in}+\dot m_a h_{a,in}
-\dot m_c h_{c,out}-\dot m_a h_{a,out}=0
$$


$$
\dot m_c\left(h_{c,in}-h_{c,out}\right) =
\dot m_a\left(h_{a,out}-h_{a,in}\right)
$$

This can be further simplified under the assumption of constant specific heats, which is reasonable considering that car radiators do not typically span a huge range of temperatures:


$$
\dot m_c c_{p,c}\left(T_{c,in}-T_{c,out}\right)\approx
\dot m_a c_{p,a}\left(T_{a,out}-T_{a,in}\right)
$$

The radiator heat rejection rate 
$$
\dot Q_{rej}
$$
represents the rate at which heat is transferred out of the hot coolant and into the air stream.

$$
\dot Q_{rej} = \dot m_c c_{p,c}\left(T_{c,in}-T_{c,out}\right)
$$

Interpretation: The rate at which a radiator rejects heat from its coolant is dependent on its mass flow rate and the magnitude of the difference between its exit and inlet temperatures.

---

### Entropy balance
General steady-state entropy balance:

$$
\sum_{in}\dot m s_{in}-\sum_{out}\dot m s_{out}+\sum_k\frac{\dot Q}{T_b}+\dot S_{gen} = 0
$$

For a cross-flow heat exchanger:

$$
\dot S_{gen}=
\dot m_c\left(s_{c,out}-s_{c,in}\right)+
\dot m_a\left(s_{a,out}-s_{a,in}\right)
-\sum_k\frac{\dot Q}{T_b}
$$

Since the radiator model is externally adiabatic:

$$
\dot S_{gen}=
\dot m_c\left(s_{c,out}-s_{c,in}\right)+
\dot m_a\left(s_{a,out}-s_{a,in}\right)\ge 0
$$

Interpretation: For any real radiator, the value of entropy generated will be significantly greater than 0, since heat transfer occurs across a finite temperature difference. For the ideal and internally reversible radiator, the entropy generated is equal to 0. The entropy generation for the radiator will never be negative because this is impossible.

---
### Radiator Performance Under Different Operating Conditions

1.
Consider a very slow moving vehicle:

In this case, 
$$
\dot m_{a,in}
$$
is very small, since a lot of the mass flow of air is from air coming under the hood while driving. This decreases the value of 
$$
\dot Q_{rej}
$$
, as they are directly porportional. Since the radiator is able to reject less heat from the coolant at low speeds, this explains why overheating is common at idle rather than on the highway. This is also why most radiators typically have a fan that ensures a high enough mass flow rate of air even when the vehicle isn't moving.

2.
Consider a very hot day:

In this case,
$$
\dot T_{a,in}
$$
is likely similar in value to 
$$
\dot T_{c,in}
$$
, meaning that the temperature driving force of the radiator is greatly decreased. This reduces the possible decrease in temperature of the coolant that the radiator is attempting to achieve, and in turn sends coolant that is still too hot back to the engine, eventually risking overheating.

3.
Consider a radiator that has clogged fins:

In this case, the effective area of the radiator that is available for heat transfer decreases. While this may not relate directly to previous entropy and enegery balances, there is another equation that governs real heat exchangers:

$$
\dot Q \approx UA \Delta T_{lm}
$$

Where U is the overall heat transfer coefficient, A is effective heat transfer area, and T is the log mean temperature difference. In idealized calculations area was ignored, but in reality a radiator with more heat transfer area is able to remove more heat from the coolant. Therefore, a radiator that is dirty or has debris in its fins has reduced heat transfer area, and is thus less effective.

