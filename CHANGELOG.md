# Changelog

All notable changes to the Phospho Proteoform Calculator will be documented in this file.

## [1.1.0] - 2026-02-06

### Added
- Side-by-side layout: spectrum on left (2/3 width), phosphorylation sites on right (1/3 width)
- Auto-load random protein on startup for immediate demonstration
- User guidance hint text above controls
- Improved peak label positioning to prevent overlaps
- Version history section in README

### Changed
- Tighter zoom range: 1 kDa (from 2 kDa) for better centering of phosphorylation states
- Compact interface: reduced header size, condensed site controls
- Removed "Simulate. Visualize. Learn." tagline
- Updated subtitle: "mass spectrometry" instead of "in native mass spectrometry"
- Removed "Protein Presets:" label from controls
- Changed "Random" button to "Random Protein"
- Reorganized layout: grey separator now between presets/spectrum and protein controls
- Spectrum aspect ratio increased to 65% for taller display

### Fixed
- Peak labels (P3, P4, etc.) no longer overlap when close together
- Site controls initialization error on startup
- Peak label alternating logic now properly tracks previous position

### Technical
- Improved responsive CSS for tablets and phones
- Optimized site control spacing and styling
- Better mobile adaptation with vertical stacking

## [1.0.0] - 2026-02-04

### Added
- Initial release
- AMPK protein presets (α1, β1, γ1, complex)
- Random protein generator
- Combinatorial phosphorylation simulation (2^10 = 1024 states)
- Isotope distribution modeling (Averagine model)
- Adjustable resolving power (1k-500k FWHM)
- Peak shape presets (All 50%, Gradient, Bimodal, Reset)
- Main phosphorylation slider (0-10P)
- Individual site controls
- Automatic peak annotations
- Data export (PNG spectrum, CSV data)
- MIT License
- Comprehensive documentation
