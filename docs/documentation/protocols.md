# Protocols

---

<details>
<summary><b>1. In Silico Simulation of HIS1–Substrate Docking</b></summary>  
  <br>
  
- Perform molecular dynamics (MD) using GROMACS (AMBER99SB-ILDN, TIP3P water model):  
  - Energy minimization → 100ps NVT → 100ps NPT → 5ns production run.  
- Assess trajectory quality via RMSD, RMSF, and radius of gyration; confirm equilibration (~1ns).  
- Calculate per-residue solvent-accessible surface area (SASA) using gmx sasa; classify residues as exposed (>0.2nm²).  
- Construct a polypropylene (PP) decamer in Open Babel.  
- Perform Autodock Vina docking using the final MD structure as the receptor (search box = full surface).  
- Generate 20 poses; identify residue–ligand contacts within 4–6Å.  
- Exclude residues within 6Å of cofactors (Fe²⁺, 2-oxoglutarate; from PDB 8s7b), buried (low SASA), or highly flexible (RMSF > 0.25nm).  
- Use FoldX to compute ΔΔG per hydrophobic substitution; rank residues by mutational stability.

</details>

---

<details>
<summary><b>2. Sub-Cloning and Expression of HIS1</b></summary>
<br>
  
**Host:** *E. coli* BL21(DE3)  
**Plasmid:** pET28-A–HIS1  

- Inoculate 5mL LB + 5µL kanamycin from glycerol stock; incubate overnight (37°C, 200rpm).  
- Transfer 2mL to 200mL TB + 200µL kanamycin; grow (30°C, 180rpm) until OD₆₀₀ = 0.8–0.9.  
- Chill culture on ice (20 min).  
- Add cofactors: 2mM FeSO₄ and 6mM 2-oxoglutarate.  
- Induce with 0.4mM IPTG; incubate (20°C, 200rpm, 20h).  
- Harvest cells (10,000 × g, 20 min, 4°C); discard supernatant.  
- Store pellets at –20°C.

</details>

---

<details>
<summary><b>3. Mutant Library Synthesis</b></summary>
<br> 
  
#### 3.1 Two-Phase Mutagenesis Strategy
- Target residues: 110, 148, 268, 297, 304, 305, 307.  
- Use degenerate codon DTN for hydrophobic substitutions.  
- Two-phase mutagenesis planned to minimize library size (deferred due to screening delay).

#### 3.2 Vector Amplification
- Purify pET28-A using QIAprep Miniprep.  
- Digest with EcoRI and HindIII (1µL each, 1h).  
- Verify by 0.8% agarose gel; extract the target band.  
- Measure DNA concentration with Nanodrop.

#### 3.3 Site-Directed Mutagenesis

##### (a) Degenerate Codon Substitution (BsaI)
- Primers: PPase_Fs and PPase_Rs.  
- Run PCR → visualize on 0.8% agarose gel.  
- No visible bands → method discontinued.

##### (b) Mutant Megaprimer Method
- Design mutagenic primers with DTN codon (Tm = 60°C).  
- Perform asymmetric PCR (100:1 primer ratio; 35 cycles, 65°C annealing).  
- Run symmetric PCR as a control.  
- Digest products with DpnI (1µL); purify (Promega Wizard® kit).  
- Pool and concentrate 6 × 50µL reactions; measure DNA concentration.  
- Generate full-length genes using mutant megaprimers as reverse primers.  
- Digest (EcoRI + HindIII, 1h), purify, verify by gel, and quantify DNA.

