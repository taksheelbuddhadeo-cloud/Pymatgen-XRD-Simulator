# Pymatgen-XRD-Simulator
# Automated Materials Project & Powder XRD Simulation Pipeline

![Python](https://img.shields.io/badge/Python-3.10%2B-blue)
![Pymatgen](https://img.shields.io/badge/pymatgen-2026.9%2B-green)
![Materials Project](https://img.shields.io/badge/API-mp--api-orange)
![License](https://img.shields.io/badge/License-MIT-lightgrey)

## Scientific Abstract
Determining phase stability and characterizing crystal structures are foundational steps in computational metallurgy and materials science. This Python command-line pipeline interfaces with the **Materials Project API (`mp-api`)** to query polymorphs of a target chemical formula, automatically isolating the thermodynamically most stable ground-state structure ($\min E_{\text{hull}}$). Using **`pymatgen`**, the tool transforms primitive cells into conventional standard crystallographic settings via `SpacegroupAnalyzer` and simulates powder X-ray Diffraction (XRD) patterns using $\text{Cu-K}\alpha$ radiation, outputting publication-grade diffractograms annotated with Miller indices $(hkl)$.

## Key Features
* **Thermodynamic Filtering:** Queries Materials Project summary documents and automatically selects the polymorph with the lowest energy above the convex hull ($E_{\text{hull}}$).
* **Symmetry & Cell Standardization:** Converts stored primitive cells into conventional standard cells (`symprec=0.01`) to report accurate space groups, crystal systems, lattice parameters ($a, b, c, \alpha, \beta, \gamma$), cell volumes, and theoretical densities.
* **Powder XRD Simulation:** Computes $2\theta$ reflection positions, interplanar $d$-spacings, and scaled relative intensities across customizable angular ranges using $\text{Cu-K}\alpha$ ($\lambda \approx 1.54184\text{ \AA}$) radiation.
* **Publication-Quality Plotting:** Renders high-resolution (`300 DPI`) diffractograms styled with serif LaTeX typography and automated $(hkl)$ peak labeling for dominant reflections.

## Installation & Dependencies

Clone the repository and install the required scientific computing packages:

```bash

export MP_API_KEY="your_api_key_here"


git clone [https://github.com/](https://github.com/)<your-username>/mp-xrd-simulator.git
cd mp-xrd-simulator
pip install mp-api pymatgen matplotlib numpy
