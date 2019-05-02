# UDN_SV_export
This repo contains the exported structural variants for UDN Phase I as called by [Manta](https://academic.oup.com/bioinformatics/article/32/8/1220/1743909) after aligning to GRCh37 human reference genome.

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

The total number of samples captured by the data dumps is 1641.

## Limitations
For the purpose of generating these data dumps, we made **no effort** to condense or consolidate similar variant calls, even when significant overlap is readily apparent.  When determining variant rarity, users should be careful to check for variants that closely match their variant of interest.

At this time, these data dumps contain all structural variant calls that were generated for UDN Phase I.  This means that **no effort** has been made to distinguish between affected and unaffected individuals.  Additionally, **no effort** has been made to remove related individuals from the pool of exported data.  However, **efforts were made** to insure that each individual is represented only once, even in the event of multiple samples for that individual.  When determining variant rarity, users should be cognizant of these limitations.

## Reference
This data is released in support of a paper describing the UDN Phase I efforts to identify structural variants in rare disease patients through genome sequencing.  If you use this data, please cite:

Pre-print forthcoming.