#### Primer Sequences
| **Purpose**                  | **Primer Name** | **Primer Sequence**                               |
|------------------------------|-----------------|---------------------------------------------------|
| **Cloning (non-mutagenic)**  | PPase_F         | ACTGGAATTCCCTGGTGCCACGCG                          |
|                              | PPase_R         | CTAAATACGCAGGCTATCAATATAGCGTTC                   |
| **Combinatorial mutagenesis** | PPase_110_F     | CGCAAACAGAAATTCAGC**dtn**CTGATCGATGGCAAGAAC          |
|                              | PPase_148_F     | CGTGTGGAACCGAAA**dtn**GAACAGGATCTGGCATTTTG           |
|                              | PPase_268_F     | CTGCTGATTAATCTGGGT**dtn**ACAATGGAAGTTATGTGC          |
|                              | PPase_297_F     | GAAAAAGAACGTATTAGCCTG**dtn**ATGCTGTATAGCGTGAATG      |
|                              | PPase_304_F     | CAATGCTGTATAGCGTGAAT**dtn**GAGAAAGATATTGAACCTGCC     |
|                              | PPase_305_F     | GCTGTATAGCGTGAATGAT**dtn**AAAGATATTGAACCTGCCG        |
|                              | PPase_307_F     | GTATAGCGTGAATGATGAGAAA**dtn**ATTGAACCTGCCGC          |
| **Single-site mutagenesis**  | PPase_Fs        | atcGGTCTCttcagc**dtn**CTGATCGATGGCAAGAACTTT          |
|                              | PPase_Rs        | ATCggtctcGCTGAATTTCTGTTTGCGTTC                   |


</details>

---

<details>
<summary><b>4. Ligation, Transformation, and Sequencing</b></summary>

**Ligation:**
- Set up 20µL reactions with T4 DNA ligase (+/– insert, +/– ligase controls).  
- Incubate 1h at room temperature.

**Transformation:**
- Mix 10µL ligation mix + 100µL competent *E. coli*.  
- Controls:  
  - Positive: 50µL cells + 1µL template DNA.  
  - Negative: 50µL cells only.  
- Ice (15 min) → Heat shock (42°C, 1 min) → Ice (1 min).  
- Add 250µL SOC; incubate (37°C, 1 h).  
- Plate 50µL onto LB agar; incubate overnight (37°C).

**Sequencing:**
- Send 6 colonies (+L+I plates) for Sanger sequencing using PPase_F/R primers.

</details>

---

<details>
<summary><b>5. HIS1 Protein Purification</b></summary>
<br>
  
- Lysis buffer: 20mM Tris-HCl, 100mM NaCl, 2.5mM MgCl₂, 0.5mM CaCl₂  
- Binding buffer: 20mM Tris-HCl, 0.1mM MgCl₂  
- Wash buffer: 20mM Tris-HCl, 10mM Imidazole, 200mM NaCl, 0.1mM MgCl₂  
- Elution buffer: 20mM Tris-HCl, 500mM Imidazole, 50mM NaCl, 0.1mM MgCl₂  
<br>

- Resuspend pellet in 20mL BugBuster®; incubate 30 min (RT).
- Centrifuge (40,000 × g, 30 min, 4°C); retain supernatant.  
- Equilibrate Ni-Sepharose column with 30mL water → 30mL binding buffer.  
- Load lysate; collect flow-through.  
- Wash with 10mL wash buffer until A₆₀₀ ≈ 0.  
- Elute with elution buffer (1mL fractions) until A₆₀₀ ≈ 0.  
- Pool fractions with the highest absorbance; quantify protein.  
- Clean column (Tris + Imidazole → MilliQ → 20% EtOH).  
- Concentrate pooled elution with Vivaspin® to ≤ 0.5mL; exchange into HEPES buffer (repeat until Imidazole < 3mM).  
- Verify by SDS-PAGE.

</details>

---

<details>
<summary><b>6. Polypropylene Degradation Assay</b></summary>
<br>
  
- Lyse cells in BugBuster® (30 min, RT) → centrifuge (40,000 × g, 30 min, 4°C).  
- Discard pellet; incubate supernatant with 5mg polypropylene, 2mM FeSO₄, 6mM 2-oxoglutarate in pH 7 buffer at 30°C.  
- Replace enzyme + cofactors every 24h.

</details>

---

<details>
<summary><b>7. KMnO₄ Oxidation of Polypropylene</b></summary>
<br>
  
- Clean samples (acetone + ethanol, ultrasonic bath); dry 50°C, 1h.  
- Treat with 0.5M HCl / 0.25M KMnO₄ at 45°C for 2–8h.  
- Rinse with water until colorless.  
- Remove MnO₂ deposits using a 12M HCl rinse.

