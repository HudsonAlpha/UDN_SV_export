# UDN_SV_export
This repo contains the exported, aggregate structural variants for UDN Phase I as called by [Manta](https://academic.oup.com/bioinformatics/article/32/8/1220/1743909) after aligning to GRCh37 human reference genome.

## File Description
Inside the "data" folder, there are files with the following labels:
```
UDN_dump_[YYMMDD].vcf.gz
UDN_dump_[YYMMDD].vcf.gz.tbi
```
These files represent an export of our UDN Phase I structural variant database that has been converted back to a bgzipped VCF file and corresponding tabix index.  The date of extraction in year-month-date form is represented by [YYMMDD].

## VCF Format
Inside the files, each variant is represented as it was originally called by Manta.  We added two fields to the INFO column of the VCF:

1. `HETCOUNT` - this is the number of times the variant was called heterozygous (0/1) in UDN Phase I samples
2. `HOMCOUNT` - this is the number of times the variant was called homozygous (1/1) in UDN Phase I samples

The total number of samples captured by the aggregate dataset is 1641.

## Limitations
At this time, the aggregate calls contain all structural variant calls that were generated for UDN Phase I.  Users should be aware of limitations that apply to these aggregate calls, including but not limited to:

1. **No effort** has been made to condense or consolidate similar variant calls, even when significant overlap is readily apparent.  When determining variant rarity, users should be careful to check for variants that closely match their variant of interest.
1. **No effort** has been made to verify the accuracy of every variant call in the dataset.  Users should be aware of Manta's limitations in detection when evaluating variants present or absent from this dataset.  Through internal testing, we found Manta to have roughly ~90% recall and ~50% precision.  
2. **No effort** has been made to distinguish between affected and unaffected individuals.  Users should be careful not to consider this dataset as representative of a "healthy", "normal", "unaffected", or similar population.
3. **Efforts were made** to insure that each individual is represented only once, even in the event of multiple sequencing samples for that individual.  In the event of multiple sequencing samples for an individual, only the primary sample was selected to be included in the aggregate dataset.

## Reference
This data is released in support of a paper describing the UDN Phase I efforts to identify structural variants in rare disease patients through genome sequencing.  If you use this data, please cite:

Pre-print: [Holt, James M., et al. "Identification of Pathogenic Structural Variants in Rare Disease Patients through Genome Sequencing." bioRxiv (2019): 627661.](https://doi.org/10.1101/627661)