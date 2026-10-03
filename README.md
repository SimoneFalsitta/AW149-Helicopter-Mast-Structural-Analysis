# AW149 Helicopter Main Rotor Shaft (Mast) - Structural & Fatigue Validation

## Project Overview
This repository contains the complete structural analysis, analytical modeling, numerical FEM simulation, and experimental fatigue validation of the **main rotor shaft (mast)** of the **AW149 military helicopter**, a safety-critical project commissioned by former **AgustaWestland S.p.A. (now Leonardo S.p.A.)**.

The main rotor mast serves as the primary dynamic and structural interface between the main gearbox and the rotor hub, transferring torque, thrust, bending moments, and severe aerodynamic vibratory loads. This study verifies the structural integrity of the mast under ultimate static and multiaxial fatigue loading conditions using representative scaled specimens.

---

## Key Methodologies & Project Workflow

### 1. Analytical Static Assessment (Mast & Representative Specimen)
- **Geometry & Loading**: Evaluated a simplified hollow shaft geometry ($R_i = 70\text{ mm}, t = 9\text{ mm}$) subjected to combined axial load ($N = 100\text{ kN}$), transverse shear ($T = 32\text{ kN}$), bending moment ($M_b = 35\text{ kNm}$), and engine torque ($M_t = -80\text{ kNm}$).
- **Mohr Circle & Yield Criteria**: Derived 2D plane stress state at critical notch locations, calculating principal stresses ($\sigma_I, \sigma_{II}, \sigma_{III}$) and equivalent Von Mises stress.
- **Specimen Equivalence**: Designed a representative specimen ($D_e = 46.94\text{ mm}, D_i = 41.1\text{ mm}$) subjected to an equivalent axial force ($F \approx 127\text{ kN}$) and torque to replicate identical stress fields in laboratory conditions.

### 2. Multiaxial Fatigue Assessment & Buckling Analysis
- **Time-Dependent Stress Cycles**: Evaluated under sinusoidal axial fatigue loads ($N(t) = 12000 + 80000 \sin(\omega t)\text{ N}$) and constant torque ($M_t = 1500\text{ Nm}$).
- **Eulerian Compressive Instability**: Verified buckling safety under peak compressive fatigue loads ($N_{min} = -68\text{ kN}$), obtaining a critical buckling load $P_{cr} = 5371.8\text{ kN}$ ($\eta_{cr} = 79.0$).
- **Sines Multiaxial Fatigue Criterion**: Evaluated alternating stress amplitude ($\sigma_s^* = 198.11\text{ MPa}$) and mean stress hydrostatic invariant ($I_{1,m} = 29.72\text{ MPa}$), taking into account surface finish ($R_a = 0.4\,\mu\text{m}$ grinding) and notch effects ($K_f = 1$).

### 3. Material Selection & Comparison
Evaluated two high-strength aerospace steel alloys for both static and fatigue conditions:
| Property / Metric | 9310 VIM VAR | 32CDV13 |
| :--- | :---: | :---: |
| **Yield Strength ($S_{ys}$)** | $893\text{ MPa}$ | $850\text{ MPa}$ |
| **Ultimate Tensile Strength ($UTS$)** | $1020\text{ MPa}$ | $1000\text{ MPa}$ |
| **Endurance Limit ($\sigma_{FA}$)** | $350\text{ MPa}$ | $320\text{ MPa}$ |
| **Static Safety Factor ($\eta_{VM}$ - Mast)** | **1.548** | **1.474** |
| **Static Safety Factor ($\eta_{VM}$ - Specimen)** | **1.551** | **1.477** |
| **Fatigue Safety Factor ($\eta_{Sines}$ - Specimen)** | **1.715** | **1.567** |

### 4. Experimental Campaign & Rosette Data Processing
- **Strain Gauge Rosette Acquisition**: Processed multi-axial strain time series from 3-element rosettes ($+45^\circ, 0^\circ, -45^\circ$) across three independent experimental campaigns (**Campaigns A, B, and C**).
- **Constitutive Modeling**: Reconstructed full 3D strain/stress tensors via Hooke's 3D law in plane stress conditions using MATLAB.
- **Statistical Analysis**: Automated processing of experimental data using scatterplots and **Gaussian Probability Density Functions (PDF)** to quantify load spectrum variability.

### 5. Numerical FEM Simulation (Abaqus/Standard)
- Constructed 3D Finite Element models in **Abaqus** under peak fatigue load conditions ($N = 92\text{ kN}, M_t = -1500\text{ Nm}$).
- **FEM vs. Analytical Validation**:
  - Analytical Von Mises Stress: $\sigma_{VM, analytical} = 384.99\text{ MPa}$
  - Abaqus FEA Von Mises Stress: $\sigma_{VM, FEM} = 386.80\text{ MPa}$
  - **Relative Error**: **0.47%**, confirming exceptional accuracy and consistency between analytical models and FEA simulations.

---

## MATLAB Source Code (Appendix A)
All computational routines developed for this project are included in **Appendix A (pages 30–40)** of the report:
- `MAST STATIC ASSESSMENT`: Shear/bending moment diagrams, Mohr circle calculations, and Von Mises safety factors.
- `SPECIMEN STATIC ASSESSMENT`: Equivalent force calculations and notch stress distribution.
- `SPECIMEN FATIGUE ASSESSMENT`: Time-dependent principal stress eigenvalues, Eulerian buckling check, and Sines fatigue criteria.
- `EXPERIMENTAL DATA`: Automated import and strain rosette transformation matrix solving.
- `STATISTICS`: Statistical scatterplots and Gaussian PDF distribution generation routines across testing campaigns.

---

## Repository Structure
- `MACHINE_DESIGN.pdf`: Complete technical report detailing the mathematical formulations, boundary condition diagrams, Mohr circles, Abaqus FEA stress contours, experimental statistical plots, and MATLAB code.

---

### Authors & Collaborators:
- **Simone Falsitta** 
- **Simone Gandini** 
- **Francesco Micoli** 
- **Andrea Salvi**

 ## 👥 Project Team & Academic Context

**Politecnico di Milano 1863**  
*School of Industrial and Information Engineering — M.Sc. in Aeronautical Engineering* (A.Y. 2024–2025)  
**Course**: Machine Design  
**Supervisors**: Prof. Andrea Manes, Prof. Salvatore Annunziata  
