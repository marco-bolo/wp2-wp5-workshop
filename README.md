![status](https://img.shields.io/badge/expression_of_interest-13_September-green)
![registrations](https://img.shields.io/badge/registrations-50-purple)
<p align="center">
<img src="https://avatars.githubusercontent.com/u/128803255?s=280&v=4" alt="drawing" width="190" align="left"/>
</p>


# The MBO WP2/5 Data Analysis Challenge

Join the [EU Horizon MARCO-BOLO project](https://marcobolo-project.eu/) in comparing bioinformatics pipelines for analysing eDNA data by participating in the **DATA ANALYSIS CHALLENGE**.

In doing so, you will help improve recommendations for eDNA metabarcoding pipeline choice amongst the myriad of options out there and contribute towards the development of indicator workflows to report on biodiversity monitoring.

> Find a more detailed description of [the challenge](#the-challenge) and [the datasets](#the-datasets) below.


*What you do*

- :wrench:  Come with your favourite pipeline
- :computer:  Run it on one of our plankton or fish eDNA datasets
- :globe_with_meridians:  Send us your resulting OTU/ASV/ZOTU and Taxonomy tables

*What we do*

- :floppy_disk:  Provide the eDNA datasets (18S plankton time series and 12S/16S/COI aquarium samples) along with standardised reference libraries
- :bar_chart:  Compile and compare the resulting tables across participants' pipelines
- :memo:  Report and share these results back with the participants and on the MARCO-BOLO website


## Timeline of challenge

- **Extended until the 13th of September 2024**: Registration deadline. Datasets are shared with participants who expressed their interest to join.
- 30th of September 2024: Deadline for the submission of analysis results.
- 7th and 8th of October: Data comparison and indicator workflow development by MARCO-BOLO internally.
- Early November: MARCO-BOLO initial report.

## Registration form

Register your interest for the challenge using the [Registration form](https://docs.google.com/forms/d/e/1FAIpQLSfrSrlqA2TQKWda8ZRReNQ-AtB90eMF29MDgd8ZHk4ALKbA4w/viewform?usp=sf_link) before September 13th 2024.

*Why register to participate*

- You want your pipeline to be included in the comparison
- You like a challenge and want to see how your pipeline performs on new data
- You want to contribute towards better guidelines on pipeline choice and improved workflows for biodiversity monitoring
- You will be acknowledged for your contribution in eventual outputs

## The Challenge

> Read on for detailed information

In the context of MARCO-BOLO (https://marcobolo-project.eu/) we are testing different bioinformatic pipelines 
to optimise the pelagic habitat indicator workflows to report on biodiversity monitoring to the European Marine Strategic Framework Directive (MSFD). 
Currently, there is considerable variation in the analysis of environmental DNA (eDNA) data using bioinformatic pipelines. 
Also, there is no clear assessment of how these different pipelines and parameter choices therein affect the calculation of indicators. 

We are therefore inviting you to take part in our **DATA ANALYSIS CHALLENGE**, where we aim to compare different bioinformatics pipelines currently used for eDNA analysis across the eDNA community. In a follow up analysis, this will allow us to compare the effect of pipeline choice on the MSFD pelagic habitat indicator calculations. 

The goal of this challenge is to analyse the same datasets with different pipelines. **We will provide small datasets that can be run with your personal/favourite analysis method, and ask that you only return the final OTU/ASV tables and taxonomic information resulting from your analysis.**

Your participation will be acknowledged in the Marco-Bolo project reports and on the Marco-Bolo website. The final comparison will provide clear evidence on how robust and comparable current eDNA practices are, with the aim to increase our understanding of the method and the trust in the results. The datasets will also remain available for further comparisons, whenever new workflows are being developed.


## The Datasets

Based on your preference, you may choose to analyse one or more of the following datasets. The proposed datasets cover an 8-year time series of plankton protist communities in the Western English Channel identified with the 18S V4 region, and a punctual multi-marker (12S, 16S, COI) assessment of the fish communities inhabiting the Lisbon aquarium.

### Plankton 18S time series

This time series was collected to analyse patterns of plankton protist community succession off the French coast in the Western English Channel. Over the course of 8 years (2009-2016), bimonthly samples of 5 L of seawater were collected at 60m depth at the SOMLIT-Astan station (Roscoff, Western English Channel). The primers TAReuk454FWD1 and TAReukREV3 were used to amplify the V4 region of the 18S rRNa gene and to target most eukaryotic groups. This long-term, comprehensive dataset will allow us to explore how biodiversity indicators inform on the temporal structure of community changes.

- 185 samples collected over 8 years
- One primer pair: 

    V4 18S rRNA: TAReuk454FWD1 & TAReukREV3 ~380 bp (Stoeck et al., 2010)
- Reference library: please use the [PR2 reference sequence database](https://pr2-database.org) above version 5.0.0 

*[Data ownership: This dataset was published and made publicly available by [Caracciolo et al. 2022](https://doi.org/10.1111/mec.16539)]*

### Fish 12S/16S/COI aquarium dataset

This dataset consists of triplicate 5L water volumes collected from the Lisbon Aquarium (Oceanário de Lisboa). Extracted DNA was amplified with multiple primer pairs to target fish species using the 12S, 16S and COI genes. The existence of a reference list of species inhabiting the aquarium at the time of sampling allows to compare primer- and pipeline efficiency and accuracy not only across marker genes but also against the target list of species actually present.

- 9 samples (triplicate samples for each primer pair)
- 3 primer pairs:
  -  COl: Leray-Lobo ~ 313bp (Leray et al. 2013; Lobo et al. 2013)
  -  12S rRNA: MIFISHU-E ~170bp (Miya et al. 2015)
  -  16S rRNA: Fish16sF/D/ & 16s2R ~ 200bp (Berry et al. 2015)
-  Reference libraries: will be provided in fasta format

*[Data ownership: [A-Fish-DNA-Scan](https://sites.google.com/view/a-fish-dna-scan/project-outputs) and [ME-BARCODE](https://me-barcode.weebly.com) group at the University of Minho. By participating in this challenge, you agree to not use the dataset beyond this exercise. Contact: [Filipe Costa](fcosta@bio.uminho.pt)*

## Associated files and pipeline details

The datasets will be shared with registered participants directly. The data shared contains the demultiplexed files in fastq format. We will also share the necessary metadata files and primer sequences, as well as the reference libraries for each primer pair of the fish aquarium dataset in fasta format. 

In the meantime, the metadata and primer files can also be found under :file_folder: &nbsp;[**associated_files/**](https://github.com/marco-bolo/wp2-wp5-workshop/tree/master/associated_files)

When completing the analyses, we request that you share the necessary pipeline information by filling out the [Pipeline_metadata_eDNA_data_analysis_challenge.xlsx](https://github.com/marco-bolo/wp2-wp5-workshop/blob/main/Pipeline_metadata_eDNA_data_analysis_challenge.xlsx) template. Alternatively, you can also send us your script and associated parameter files directly.

## Acknowledgements

The MARCO-BOLO project is funded by the European Union under the Horizon Europe Programme, Grant Agreement No. 101082021 (MARCO-BOLO). Views and opinions expressed are however those of the author(s) only and do not necessarily reflect those of the European Union or the European Research Executive Agency (REA). Neither the European Union nor the granting authority can be held responsible for them.
UK participants in MARCO-BOLO are supported by the UKRI’s Horizon Europe Guarantee under the Grant No. 10068180 (MS); No. 10063994 (MBA); No. 10048178 (NOC).

## Contact and help

This challenge is jointly organised by WP2 and WP5 of MARCO-BOLO, with efforts lead by Hanneloor Heynderickx (WP5, VLIZ), Saara Suominen (WP2, OBIS/UNESCO), Daniel Morais (WP2, UiT) and Emilie Boulanger (WP2, OBIS/UNESCO).

You can direct your questions regarding the challenge to Emilie Boulanger at e.boulanger@unesco.org.

Please reach out if you get stuck at any stage of the challenge and we will help you as best we can.

