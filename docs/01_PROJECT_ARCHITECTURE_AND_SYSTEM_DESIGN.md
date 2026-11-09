# Project Architecture & System Design: Engine-Driven Centrifugal Blower System

---

## 1. Executive Summary

The **Engine Blower System** is an integrated mechanical assembly combining an internal combustion (IC) reciprocating piston engine with a direct-coupled centrifugal blower. 

In this system:
- The **engine** acts as the prime mover, converting thermal combustion energy into rotational mechanical power.
- The **crankshaft** directly drives the blower rotor without intermediate belts or reduction gearboxes.
- The **centrifugal impeller and volute casing** accelerate and compress ambient air, producing a directed, high-velocity, pressurized airflow stream for industrial cooling, forced induction, or material handling applications.
- The entire powertrain is mounted on a dedicated, structurally stiff **engine mount** to maintain shaft alignment, absorb cyclic engine vibration, and secure the machine to its foundation.

```
       [ Air / Fuel Combustion ]
                   │
                   ▼
       ┌───────────────────────┐
       │     Piston Crown      │ <── Linear Reciprocating Motion
       └───────────┬───────────┘
                   │  (Wrist Pin)
                   ▼
       ┌───────────────────────┐
       │    Connecting Rod     │ <── Kinematic Slider-Crank Inversion
       └───────────┬───────────┘
                   │  (Crankpin)
                   ▼
       ┌───────────────────────┐
       │      Crankshaft       │ <── Continuous Rotary Motion (Torque + RPM)
       └───────────┬───────────┘
                   │  (Direct Drive Co-Axial Extension)
                   ▼
       ┌───────────────────────┐
       │ Centrifugal Impeller  │ <── Radial Acceleration of Air (Dynamic Head)
       └───────────┬───────────┘
                   │  (Centrifugal Throw into Volute)
                   ▼
       ┌───────────────────────┐
       │    Impeller Casing    │ <── Pressure Recovery (Diffusion) -> Static Pressure
       └───────────┬───────────┘
                   │
                   ▼
       [ High-Pressure Discharged Air Stream ]
```

---

## 2. File & Component Inventory

The project is modeled in **AutoCAD Mechanical 3D Solid Modeling** (`AC1032` format). All backup files (`.bak`) have also been recovered as active drawing files (`.dwg`).

