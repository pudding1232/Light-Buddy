# Light Buddy: Adjustable Flashlight Arm

**An articulating, tool-free arm that holds a pocket flashlight so you can light up a work area and keep both hands free.**

<p align="center">
  <img src="images/final-assembly.jpg" width="620" alt="Final Light Buddy assembly holding a flashlight">
</p>

| | |
|---|---|
| **Team** | Tran Gia Huy Pham, Robert Lopez, Leonardo Valenti |
| **Context** | Critical Design Review (CDR), <!-- TODO: course name / school, e.g. "ME 1XX – Additive Manufacturing" --> Spring 2026 |
| **Processes** | FDM (Markforged Onyx + continuous carbon fiber), SLS (Nylon 12), FDM TPU, PolyJet |
| **CAD** | <!-- TODO: e.g. Autodesk Fusion / SolidWorks --> Parametric CAD, assembly drawing, rendered animation |
| **Outcome** | Functional prototype, 114.71 cc total part volume, about $23.88 material cost per unit |

---

## My role

<!-- TODO: This is the most important section for a recruiter. Replace the bullets below with what YOU did. Be specific. -->
- _[What you personally designed, e.g. the Hirth-joint arm links and thumbscrews]_
- _[Analysis or testing you ran]_
- Created the arm link assembly drawing and parts list ([docs/arm-link-assembly-drawing.png](docs/arm-link-assembly-drawing.png))

---

## The problem

> *"Design an adjustable arm that allows the user to securely hold a variety of small flashlights in order to illuminate a specific area."*

Professionals and hobbyists often carry a pocket flashlight, but holding it ties up a hand. Light Buddy mounts on a surface, grips a range of flashlight sizes, and can be aimed and locked in place. That leaves both hands free for the work.

## Final design

<p align="center">
  <img src="images/exploded-view.gif" width="420" alt="Animated exploded view of the assembly">
  <img src="docs/arm-link-assembly-drawing.png" width="420" alt="Arm link assembly drawing with parts list">
</p>

| Feature | Why it's there |
|---|---|
| **Ratcheting base with removable cap** | Rotates in fixed steps. The cap can be swapped for future base designs. Pockets for insert magnets let it mount on ferrous surfaces. |
| **Hirth gear joints** | Serrated face gears lock at discrete angles, so the arm holds its aim under load. The design is modular, so links can be added to extend the reach. |
| **Thumbscrews** | Every joint adjusts by hand, with no tools needed. |
| **V-block mount + TPU straps** | The V-shape self-centers round bodies of different diameters. Integrated strap buckles clamp the light in place. |

**Parts list:** 2× arm link, 3× thumbscrew, 1× flashlight holder (V-block), 1× ratchet base assembly.

---

## Design iterations

### Prototype V1: proving the joints

<p>
  <img src="images/cad-v1-render.png" height="175" alt="V1 CAD render">
  <img src="images/cad-v1-hirth-joint.png" height="175" alt="V1 Hirth joint">
  <img src="images/v1-assembly.jpg" height="175" alt="V1 printed assembly">
  <img src="images/v1-vblock.jpg" height="175" alt="V1 printed V-block">
</p>

- ✅ The Hirth gears and threads worked well.
- ❌ The V-block was bulky, and the base wasn't very functional.

### Prototype V2: a better base and a smaller holder

<p>
  <img src="images/cad-v2-render.png" height="175" alt="V2 CAD render">
  <img src="images/cad-v2-ratchet-base-section.png" height="175" alt="V2 ratcheting base section">
  <img src="images/v2-ratchet-core.jpg" height="175" alt="V2 printed ratchet core">
  <img src="images/v2-vblock.jpg" height="175" alt="V2 printed V-block">
</p>

- Added a **ratcheting base with integrated magnets**.
- Made the V-block smaller and added **strap loops** to the holder.

### Prototype V3: designing for manufacturing

<p>
  <img src="images/cad-v3-render.png" height="175" alt="V3 CAD render">
  <img src="images/cad-v3-built-in-support.png" height="175" alt="V3 built-in support">
  <img src="images/v3-vblock-straps-1.jpg" height="175" alt="V3 V-block with TPU straps">
  <img src="images/v3-base-vblock.jpg" height="175" alt="V3 base and V-block">
</p>

- Designed **support structures into the V-block model** so it prints cleanly (DfAM).
- Added a **lip to the base** so bases can be swapped more easily.

### V-block evolution (V1 → V3)

<p align="center"><img src="images/vblock-v1-v3-front.jpg" width="620" alt="V-block versions 1, 2 and 3 side by side"></p>

---

## Engineering challenges

**Materials**

- **Onyx with continuous carbon fiber** for the arms, for stiffness so the arm stays rigid once it's locked.
- **Flexible Onyx ears** in the ratcheting base, so the ratchet can click.
- **SLS Nylon 12** for the ratchet core and housing cap, for precision and isotropic strength.
- **TPU 95A** for the straps.

**Design for additive manufacturing**

