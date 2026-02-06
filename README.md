# Phosphorylation Proteoform Calculator

[![Version](https://img.shields.io/badge/version-1.0.0-blue.svg)](https://github.com/Boriz4k/phospho-calculator-html/releases)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

Interactive web-based tool for simulating phosphorylation state distributions and their resulting deconvoluted mass spectra in native mass spectrometry.

**Try it live:** [https://Boriz4k.github.io/phospho-calculator-html](https://Boriz4k.github.io/phospho-calculator-html)

## Overview

The Phosphorylation Proteoform Calculator models how combinatorial phosphorylation patterns create distinct mass spectral signatures. Users can adjust individual site occupancies or overall phosphorylation levels and visualize the resulting proteoform distributions in real-time.

This tool is designed for education and experimental design in native mass spectrometry and top-down proteomics, allowing researchers to predict and interpret complex phosphorylation patterns before or alongside their experiments.

## Features

- Real-time simulation of combinatorial phosphorylation patterns across 10 sites
- AMPK protein presets with experimentally-determined phosphorylation extents (α1, β1, γ1 subunits and α1β1γ1 complex)
- Isotope distribution modeling using the Averagine model for realistic mass spectra
- Adjustable resolving power (1k-500k FWHM) to simulate different MS instruments (TOF, Orbitrap, FT-ICR)
- Interactive controls for average total phosphorylation (0-10P) or individual site-specific ratios
- Peak shape presets (uniform, gradient, bimodal patterns)
- Data export: Download spectrum as PNG (1600×800) or export peak data as CSV
- Automatic peak annotations (P0, P1, P2, etc.)
- Responsive design - works on desktop, tablet, and mobile
- No installation required - runs entirely in the browser

## Development History

This calculator evolved from an Excel-based prototype with multiple interconnected worksheets that demonstrated the underlying algorithm but was extremely slow and cumbersome to use. The Excel version had tabs for mass calculations, combinatorial event generation (2^10 = 1024 states), probability calculations, and spectrum visualization, but updating parameters required waiting for extensive recalculations.

The current web-based version was developed using AI-assisted programming (Claude, Anthropic) to translate the Excel logic into efficient JavaScript with real-time interactivity. This development approach - sometimes called "vibe coding" - allowed rapid iteration on the user interface and algorithm optimization while maintaining the validated mathematical framework from the original Excel implementation.

The tool is validated against experimental data presented in Krichel et al. (2025), which provides the AMPK phosphorylation site occupancies used in the protein presets. This publication demonstrates the real-world applicability of the simulation approach for interpreting complex native mass spectrometry data.

## Use Cases

**Education:** Understand how combinatorial post-translational modifications create complex mass spectral patterns. Visualize how individual site occupancies contribute to overall proteoform distributions.

**Experimental Design:** Predict whether your instrument's resolving power can distinguish between adjacent phosphorylation states (e.g., P5 vs P6) for a given protein mass.

**Data Interpretation:** Model expected spectral patterns for your protein of interest and compare with experimental native MS data.

**Publication Figures:** Export high-resolution spectra for manuscripts and presentations.

## Scientific Background

### Algorithm

The calculator simulates all 2^10 = 1024 possible phosphorylation states:

1. Generate all combinatorial phosphorylation patterns (binary states across 10 sites)
2. Calculate probability of each state from individual site occupancies (product of site ratios)
3. Aggregate states by total phosphorylation number (0P, 1P, 2P...10P)
4. Generate mass spectrum with:
   - Phosphorylation mass shift: +79.9799 Da per site
   - Isotope distribution: Averagine model (C4.93H7.76N1.36O1.48S0.04 per 111.13 Da)
   - Peak width: Resolving power-dependent (FWHM = mass/RP)

### Assumptions

- Independent phosphorylation events at each site
- Substoichiometric phosphorylation (0-100% occupancy per site)
- Deconvoluted mass spectrum (charge states already resolved)
- Gaussian peak shapes

## Quick Start

### Online Version (Recommended)
Visit: [https://Boriz4k.github.io/phospho-calculator-html](https://Boriz4k.github.io/phospho-calculator-html)

### Local Version
1. Download `index.html` from this repository
2. Open in any modern web browser
3. No installation or dependencies required

## How to Use

**Basic Workflow:**
1. Select a protein from the AMPK presets (or use Random Protein)
2. Adjust phosphorylation using the main slider (0-10P)
3. View the spectrum with all proteoform peaks labeled
4. Export data as PNG or CSV

**Advanced Controls:**
- Individual sites: Adjust each phosphorylation site independently in "Advanced Peak Shape" section
- Peak shapes: Try preset patterns (All 50%, Gradient, Bimodal)
- Protein mass: Enter custom protein mass (Da)
- Resolving power: Simulate different MS instruments

**AMPK Protein Presets:**
- α1 (64.7 kDa): 10 phosphorylation sites
- β1 (30.4 kDa): 5 sites including S23/24, S96, S101, S108, T148
- γ1 (37.6 kDa): 1 site (S9)
- α1β1γ1 complex (132.6 kDa): Full heterotrimer

## Technical Details

- Frontend: Pure HTML5/JavaScript (single file, no frameworks)
- Visualization: Plotly.js (loaded from CDN)
- File size: ~150 KB
- Browser compatibility: Chrome, Firefox, Safari, Edge (last 2 versions)
- Performance: Real-time rendering with <100ms update time

## Citation

If you use this tool in your research, please cite:

```bibtex
@software{krichel2025phosphocalc,
  author = {Krichel, Boris and others},
  title = {Phosphorylation Proteoform Calculator},
  year = {2025},
  version = {1.0.0},
  url = {https://github.com/Boriz4k/phospho-calculator-html}
}
```

**Plain text:**
Krichel et al. (2025). Phosphorylation Proteoform Calculator (Version 1.0.0). https://github.com/Boriz4k/phospho-calculator-html

## Related Publication

The AMPK phosphorylation site occupancies used in this tool are derived from:
AMPK Phosphorylation Proceeds Through Hierarchical Proteoform Cascades Revealed by Integrated Mass Spectrometry
Krichel et al., bioRxiv (2025). (https://doi.org/10.1101/2025.10.10.681638 )
## License

MIT License - see [LICENSE](LICENSE) file for details.

Free to use for academic and commercial purposes. Modification and distribution permitted with attribution.

## Contributing

Contributions welcome via GitHub Issues or Pull Requests.

**Potential improvements:**
- Custom protein input (mass + number of sites)
- Additional PTMs (acetylation, methylation, ubiquitination)
- Charge state simulation (m/z view)
- Comparison mode (overlay multiple proteins)
- Save/load configurations

## Authors

Boris Krichel and collaborators  
Centre for Structural Systems Biology (CSSB)  

Developed as part of ERC-funded research on metabolic regulation via AMPK phosphorylation networks.

## Acknowledgments

- Plotly.js for interactive visualization
- AMPK phosphorylation data from experimental native mass spectrometry (Krichel et al. 2025)
- Averagine model from Senko et al. (1995)
- AI-assisted development using Claude (Anthropic)

## Contact

For questions or collaborations:
- GitHub Issues: [https://github.com/Boriz4k/phospho-calculator-html/issues](https://github.com/Boriz4k/phospho-calculator-html/issues)

---

**Version 1.0.0** | Last updated: February 2026
