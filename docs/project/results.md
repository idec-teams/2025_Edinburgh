# Results

### Directed Evolution and Computational Analysis

Molecular dynamics and docking simulations of the enzyme HIS1 with PP identified several surface-exposed residues as potential mutation targets to enhance substrate binding. FoldX-based mutational stability screening suggested seven key sites (N110, E148, A297, D304, E305, D307) with favourable ΔΔG values below -0.15, indicating potential structural stability upon substitution with hydrophobic residues. Due to screening capacities and time restraints, we identified the degenerate codon DTN to be optimal for our experiments, as it yields an array of four hydrophobic residues (I, V, L, and F) and a stop codon.

### Library Generation

To efficiently minimize library size, a dual-screen approach was adapted. Single-site mutants were intended for initial screening, followed by combinatorial mutagenesis of beneficial variants. To generate site-directed mutations, we adapted a protocol for combinatorial library generation to create single-site mutants [^1]. This strategy was chosen as it would facilitate both single-site and combinatorial mutagenesis. However, sequencing of transformed colonies confirmed the presence of the gene but not the intended N110 mutation, halting further library construction.

---

### Evaluation of Enzymatic Activity

#### Thin-Layer Chromatography (TLC)
TLC analysis of HIS1 (in lysate and purified form) incubated with HPP showed no detectable enzymatic activity. HPP spots remained unchanged compared to the controls, indicating no substrate conversion.

#### Gas Chromatography-Mass Spectrometry (GC-MS)

Comparison of untreated and HIS1-treated PP samples showed similar chromatographic profiles. No expected oxidation products, including: 2-Pentene, Undecane, Dodecane, 3-Methyl-5-propylnonane, 2,6,10-Trimethyltridecane, and 2,6,10,14-Tetramethylpentadecane [^2] were seen in the sample. The main detected compound, 9-octadecenamide, appeared in both samples, suggesting it is not a product of enzymatic breakdown but a contaminant or a product of previous treatment during manufacturing. The method was limited by the potential loss of polar oxidation products during extraction and their possible retention on the polymer surface.

#### Atomic Force Microscopy (AFM)

AFM imaging revealed increased surface roughness on PP films treated with purified HIS1, while HIS1 lysate and control treatments showed no significant differences. The observed changes may indicate surface interaction or coating by protein, but not necessarily substrate oxidation or degradation.

#### Fourier Transform Infrared Spectroscopy (FTIR)

FTIR spectra of HIS1-treated samples showed no detectable oxidation peaks compared to oxidised KMnO₄ controls. The characteristic PP bands were unchanged, suggesting minimal to no chemical modification of the surface by HIS1 under the tested conditions.

--- 

### High-Throughput Assay Development

#### Toluidine Blue O (TBO) Assay

A colorimetric assay using Toluidine Blue O successfully distinguished between untreated and chemically oxidised PP microtubes, with approximately a 20-fold higher absorbance in oxidized samples. While effective in microtube format, the assay showed inconsistent results in 96-well plates, likely due to dye degradation, requiring further optimisation for high-throughput use.

#### Nickel-Pyrocetechol Violet (Ni-PV) Assay

A secondary colorimetric assay quantified surface carboxyl groups via Ni²⁺ binding. KMnO₄-treated PP tubes showed reduced absorbance, consistent with surface oxidation, but statistical significance was marginal (p ≈ 0.058 after Welch’s correction). The assay detection limit was estimated at ~0.064 µmol·cm⁻² of carboxyl groups. No measurable oxidation was detected on HIS1-treated samples, suggesting enzyme inactivity or sub-threshold surface modification.

--- 

### Summary

Overall, computational modeling identified seven potential mutation targets for HIS1 aimed at improving PP binding. Experimental mutagenesis efforts partially succeeded in producing single-site mutants, through confirmed substitutions were not achieved. Enzymatic assays and analytical techniques (TLC, GC-MS, AFM, FTIR) showed no definitive evidence of HIS1 activity against polypropylene. Two colorimetric assays for detecting PP surface oxidation were developed and validated for positive controls, but HIS1-treated samples produced no measurable oxidation under current conditions.

 

[^1]: (Sadler et al., 2018)
[^2]: (Tan et al., 2024)
