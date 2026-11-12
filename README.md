# ☀️ SunForge: Off-Grid Concentrated Solar Thermal Foundry

**SunForge** is a modular, off-grid solar thermal casting system designed to melt or sinter local silica sand (\(SiO_2\)) and basaltic regolith into structural bricks, thermal storage blocks, fire-shield tiles, and sintered footwear soles using concentrated sunlight, gravity, and non-wetting Carbon-Carbon (C/C) molds.

---

## 🏗️ Core Architecture & Process Flow

SunForge separates high-temperature thermal melting from low-power mechanical positioning to maximize reliability and energy efficiency:

```text
[ GRAVITY-FED RAW SAND / REGOLITH HOPPER ]
  └── Passive pre-heating via rising convective heat; cold outer sand insulates walls
         │
         ▼
[ X-FLUX OPTICAL MELTING CORE (> 1700°C) ]
  └── Heliostat / Fresnel lens concentrates solar beam onto the underside melt boundary
         │
         ▼  (Viscous molten stream)
[ LATERAL C/C MOLD CARRIAGE & PURGE TRAY ]
  ├── Primary Mold: Forms structural tile / brick / sole (with mechanical compaction roller)
  └── Adjacent Overflow / Purge Crucible: Captures startup impurities & excess melt flow
         │
         ▼  (Inert gas seal boundary -> Cool exterior rails)
[ CONTROLLED ANNEALING & COOLING TUNNEL ]
  └── Gradual stress-relief cooling to prevent thermal shock fracturing
```

---

## ⚙️ Essential Physics & Engineering Constraints

To keep future simulations, CAD designs, and scale calculations physically realistic, all development must adhere to the following laws and constraints:

### 1. High Melt Viscosity & Mechanical Compaction
* **Physics Constraint:** Unlike molten metals, molten silica ($SiO_2$) has an extremely high viscosity ($10^5 - 10^7 \text{ Pa}\cdot\text{s}$ even at 1800–2000°C) and **does not self-level** into sharp corners.
* **Design Rule:** Gravity alone is insufficient for precision molding. A rotating **C/C compaction cam-roller** (or mechanical press) must actively press the viscous melt into the mold cavity while shedding heat during its non-contact rotation phase.

### 2. Overflow / Purge Crucible & Flow Stabilization
* **Physics Constraint:** Solar flux fluctuates with passing clouds, causing variations in melt rate and viscosity. Stopping a high-temperature melt stream abruptly risks solidifying glass inside the nozzle.
* **Design Rule:** An **adjacent C/C overflow/purge crucible** is mounted directly beside the primary mold on the lateral carriage. During startup, cloud transients, or mold indexing, a slight lateral shift diverts excess melt and surface impurities safely into the overflow tray. Cooled overflow cullet is crushed and recycled into the raw feed (zero-waste).

### 3. Thermal Expansion & Annealing (Avoiding Devitrification)
* **Physics Constraint:** Rapid cooling through the $1100^\circ\text{C} - 1400^\circ\text{C}$ window triggers crystallization (devitrification into cristobalite), causing structural micro-cracking upon further cooling.
* **Design Rule:** Cast parts must rapidly clear the upper crystallization zone, hold briefly in an insulated **annealing zone (~950–1100°C)** to equalize internal stresses, and cool gradually to ambient temperature.

### 4. Carbon-Carbon (C/C) Oxidation Limit & Gas Shielding
* **Physics Constraint:** Non-wetting Carbon-Carbon molds withstand > 2500°C in vacuum or inert gas, but rapidly oxidize (burn) in open air above **450–500°C**.
* **Design Rule:**
  * *Terrestrial Operation:* The hot C/C mold zone must be enclosed inside a slightly positive-pressure **Argon ($Ar$) or Nitrogen ($N_2$) chamber**, using sand seals so all drive rails and motors stay outside in cool air.
  * *Lunar / Vacuum Operation:* Natural vacuum eliminates oxidation completely, allowing open-frame C/C tooling with zero shielding gas.

### 5. Solar Flux & Concentration Ratio ($C$)
* **Physics Constraint:** Reaching 1750°C+ requires a solar concentration ratio of at least **1,500x to 3,000x** (accounting for radiative heat losses proportional to $T^4$ per the Stefan-Boltzmann law).
* **Design Rule:** Keep initial prototypes compact (e.g., 1–2 $m^2$ concentrator producing small bricks or tiles) rather than oversized industrial plants, scaling throughput via parallel modular units.

---

## 🤖 AI & Engineering Context (For Future Development)

*Note to AI assistants and contributors:* This repository is an independent, modular solar-foundry project decoupled from *QuartzGate* and *BioFrame*. When assisting with calculations, CAD, or control logic, follow these strict rules:

1. **Keep Scale Realistic:** Avoid sci-fi megastructures. Focus on portable, trailer-sized or modular field units (1–5 kW thermal input) before modeling multi-ton industrial plants.
2. **Respect Viscosity & Flow Continuity:** Never model molten quartz like water or liquid aluminum. Always include mechanical roller compaction and lateral diversion to the **adjacent overflow/purge tray** during mold transitions.
3. **Thermodynamic Honesty:** Account for radiative heat losses ($\sigma T^4$) at > 1700°C and include inert-gas shielding requirements for terrestrial C/C components.
4. **Cross-Project Compatibility:** Maintain parametric mold dimensions so SunForge can cast flat interlocking tiles (*QuartzGate* repair modules), thermal storage bricks, and sintered regolith footwear soles (*BioFrame* ISRU boots).

---

## 🚀 Roadmap
- [ ] **Phase 1: Solar Thermal Energy Balance** (Python script calculating mirror/lens area, radiative losses at 1800°C, and melt rate in kg/hour).
- [ ] **Phase 2: C/C Mold & Overflow Carriage CAD** (Parametric 2D/3D layout of the primary mold, adjacent purge tray, and sand-sealed external rails).
- [ ] **Phase 3: Small-Scale Bench Prototype** (Testing basalt/silica sintering using a 1–2 $m^2$ Fresnel lens or parabolic dish).
