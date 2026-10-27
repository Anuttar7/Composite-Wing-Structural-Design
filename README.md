# Composite Wing Structural Design

**Preliminary Design Review**

A preliminary analytical structural design of a composite wing-box for a light, low-speed aircraft. The project connects idealised aerodynamic loading to structural sizing using beam theory, Classical Laminate Theory (CLT), and thin-walled closed-section relationships.

## Project overview

The aim is to establish first-order estimates of the loads, stiffness requirements, and dimensions of the wing's primary load-carrying structure. The wing is represented as a straight, untwisted rectangular planform, and the analysis is performed on one semi-span.

The work covers:

- Idealised spanwise lift distribution and derivation of shear-force, bending-moment, and torsional-moment distributions.
- Wing-box geometry based on the NACA 2412 airfoil.
- Composite laminate stiffness calculations using the \(A\), \(B\), and \(D\) matrices.
- Preliminary sizing of spar caps, spar webs, skins, and ribs.
- First-order evaluation of bending stiffness, torsional rigidity, and shear-driven panel stability.
- Discussion of likely failure modes and limitations of the simplified model.

## Aircraft and wing configuration

| Parameter | Value |
|---|---:|
| Maximum take-off mass (MTOW) | 580 kg |
| Aircraft weight used in calculations | 5,680 N |
| Wingspan | 11 m |
| Semi-span | 5.5 m |
| Wing area | 13.5 m² |
| Aspect ratio | 9 |
| Mean chord | 1.23 m |
| Airfoil | NACA 2412 |
| Positive limit load factor | +3.8 |
| Negative limit load factor | −1.52 |
| Ultimate load factor | 5.7 |

The lift distribution is approximated as elliptical. Positive manoeuvre loading is treated as the primary case for preliminary stiffness sizing, while ultimate loading is used for strength-oriented checks.

## Methodology

### 1. Aerodynamic load modelling

An elliptical spanwise lift distribution is used to estimate the distributed aerodynamic load. Integrating this load gives the spanwise shear force and bending moment. Torsion is estimated from the offset between the aerodynamic centre and the assumed shear centre.

### 2. Wing-box idealisation

The wing-box is treated as a thin-walled, closed section comprising:

- **Spar caps** — primarily resist bending through axial tension and compression.
- **Spar webs** — primarily carry shear.
- **Upper and lower skins** — contribute to torsional rigidity and load distribution.
- **Ribs** — maintain the cross-sectional shape and help control panel stability.

The front and rear spars are assumed to lie at approximately 25% and 65% of chord, respectively.

### 3. Composite laminate mechanics

Classical Laminate Theory is used to transform the stiffness of individual plies and assemble the laminate \(A\), \(B\), and \(D\) matrices. Effective in-plane properties are then used for preliminary component sizing.

### 4. Structural sizing

Beam theory is used to estimate the required bending stiffness from a wing-tip deflection constraint. The spar caps are sized to provide the required second moment of area. Thin-walled closed-section theory is used to estimate torsional rigidity, and a simplified shear-based relationship is used to estimate rib spacing.

## Selected results

The report gives the following preliminary sizing results:

| Quantity | Reported value |
|---|---:|
| Spar-cap thickness | 4 mm |
| Spar-web thickness | 4 mm |
| Skin thickness | 2 mm |
| Front spar-cap width | 0.2747 m |
| Rear spar-cap width | 0.1831 m |
| Rib spacing | 0.1080 m |
| Bending stiffness, \(EI\) | \(1.739 \times 10^6\) N·m² |
| Torsional rigidity, \(GJ\) | \(5.897 \times 10^5\) N·m² |
| Spar-cap effective modulus | \(1.12 \times 10^{11}\) Pa |
| Skin effective modulus | \(1.69 \times 10^{10}\) Pa |
| Wing-root shear force | \(1.081 \times 10^4\) N |
| Wing-root bending moment | \(2.523 \times 10^4\) N·m |

The analysis identifies bending as the dominant global loading effect, with the largest bending moment at the wing root. The report identifies fibre-direction failure in the spar caps as the principal failure mechanism considered; matrix and shear failure are discussed as secondary mechanisms in the preliminary assessment.

## Assumptions and limitations

This is a **preliminary analytical design study**, not a certified or flight-ready structural design. The analysis uses simplifying assumptions, including:

- Elliptical lift distribution on a rectangular wing.
- Straight, untwisted wing geometry without taper or sweep.
- Classical beam theory for global structural response.
- Linear-elastic composite material behaviour represented through laminate theory.
- Idealised load transfer between structural components.
- Neglect of local stress concentrations, detailed local buckling, and aeroelastic coupling.

The reported sizing and conclusions should therefore be treated as preliminary estimates. They require independent verification before being used for detailed engineering decisions.

## Future work

Potential extensions identified in the report include:

- Local buckling analysis of skin panels and spar webs.
- Composite failure assessment using criteria such as Tsai–Wu or Hashin.
- Finite-element modelling to validate the analytical results.
- Aeroelastic analysis of coupled structural and aerodynamic behaviour.
- Optimisation of the laminate stacking sequence.

## Repository contents

The accompanying report includes the design assumptions, derivations, results, plots, and code listings for the laminate stiffness matrices and wing-box analysis. Adapt this section to match the actual files committed to the repository.

A suggested layout is:

```text
.
├── README.md
├── Report.pdf
├── Code.mlx
└── data/
    ├── datasheet_sparcap.xlsx
    ├── datasheet_skin.xlsx
    └── datasheet_sparweb.xlsx
```


## Running the code

The report contains MATLAB-style function listings for the laminate stiffness calculations and wing-box analysis. To make the scripts reproducible on another machine:

1. Place the source files and material datasheets in the project directory.
2. Update any file paths so they are relative to the repository rather than tied to a particular computer.
3. Run the laminate stiffness calculations for the spar caps, skins, and spar webs.
4. Run the wing-box analysis to calculate the load distributions and preliminary sizing outputs.

The report's code references local spreadsheet paths. Those paths must be changed before the code can run on another machine. The exact entry-point script and required MATLAB version should be documented once confirmed from the repository.

## Author

**Anuttar Jain**

*Composite Wing Structural Design — Preliminary Design Review (PDR++), 14 April 2026.*

## Disclaimer

This repository documents an academic preliminary design exercise. The calculations rely on idealisations and have not been presented here as a fully validated, certified aircraft structure. Verify equations, inputs, implementation, and results independently before reusing them.
