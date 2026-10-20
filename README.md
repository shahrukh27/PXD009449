<div align="center">

# PXD009449
### A processed MS/MS dataset for modified peptide evaluation

[![Source PRIDE](https://img.shields.io/badge/Source-PRIDE-3876BB)](https://www.ebi.ac.uk/pride/archive/projects/PXD009449)
[![Related MS thesis](https://img.shields.io/badge/Related-MS_thesis-8062AB)](https://github.com/shahrukh27/MS-Thesis)
[![Pipeline](https://img.shields.io/badge/Pipeline-Data_Cleanup-blue)](#data) 
</div>

PXD009449 dataset was used in my [MS Thesis](https://github.com/shahrukh27/MS-Thesis.git). This dataset was used for p-value estimation of modified peptides using Generalized Pareto Distribution.  

PXD009449 MS/MS dataset was downloaded from the PRoteomics IDEntifications Database (PRIDE). This dataset was published as part of the study done by Zolg et.al. in 2018. It consisted of MS/MS spectrum of ~5000 synthetic peptides carrying 21 different post-translational modifications (PTMs) and their respective unmodified forms. The 21 PTMs performed on 4 target amino acids were as follows: 

| Amino Acid | Modification |
| :---: | :----: |
| Lysine | Acetylation |
| Lysine | Biotinylation |
| Lysine | Butyrylation |
| Lysine | Crotonylation |
| Lysine | Dimethylation |
| Lysine | Formylation |
| Lysine | Glutarylation |
| Lysine | GlyGlycylation |
| Lysine | Hydroxyisobutylation |
| Lysine | Malonylation |
| Lysine | Methylation |
| Lysine | Propionylation |
| Lysine | Succinylation |
| Lysine | Trimetylation |
| Arginine | Citrullination |
| Arginine | Dimethylation_asym |
| Arginine | Dimethylation_symm |
| Arginine | Methylation |
| Proline | Hydroxyproline |
| Tyrosine | Nitrotyrosine |
| Tyrosine | Phosphorylation |

MS/MS spectra were produced using Orbitrap Fusion ETD Mass Spectrometer. In this study, ~1.4 million MS/MS spectra (survey_R1) of Collision-induced dissociation (CID) and higher energy collisional dissociation (HCD) fragmentation methods were initially selected.
<a id="data"></a>
## :broom: Data Cleanup

[Data Cleanup Pipeline](assets/data_cleanup.png) | [Data Source](https://www.ebi.ac.uk/pride/archive/projects/PXD009449)

All the peptides present in the PXD009449 dataset were passed through a series of filtration steps:

* First step was to ensure that all selected synthetic peptides were present in the target protein database (UniProtKB). Human protein sequences were downloaded from UniProtKB database (release # 2022_05, Accession ID: [UP000005640](https://www.uniprot.org/proteomes/UP000005640)) on Dec 19th, 2022. Any peptide not found in target database was discarded.
* Second step was to remove peptides without target amino acid (Y, K, R, P).
* Third step was to remove peptides without MS/MS spectra mapping infomration in PXD009449 dataset's [supplemetary file](Data/137237_1_supp_136394_p8kmm9.csv).

These filtering steps reduced the numbers of peptides from ~5000 to 4090 peptides. In the PXD009449 dataset (CID and HCD, survey run), all MS/MS spectra with missing peptide mapping or ion information were removed. Spectrum against demethylation post-translational modification were removed due to data issues. 

Following table details the MS/MS counts before and after data cleanup:

[Final MS/MS Counts Details](assets/msms_counts.png)

[msms_info.csv](Data/msms_info.csv) file contains the relevant information of the filtered (final) spectrum. It has following columns:

- Scan: Scan number in the MS/MS run
- Fragmentation: fragmentation method used in the respective MS/MS run 
- PTM: respective PTM on a peptide 
- Mapped_Scan: Assigned scan number after filtering
- Peptide: Precusrsor peptide of MS/MS spectra
- PTM_Loc: Amino Acid number in the peptide seqeunce with the respective PTM

## :file_folder: Repository guide

| Path | Purpose |
| --- | --- |
| `Data/msms_info.csv` | Main processed-spectrum metadata index |
| `Data/137237_1_supp_136394_p8kmm9.csv` | Supplementary peptide information |
| `Data/msms_spectrums/` | Grouped spectrum archives and the phosphorylation download pointer |
| `assets/` | New figures, animations, and static alternatives |

## :open_book: Publication

Please cite the original dataset publication when using the ProteomeTools data:

Zolg, D. P., et al. (2018). **ProteomeTools: Systematic Characterization of 21 Post-translational Protein Modifications by Liquid Chromatography Tandem Mass Spectrometry (LC-MS/MS) Using Synthetic Peptides.** *Molecular & Cellular Proteomics*, 17(9), 1850–1863. [https://doi.org/10.1074/mcp.TIR118.000783](https://doi.org/10.1074/mcp.TIR118.000783)

The citation credits the source dataset study. The filtering and packaging documented in this repository are a separate contribution. Follow the original dataset's reuse terms; this documentation update does not introduce a new license for the data.

