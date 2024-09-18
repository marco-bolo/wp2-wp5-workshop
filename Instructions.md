# Instruction specifications following the information sessions

We’ve received a lot of good questions and comments during the two [information sessions](https://github.com/marco-bolo/wp2-wp5-workshop/blob/main/Information_QA.md) that were held on the 9th and 16th of September.
These questions gave us some excellent food for thought and we’d like to share some additional requests and/or recommendations for the data analysis challenge. 

1. Please send in your <ins>sequence table</ins>  alongside your OTU/ASV tables and Taxonomy tables

2. When assigning taxonomy, please <ins>do not discard any non-identified sequences</ins> or non-target taxa but leave everything in your taxonomy table.   
   
    If you would normally conduct post-assignment processing, you can include the results of these in a separate taxonomy table and document which steps were taken to get there in the metadata file.

3. The reference libraries we provided for the **aquarium 12S, 16S and COI** datasets only contain target taxa (i.e. fish). We ask you to <ins>use these standardised reference libraries</ins> for your species assignment. The species lineages were added to the reference libraries on 13/09/2024. 

    \* However, several of you have noted that they would like to include outgroups (only for COI/16S/12S) which would allow to separate un-assigned fish sequences from non-fish sequences (e.g. crustacea or bacteria which are known to co-amplify with the given primer sets). We encourage you to do <ins>an additional taxonomic assignment</ins> using a reference library of your choice, (in addition to the assignment to the standardised reference libraries provided by us). For the submission please upload the resulting taxonomy table with all the sequences (i.e. do not discard any) as an additional table. Also provide the information of the extra reference database (all extra steps) you used in the metadata file.

4. The  runs of the plankton 18S dataset are mixed-orientated. This means that the R1 file will have a mix of forward and reverse reads (~50% each), and the R2 file will also have a mix of forward and reverse reads (~50% each). This is due to the way the library was prepared.

    The safest way to deal with mixed orientated reads is to split them at the beginning of the workflow into separate files and consider the two pools as two different runs.

    This means it's up to you to re-orient your files by e.g. separating the forward and reverse reads into separate FWD and REV folders before you proceed with your analyses. You can find the details on how this was done in the original [Caracciolo et al. 2022](https://doi.org/10.1111/mec.16539) paper in the [index.html](https://doi.org/10.5281/zenodo.5791089) file of their pipeline.

    Some more info on this can also be found in the Information_QA.md under [Question 1: What preprocessing has been done to the data?](https://github.com/marco-bolo/wp2-wp5-workshop/blob/main/Information_QA.md#for-the-plankton-18s-time-series)