</details>

---

<details>
<summary><b>8. Colorimetric Quantification of Surface Carboxyl Groups (PV-Ni Assay)</b></summary>
<br>
  
**Reagents:** Pyrocatechol violet (PV), Ni²⁺, 10mM HEPES pH 7  
<br>

- Rinse samples thoroughly with HEPES buffer.  
- Incubate plastics with 400µM Ni²⁺ in 10mM HEPES (25°C, 2 min).  
- Transfer liquid → add PV (final concentration = 40µM).  
- Measure absorbance at 650nm.  
- Controls: KMnO₄-oxidized (positive), untreated PP (negative).  
- Adapted for 96-well PP plates (transfer to flat-bottom plates for reading).  
<br>
  
- *LOD* = (3.3 × s_blank) / m  
- *LOQ* = (10 × s_blank) / m  

</details>

---

<details>
<summary><b>9. Toluidine Blue O (TBO) Staining to Quantify Surface Organic Compounds</b></summary>
<br>
  
- Treat PP microtubes with enzyme solutions (HIS1/EV + cofactors) at 30°C for 48h.  
- Ultrasonically clean (1% SDS → water → 75% EtOH); dry at ~50°C 1h.  
- Incubate in 0.1% TBO / 1mM NaOH (40°C, 15 min, 250rpm).  
- Wash in 1mM NaOH until supernatant is clear (~4×).  
- Desorb dye with 20% SDS (40°C, 30 min, 250rpm).  
- Measure absorbance at 630nm.  
- Adaptable to KMnO₄-treated 96-well plates (same steps).

</details>

---

<details>
<summary><b>10. Surface Contact Angle (SCA) Measurement</b></summary>
<br>
  
- Clean PP pieces (70% EtOH → water); dry (55°C, 1h).  
- Measure initial contact angles using 7µL water droplets (2 min per run).  
- Treat plastics with HIS1 or EV lysate (overnight) or KMnO₄ (4–8h).  
- Post-treatment cleaning: sonicate in 1:10 IPA + water (3 min), wash (EtOH + water), dry (55°C).  
- Re-measure daily for 5 days (replace reaction mixture every 24h).

</details>

---

<details>
<summary><b>11. FTIR Analysis</b></summary>
<br>
  
- Clean 1cm × 1cm PP films (1% SDS → water → EtOH); dry (50°C, 1h).  
- Perform FTIR (Dr. Simone Dimartino’s lab, Bioengineering, UoE).

</details>

---

<details>
<summary><b>12. AFM Analysis</b></summary>
<br>
  
- Prepare 6mm PP discs; treat with buffer, HIS1, HIS1 lysate, or EV lysate.  
- Clean (1% SDS → water → EtOH); dry (50 °C, 1 h).  
- Acquire AFM images at 1 µm and 10 µm scales (1 Hz scan, 256 × 256 pixels).  
- Analyze surface roughness and thickness.

</details>

---

<details>
<summary><b>13. GC-MS Analysis</b></summary>
<br>
  
- Treat 5mg PP films with purified HIS1 or HEPES control (72h, 30°C); replace mixtures daily.  
- Pool reactions; add 3:1 cold methanol, incubate on ice (30 min).  
- Centrifuge (12,000rpm, 30min, 4°C); collect supernatant.  
- Add 10% DCM; inject 1µL onto DB-5ms column (40m × 250µm × 0.25µm).  
- Carrier: helium (1mL/min), 70eV ionization.  
- Analyse chromatograms and identify peaks via NIST library.

</details>

---

<details>
<summary><b>14. TLC Analysis of HPP Breakdown</b></summary>
<br>
  
- Prepare 300µL HIS1/EV lysates and 0.5mg/mL pure HIS1/HEPES reactions (2mM FeSO₄, 6mM 2-oxoglutarate, 6mM HPP or no HPP as control).  
- Incubate 30°C, 24h.  
- Spot samples on silica gel TLC plates.  
- Run in ethyl acetate:hexane:acetic acid = 70:30:2.  
- Air dry; visualize under UV light.

</details>

---


