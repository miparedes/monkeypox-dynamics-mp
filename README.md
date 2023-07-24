# mpox-dynamics:

## Early underdetected dissemination followed by extensive local transmission propelled the 2022 mpox epidemic and limited impact of vaccination 

Miguel I. Paredes<sup>1,2*</sup>, Nashwa Ahmed<sup>2,3</sup>, Marlin Figgins<sup>2,4</sup>, Vittoria Colizza<sup>5</sup>, Philippe Lemey<sup>6</sup>, John T. McCrone<sup>2</sup>, Nicola Müller<sup>2</sup>, Cécile Tran-Kiem<sup>2</sup>, Trevor Bedford<sup>1,2,7</sup>

### Affiliations
1 Department of Epidemiology, University of Washington, Seattle, Washington, USA
2 Vaccine and Infectious Disease Division, Fred Hutchinson Cancer Center, Seattle, Washington, USA
3 Molecular and Cellular Biology Program,  University of Washington, Seattle, WA, USA
4 Department of Applied Mathematics, University of Washington, Seattle, WA, USA
5 INSERM, Sorbonne Université, Institut Pierre Louis d’Epidémiologie et de Santé Publique   IPLESP, Paris, France
6 Department of Microbiology, Immunology and Transplantation, Rega Institute, KU Leuven, Leuven, Belgium
7 Howard Hughes Medical Institute, Seattle, WA, USA
* Corresponding author. Email: paredesm@uw.edu

### Abstract: 
The World Health Organization (WHO) declared mpox a public health emergency of international concern in July 2022. It is still unclear to what extent international travel contributed to the explosive spread of mpox and the degree to which national vaccination campaigns were responsible for controlling the epidemic. We built phylogeographic and phylodynamic models to analyze MPXV genomes sampled between March 2022 and January 2023 from five global regions together with air traffic and epidemiological data to analyze the global spread of mpox. Our models reveal community transmission prior to detection by local surveillance, changes in case-reporting throughout the epidemic, and a large degree of transmission heterogeneity. Additionally, we find that viral introductions played a limited role in prolonging spread after initial dissemination, suggesting that travel bans would have had only a minor impact. We find that the time-varying effective reproductive number in North America declines below one before more than 10% of individuals at high risk individuals in the USA had vaccine-induced immunity, suggesting little impact of vaccination in controlling the epidemic. Given that cases quickly declined after detection most likely due to behavioral modifications, our findings highlight the importance of broader routine specimen screening surveillance for emerging infectious diseases. 

------------

## Organization

This repository contains the analytic code needed to reproduce the results from the above paper. To start, begin with the folder `monkeypox_build` to run the maximum likelihood analysis and create the temporally resolved phylogeny of global mpox

To prep the data format for further analysis, run `./scripts/data_prep_region.sh`. If masking of invariant sites is needed for running DTA, run `scripts/masking.ipynb`.

Then `dta` and `mascot_glm` contains the necessary data to build your own XMLs via Beauti. For ease, the XMLs used in this project can be found in the folder labeled `xmls` for each respective analsis. The results used in this study can be found in `results` under the folder for each respective analysis. For storage size efficiency, every xml, log, and trees file has been compressed. To uncompress, use the following format:

`xz --decompress --keep 1000_dta_prev_subsampling_region.xml.xz`

To analyze the posterior set of trees and log files produced by each analysis, go to `scripts` for all analystic scripts

All Genbank IDs can be found in final_acknowledgements_genbank.csv along side information regarding originating and submitting labs. We thank the public health and sequencing labs from around the globe for their prompt sequencing and upload to Genbank.

Scripts and data to reproduce the analysis of the size distribution of clusters of identical mpox sequences can be found in the folder `/polytomy-analysis/`. Input files are available in the `data/` subfolder (including case counts and the distribution of the size of clusters of identical sequences). Scripts to reproduce results and figures are available in the `scripts/` subfolder.