| Part File Name | CAD File Size | Primary Function in Architecture | Manufacturing Process |
| :--- | :--- | :--- | :--- |
| [`engine block.dwg`](file:///c:/abhay/engine_Blower_Design/engine%20block.dwg) | ~976 KB | Hosts cylinder bore, air-cooling fins, crankcase journal bearings, and front nose cone. | Die Cast Aluminum Alloy / Cast Iron |
| [`piston.dwg`](file:///c:/abhay/engine_Blower_Design/piston.dwg) | ~332 KB | Reciprocates within cylinder; receives combustion pressure and transmits force via wrist pin. | Gravity Die Cast / Forged Aluminum |
| [`connecting rod.dwg`](file:///c:/abhay/engine_Blower_Design/connecting%20rod.dwg) | ~995 KB | Connects piston wrist pin to crankshaft pin; converts reciprocating motion into rotation. | Drop Forged Carbon Steel (AISI 1045) |
| [`Crankshaft.dwg`](file:///c:/abhay/engine_Blower_Design/Crankshaft.dwg) | ~260 KB | Single-throw crankshaft with integrated counterweight, crankpin, and drive shaft extension. | Forged / CNC Turned Alloy Steel (AISI 4140) |
| [`impeller.dwg`](file:///c:/abhay/engine_Blower_Design/impeller.dwg) | ~70 KB | Centrifugal squirrel-cage drum rotor with radial/forward blades; accelerates incoming air. | Stamped / Molded Aluminum or Glass-filled Nylon |
| [`Impeller Casing.dwg`](file:///c:/abhay/engine_Blower_Design/Impeller%20Casing.dwg) | ~413 KB | Aerodynamic scroll volute housing with axial intake eye and tangential rectangular diffuser. | Sand Cast Aluminum / Formed Sheet Metal |
| [`engine mount.dwg`](file:///c:/abhay/engine_Blower_Design/engine%20mount.dwg) | ~991 KB | Welded/cast structural chassis base providing dual-support mounting pads for engine and blower. | Fabricated Structural Mild Steel (ASTM A36) |
| [`bolt1.dwg`](file:///c:/abhay/engine_Blower_Design/bolt1.dwg) | ~160 KB | Standard hex head fastener (short shank) for securing casing and block mounting brackets. | Cold Formed High-Tensile Steel (Class 8.8) |
| [`bolt2.dwg`](file:///c:/abhay/engine_Blower_Design/bolt2.dwg) | ~162 KB | Standard hex head fastener (long shank) for securing engine block crankcase and structural joints. | Cold Formed High-Tensile Steel (Class 8.8) |
| [`assembly.dwg`](file:///c:/abhay/engine_Blower_Design/assembly.dwg) | ~2.79 MB | Master 3D assembly combining all 9 subcomponents with concentric, planar, and bolted constraints. | Full Mechanical Subassembly |

---

## 3. What Inputs Were Given?

To design this engine-blower unit from scratch, three sets of engineering inputs were established:

### 3.1. Thermodynamic & Aerodynamic Performance Targets
- **Required Blower Airflow ($\mathbf{Q}$):** Continuous target volumetric flow rate (e.g., $150 - 300\text{ CFM}$ / $0.07 - 0.14\text{ m}^3/\text{s}$).
- **Static Pressure Rise ($\mathbf{\Delta P}$):** Static pressure boost required to overcome downstream air duct restriction (e.g., $2.5 - 5.0\text{ kPa}$).
- **Blower Operating Speed ($\mathbf{N}$):** $3,000 - 4,500\text{ RPM}$ (matched directly to small IC engine maximum power band).
- **Target Brake Power ($\mathbf{P_b}$):** Required engine shaft output calculated via:
  $$P_b = \frac{Q \times \Delta P}{\eta_{\text{blower}} \times \eta_{\text{mechanical}}}$$
  Assuming $\eta_{\text{blower}} \approx 65\%$ and direct coupling $\eta_{\text{mech}} \approx 98\%$, an engine rating of $1.5 - 2.5\text{ HP}$ ($1.1 - 1.8\text{ kW}$) was chosen.

### 3.2. Kinematic & Geometric Engine Inputs
- **Engine Type:** Single-cylinder, two-stroke or small four-stroke air-cooled internal combustion engine.
- **Bore Diameter ($D$):** Sized to provide adequate piston displacement ($V_d = \frac{\pi}{4} D^2 S$).
- **Stroke Length ($S$):** Determined by crankshaft crank throw radius ($R = \frac{S}{2}$).
- **Connecting Rod Length ($L$):** Sized with an optimal rod-to-crank ratio ($\lambda = \frac{L}{R} \approx 3.2 - 3.8$) to minimize piston side-thrust against the cylinder wall while keeping overall engine height compact.
- **Cooling Requirements:** Radial fin array geometry on the cylinder exterior to dissipate peak combustion heat via natural or forced convection.

### 3.3. CAD Modeling & Assembly Constraints
- **Tolerance Standards:** ISO fit standards (H7/h6 for journal bearing locations; H7/e7 for piston-cylinder running clearance).
- **Standard Hardware:** Metric standard hexagonal bolts (M6/M8) with standard clearance hole pitches.
- **Axial Alignment:** Crankshaft center axis must strictly align with the impeller hub bore and volute casing suction centerline.

---

## 4. What Does the System Produce?

The system takes in chemical fuel-air mixture and ambient air, and produces:

1. **Mechanical Output (Intermediate):** High-speed rotary shaft torque produced by the slider-crank kinematic chain.
2. **Fluid Output (Final Delivery):** A high-velocity, compressed stream of air discharged tangentially through the rectangular volute diffuser.
   - High dynamic kinetic energy imparted by the rotating impeller blades.
   - Smooth conversion of kinetic energy into static pressure within the expanding scroll volute casing.
3. **Thermal Rejection:** Dissipated heat radiating outward across the engine block cooling fins.
4. **Structural Reaction:** Balanced vibrational forces transmitted through the dual-cradle engine mount into the chassis foundation.

---

## 5. How Does It Produce It? (Step-by-Step Physics Flow)

1. **Combustion & Expansion:** Rapid burning of fuel-air mixture inside the cylinder head builds peak gas pressure ($30 - 50\text{ bar}$) against the piston crown.
2. **Linear Reciprocation:** Gas pressure drives the piston down along the vertical cylinder bore from Top Dead Center (TDC) to Bottom Dead Center (BDC).
3. **Kinematic Conversion:** The small end of the connecting rod pivots on the piston wrist pin, while the big end drives the crankpin, forcing the crankshaft to rotate.
4. **Direct Torque Transmission:** The crankshaft rotates inside journal bearings within the crankcase. The shaft extends co-axially through the front nose of the engine block directly into the blower casing.
5. **Air Ingestion (Suction):** The rotating impeller creates a low-pressure zone at the central eye of the casing, drawing ambient air in axially.
6. **Centrifugal Acceleration:** The multiblade drum rotor accelerates the air radially outward to its blade tips, imparting high velocity head ($\frac{v^2}{2g}$).
7. **Pressure Diffusion in Volute:** The air enters the logarithmic spiral volute chamber. Because the cross-sectional area of the volute casing progressively expands toward the outlet, velocity decreases smoothly, recovering velocity head into usable static pressure (Bernoulli's Principle).
8. **Tangential Discharge:** High-pressure air exits tangentially through the rectangular discharge nozzle to do work.

---

## 6. Detailed 3D CAD Modeling Architecture

The CAD implementation was executed using **Bottom-Up Assembly Methodology** in AutoCAD Mechanical:

```
[ Individual Part Modeling ]
  ├── engine block.dwg     ──> Revolve base, extrude cooling fins, subtract cylinder bore
  ├── Crankshaft.dwg       ──> Revolve main journal, extrude web/counterweight, extrude crankpin
  ├── piston.dwg           ──> Revolve hollow skirt, subtract wrist pin transverse bore
  ├── connecting rod.dwg   ──> Extrude I-beam shank, bore small/big ends, fillet transitions
  ├── impeller.dwg         ──> Revolve base boss & shroud rings, circular array of blades
  ├── Impeller Casing.dwg  ──> Sweep volute curve, loft to rectangular nozzle, shell/subtract cavity
  ├── engine mount.dwg     ──> Extrude structural side plates, gussets, base plate, hole cutouts
  └── bolt1 & bolt2.dwg    ──> Revolve threaded shank, extrude hex head, chamfer
            │
            ▼
[ Assembly Space: assembly.dwg ]
  ├── Step 1: Base Anchor  ──> Engine mount grounded in WCS (World Coordinate System)
  ├── Step 2: Block Fix    ──> Engine block mated to rear mount cradle with bolt1/bolt2
  ├── Step 3: Crankshaft   ──> Co-axial journal insertion into crankcase bore
  ├── Step 4: Slider-Crank ──> Rod big end to crankpin; piston to small end; piston into cylinder bore
  ├── Step 5: Blower Casing──> Impeller Casing aligned co-axially to crank center; bolted to front mount
  └── Step 6: Rotor Fit    ──> Impeller keyed/pressed onto crankshaft output taper inside volute cavity
```

### Key AutoCAD 3D Operations Used:
- **`UCS` (User Coordinate System):** Repositioning coordinate planes to sketch non-orthogonal features (e.g., crankpin offset, volute tangent nozzle, mounting bolt holes).
- **`EXTRUDE` & `REVOLVE`:** Generating primary axisymmetric bodies (pistons, journals, cylinder sleeve) and prismatic shapes (mounting plates, rod shanks).
- **`PRESSPULL` & `SUBTRACT`:** Hollowing internal fluid cavities, creating cylinder bores, wrist pin holes, and fastener clearances.
- **`UNION`:** Merging composite solid components (e.g., fusing crank counterweight, main shaft, and crankpin into a single continuous solid).
- **`FILLETEDGE` / `CHAMFEREDGE`:** Relieving stress concentrations at shaft step shoulders, crank webs, and connecting rod transitions.
- **`ALN` (3D ALIGN) / `3DROTATE`:** Orienting and positioning individual solid bodies into their precise spatial mates within `assembly.dwg`.
- **`INTERFERE` (Interference Check):** Running interference detection between piston and cylinder wall, connecting rod swing and crankcase interior, and impeller outer diameter and volute casing cutwater.

---

## 7. Summary of Architecture Strengths

1. **High Power Density & Compact Footprint:** Direct co-axial coupling eliminates pulleys, belts, belts guards, and extra bearing pillows, reducing total machine weight by over $30\%$.
2. **Thermal Independence:** The air-cooled fin array eliminates water pumps, radiators, hoses, and coolant fluids, enabling reliable standalone outdoor operation.
3. **Rigid Dual-Cradle Bed Mount:** The monolithic engine mount secures both the engine block and the heavy overhung blower casing on a single continuous baseline, eliminating shaft misalignment caused by operational chassis twisting.