| Problem | Solution |
|---|---|
| The V-block still needed support material | Designed custom support structures into the part |
| The ratchet base cap was fragile and broke easily because of its FDM print orientation | Switched to **SLS** for isotropic properties |
| The ratchet housing was stiff and hard to tune | Open. See [Next steps](#next-steps) |
| Metric threads don't print well | Open |

**Tolerances:** The thumbscrew threads and ratcheting base were the hardest fits to get right, and results from the Markforged printer were inconsistent between prints.

### Failure analysis

<img src="images/failure-sheared-shaft.jpg" width="220" align="right" alt="Sheared shaft at the base">

Even after the wall count was increased to 6, a shaft **broke near the base**. The cause was poor print accuracy: the threads bound up, and the torque from tightening sheared the shaft. This is why tolerance tuning on the threads became a critical project element.

<br clear="right">

---

## Verification & testing

<p>
  <img src="images/shake-test.gif" height="230" alt="Shake test: flashlight stays secured while the arm is shaken">
  <img src="images/test-1lb-load.jpg" height="230" alt="1 lb load test">
  <img src="images/test-toolbox-mount-1.jpg" height="230" alt="Mounted magnetically on a toolbox">
  <img src="images/test-flashlight-holder.jpg" height="230" alt="Holding a different flashlight">
</p>

The three critical requirements were: **holds multiple flashlights**, **stays rigid when fixed**, and **can be adjusted repeatedly**. The arm was tested with several flashlights, mounted magnetically on a toolbox, shaken, and loaded with **1 lb**.

| Quantitative requirement | Priority | Result |
|---|---|---|
| Fits within a 5″ × 5″ × 5″ envelope | High | ✅ All dimensions < 5″ |
| Part volume ≤ ⅓ of that envelope (≈ 683 cc) | High | ✅ 114.71 cc (~6% of the envelope) |
| Holds at least 3 types of flashlight | High | ✅ Tested with multiple flashlights |
| Holds about 5 oz | High | ✅ Held 1 lb (16 oz) |
| Joints survive double flashlight weight (about 10 oz) | Medium | ✅ Held 1 lb (16 oz) |
| At least 3 axes of adjustment | Medium | ✅ 3 Hirth joints + rotating ratchet base |
| Setup in about 20 s | Low | <!-- TODO: measured time --> — |
| Extended arm length about 10 in | Low | <!-- TODO: measured length --> — |

<details>
<summary>Qualitative requirements</summary>

| Requirement | Priority |
|---|---|
| Demonstrates fit with another object, or has multiple components that fit together | High |
| Serves a function other than visual | High |
| Rigid when fixed; doesn't sag over time | High |
| Holds the flashlight firmly; the light stays in place once tightened | High |
| Attaches to multiple surfaces, both magnetic and non-magnetic | Medium |
| Thin folded form factor that fits a medium pocket | Medium |
| Can be adjusted with one hand | Low |
| Collapsible and modular, with swappable parts | Low |
| Simple appearance suitable for professional use | Low |

</details>

---

## Cost & production

| # | Part | Process | Material | Volume (cc) | Cost ($) |
|---|---|---|---|---|---|
| 1 | Arm (×2) | FDM | Onyx + continuous CF | 24.70 + 1.94 CF | 11.68 |
| 2 | Nut (×3) | FDM | Onyx | 7.72 | 1.83 |
| 3 | V-block holder | FDM | Onyx | 18.24 | 4.33 |
| 4 | Ratchet housing | FDM | Onyx | 7.38 | 1.75 |
| 5 | Housing cap | SLS | Nylon 12 | 20.00 | 1.58 |
| 6 | Ratchet core | SLS | Nylon 12 | 26.50 | 2.55 |
| 7 | TPU straps (×2) | FDM | TPU 95A | 8.23 | 0.16 |
| | **Total** | | | **114.71** | **$23.88** |

### Customization concept

<p>
  <img src="images/v3-nut-polyjet-hd.jpg" height="200" alt="PolyJet printed custom nut">
  <img src="images/custom-nut-shop-logo.png" height="200" alt="Custom nut with shop logo">
  <img src="images/custom-nut-patterns.png" height="200" alt="Custom nut patterns">
</p>

Tradespeople often mark their tools so they don't get mixed up on a job site, and shops like to brand their equipment. Buyers could keep the standard black FDM thumbscrew nuts or pay extra for 1–3 **full-color PolyJet nuts** with a logo or graphic. PolyJet makes one-off customization affordable at a scale that traditional manufacturing can't match.

---

## Next steps

Planned improvements, focused on the base mount:

- A stronger hold
- More mounting styles
- A better ratcheting mechanism, or a set screw
- A grippier base to prevent slipping and rotating

---

## Repository contents

```
light-buddy/
├── README.md
├── cad/        STEP + STL files for each part
├── docs/       Assembly drawing (and CDR slides)
└── images/     Photos, renders, and animations used above
```

## Team

Tran Gia Huy Pham · Robert Lopez · Leonardo Valenti
