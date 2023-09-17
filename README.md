# PXD009449

Data source: https://www.ebi.ac.uk/pride/archive/projects/PXD009449 

PXD009449 dataset was part of study punlished in 2018 titled: Systematic characterization of 21 post-translational modification using synthetic peptides. It was based on the synthesis of ~5000 synthetic peptides with 21 different post-translational modifications (PTMs).

I used PXD009449 dataset in my MS Thesis (https://github.com/shahrukh27/MS-Thesis.git). Following steps were done in data pre-processing: 

![alt text](https://github.com/shahrukh27/PXD009449/blob/main/data_cleanup.png)

Human protein sequences were downloaded from UniProtKB database (release # 2022_05; https://www.uniprot.org/proteomes/UP000005640) on Dec 19th, 2022, using Accession ID: UP000005640. It consisted of 81,837 canonical proteins with ~25% reviewed and ~75% unreviewed entries from Swiss-Prot and TrEMBL respectively. PXD009449 MS/MS dataset was downloaded from the PRoteomics IDEntifications Database (PRIDE). This dataset was published as part of the study done by Zolg et.al. in 2018. It consisted of MS/MS spectrum of ~5000 synthetic peptides carrying 21 different post-translational modifications (PTMs) and their respective unmodified forms. The 21 PTMs were performed on 4 target amino acids: Lysine (K), Proline (P), Tyrosine (Y), Arginine (R). The 21 PTMs were: Lysine acetylation, biotinylation, butyrylation, crotonylation, dimethylation, formylation, glutarylation, hydroxyisobutyrylation, malonylation, methylation, propionylation, succinylation, trimethylation and glyglycylation (ubiquitination). Arginine citrullination, dimethyalation (symmetric/asymmetric), methylation. Hydroxyproline. Tyrosine nitration, phosphorylation. MS/MS spectra were produced using Orbitrap Fusion ETD Mass Spectrometer. In this study, ~1.2 million MS/MS spectra (survey_R1) of Collision-induced dissociation (CID) and higher energy collisional dissociation (HCD) fragmentation methods were initially selected.

All the peptides present in the PXD009449 dataset were passed through a series of filtration steps. First step was to ensure that all selected synthetic peptides were present in the target protein database (UniProtKB). Any peptide not found in target database was discarded. Second step was to remove peptides for which corresponding MS/MS spectra or PTM information was not available in PXD009449 dataset. These two filtering steps reduced the numbers of peptides from 5000 to 4090 peptides. In the PXD009449 dataset (CID and HCD, survey run), all MS/MS spectra with missing peptide mapping or ion information were removed. Spectrum against demethylation post-translational modification were removed as incorrect data files were present in the dataset. 

Following table details the MS/MS counts before and after data cleanup:

![alt text](https://github.com/shahrukh27/PXD009449/blob/main/msms_counts.png)

## Publication

DOI: 10.1074/mcp.tir118.000783, PubMed: 29848782, Des: Zolg DP, Wilhelm M, Schmidt T, Medard G, Zerweck J, Knaute T, Wenschuh H, Reimer U, Schnatbaum K, Kuster B. ProteomeTools: Systematic characterization of 21 post-translational protein modifications by LC-MS/MS using synthetic peptides. Mol Cell Proteomics. 2018
