# Additional information

## Information session

The recording of the information session on 09/09/2024 can be found [here](https://drive.google.com/file/d/1uNhEQHV1QBlr67V7EtPGTL2ppzsYjXbw/view?usp=sharing).

The slides presented during the information session on 09/09/2024 can be found [here](https://drive.google.com/file/d/1yKpLjbyMEVaCwLxfboPzVGOOsC3gmmh_/view?usp=sharing).

## Answers to questions raised at the information session
 - [What preprocessing has been done to the data?](#what-preprocessing-has-been-done-to-the-data)
   - [Plankton 18S dataset](#for-the-plankton-18s-time-series)
   - [Aquarium COI/12S/16S datasets](#for-the-aquarium-coi12s16s-datasets)
 - [What can explain the sequence length variation?](#some-variation-in-sequence-length-was-noticed-especially-for-the-aquarium-datasets-12scoi16s)
 - [Were samples collected in the same location?](#were-samples-collected-in-the-same-location)
 - [Aquarium COI/12S/16S datasets - Resident species](#aquarium-coi12s16s-datasets---resident-species)
 - [Aquarium COI/12S/16S datasets - Potential contaminants](#aquarium-coi12s16s-datasets---potential-contaminants)
 - [Aquarium COI/12S/16S datasets - Two 12S primers](#aquarium-coi12s16s-datasets---why-were-two-primers-used-for-12s)
 - [Aquarium COI/12S/16S datasets - Reference libraries target taxa](#do-the-reference-database-for-the-aquarium-datasets-contain-only-the-target-species-only-fish-species-or-also-outgroups-eg-crustaceans)
 - [Aquarium COI/12S/16S datasets - Reference libraries lineages](#is-it-possible-to-add-the-lineage-to-the-species-names-of-the-reference-libraries)

### What preprocessing has been done to the data?
#### For the plankton 18S time-series

Sequenced 2x250 bp. Demultiplexing has been done and the primer tags (+/- 12 bp) were removed during demultiplexing.
Primers are still attached, no trimming or other processing has been done. The amplicon reads should all have the same length, around 250bp. Maybe a few base pairs variation because of the primer tag removal.


Details about the demultiplexing of the 18S plankton data can be found at [https://gitlab.sb-roscoff.fr/somlit-astan-metab/demultiplexing/18s-v4-ena-submission](https://gitlab.sb-roscoff.fr/somlit-astan-metab/demultiplexing/18s-v4-ena-submission) 

`Importantly` the runs of the 18S dataset are mixed-orientated. This means that the R1 file will have a mix of forward and reverse reads (~50% each), and the R2 file will also have a mix of forward and reverse reads (~50% each). This is due to the way the library was prepared. 

The [pipeline used in the original study](https://doi.org/10.5281/zenodo.5791089) details the demultiplexing steps: 

> Demultiplexing has been done using Cutadapt. For most of the fastq files processed here, the reads are in mixed orientation. So Cutadapt is used twice, first looking for tags and forward primers in R1 and then looking for tags and forward primers in R2.
> 
> The results of demultiplexing alone are saved into \${SAMPLE}_\${RUNID}_R1.fastq.gz and \${SAMPLE}\_${RUNID}_R2.fastq.gz. The reads are not reorientated. These files are deposited in public repositories.

The safest way to deal with mixed orientated reads is to split them at the beginning of the workflow into separate files and consider the two pools as two different runs.
This means it's up to you to separate the forward and reverse reads before you proceed with your analyses. You can do this by placing the forward reads from R1 and R2 into a  separate FWD folder, and the reverse reads from R1 and R2 into a separate REV folders. You can find the details on how this was done in the original [Caracciolo et al. 2022](https://doi.org/10.1111/mec.16539) paper in the [index.html](https://doi.org/10.5281/zenodo.5791089) file of their pipeline. 



#### **For the Aquarium COI/12S/16S datasets**
The datasets provided contain the raw, demultiplexed sequences but no filtering was applied. 

### Some variation in sequence length was noticed, especially for the aquarium datasets (12S/COI/16S). 
 **For the Plankton 18S data**

The primer tags were removed during demultiplexing. These tags were located just before the forward primer, so, after demultiplexing, all the forward reads are shorter than the reverse. But, because each file contains 50% forward and 50% reverse reads, we end up with reads of different sizes in each file. Each tag was 8 bp long plus 4 random nucleotides before (some of those are sometimes missing). So forward reads should be between 238bp and 242bp long and reverse are 250bp long.

Below, the size distribution of the 18SV4 reads, one line per file:

![18S distribution](associated_files/timeseries_18S_size_distribution.png)

 **For the Aquarium COI/12S/16S data**

This could be due to non-target amplification by the chosen primers and thus represent biological variation in the amplicons.
Bacterial co-amplification occurs with the 12S primer set and is documented for the [COI primers](https://www.biorxiv.org/content/10.1101/2021.07.10.451903v1.full.pdf)

Below, the size distribution of the 16S, 12S and COI reads:


| 16S data |        |  ~  | 12S data |       | ~| COI data | | |
| -------- | ------ | ---|-------- | ------ |---| -------- |---|---|
| **Counts**   | **Length** |  ~   | **Counts** | **Length**   | ~ | **Counts** | **Length** |
| 39618    | 301    |          | 41094  | 301      |  | 62314 | 301 |
| 20800    | 300    |          | 5927   | 300      |  | 9577 | 300 |
| 14302    | 35     |          | 5674   | 299      |  | 9489 | 298 |
| 686      | 251    |          | 1199   | 217      |  | 3886 | 216 |
| 551      | 261    |          | 975    | 228      |  | 782 | 299 |
| 459      | 259    |          | 881    | 180      |  | 591 | 215 |
| 381      | 299    |          | 614    | 35       |  | 570 | 264 |
| 368      | 245    |          | 584    | 230      |  | 514 | 252 |
| 151      | 220    |          | 488    | 229      |  | 274 | 281 |
| 147      | 262    |          | 471    | 142      |  | 259 | 192 |


### Were samples collected in the same location?

For the plankton 18S time-series: yes all samples were collected at the SOMLIT-Astan sampling station, located in the western English Channel, 3.5 km off Roscoff (Brittany, France) (60 m depth, 48°46′18″ N– 3°58′6″ W).

For the fish 12S/16S/COI aquarium samples: all three [biological] replicates were collected at the same time in the Lisbon aquarium.

### Aquarium COI/12S/16S datasets - Resident species
An extended list of resident species from the aquarium, including whether or not they have sequences in the reference database, was added. While all resident species are represented in the COI database, not all have sequences for the 12S and/or 16S genes.
The list can be found under :file_folder: &nbsp;[**associated_files/aquarium_COI_12S_16S_resident_species_byprimer.xlsx**](https://github.com/marco-bolo/wp2-wp5-workshop/tree/master/associated_files)


### Aquarium COI/12S/16S datasets - Potential contaminants
Attached is a list of species confirmed by the aquarium as part of the fish' diet. However, there is no comprehensive list of all the fish used as food. The species listed were identified during the study and confirmed by the aquarium as being part of the fish' diet. The aquarium typically purchases fish for food, such as boxes of mackerel, which may contain other mixed species. Therefore, there isn't an exact list of the species used as food, just an idea of what is typically used, along with other species that may come mixed in without any control.
The list can be found under :file_folder: &nbsp;[**associated_files/aquarium_COI_12S_16S_potential_contaminantSpecies.csv**](https://github.com/marco-bolo/wp2-wp5-workshop/tree/master/associated_files)

### Aquarium COI/12S/16S datasets - Why were two primers used for 12S
It is a mix of the Mifush-U primers and Mifish-E primers. The Mifish-U primers were first designed but noted that they didn’t target elasmobranch taxa very well. Therefore a second primer pair was developed that targeted the elasmobranchs specifically. Both primers are used in multiplex to cover all fish groups.

More information on the primers can be found in [Miya et al. 2015](http://rsos.royalsocietypublishing.org/lookup/doi/10.1098/rsos.150088):

> The first universal primers for eDNA were designed on the 12S rRNA gene (for details, see
Results and Discussion) and were named MiFish-U-F/R (with overhang adapter sequences for library preparation; U, F and R represent universal, forward and reverse, respectively). In addition, we had to design MiFish-E-F/R to accommodate sequence variations in the priming sites of elasmobranchs (E), with the primer designs based on newly assembled partial mitogenome sequences from 160 species (electronic supplementary material, table S2).


### Do the reference database [for the aquarium datasets] contain only the target species, only fish species, or also outgroups (e.g. crustaceans)?

Yes they only contain fish species. 

We ask you to use these standardised reference libraries for your species assignment.

However, several of you have noted that they would include outgroups that would allow to separate un-assigned fish sequences from non-fish sequences (e.g. crustacea or bacteria which are known to co-amplify with the primer sets). We encourage you to do the taxonomic assignation to broader reference libraries the way you would normally do it, in addition to the assignation to the standardised reference libraries. You can then send us an additional taxonomic table with all the necessary documentation to know what steps were taken.

### Is it possible to add the lineage to the species names of the reference libraries?

Yes, this was done and the new reference libraries were added on 13/09/2024 to each of the data folders containing the raw read data and the reference libraries.