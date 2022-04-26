### Under construction.
Bloody hell. They keep changing the form.

1. Go to https://www.ebi.ac.uk/ena/submit/webin/ ; and log in.
2. Click on ' register study ' and complete the fields.
3. Click on ' register sample ' and complete the fields. For the taxonomic ID, you'll need to:
3.1 go on [NCBI taxonomy](https://www.ncbi.nlm.nih.gov/taxonomy).
3.2 search after your organism. Say, Scalesia atractyloides.
3.3 This will give you a taxonomic ID. For ours it is: 2708596

This is how the final sample name looked like.
```
Checklist	ERC000011	ENA default sample checklist
tax_id	scientific_name	sample_alias	sample_title	sample_description
2708596	Scalesia atractyloides	Scalesiaatractyloides69	Scalesia_atractyloidesGenome	genome
```

4. Download the web-in plugin [from here](https://github.com/enasequence/webin-cli/releases) and load java on the cluster.
5. Make a manifest file, like this for each pair of libraries.

```
STUDY   PRJEB52418
SAMPLE  ERS11818460
NAME    paPQPmaisOVossoTempo
PLATFORM        ILLUMINA
INSTRUMENT      Illumina HiSeq 2500
LIBRARY_SOURCE  GENOMIC
LIBRARY_SELECTION       unspecified
LIBRARY_STRATEGY        Hi-C
FASTQ   DTG-OmniC-104_R1_001.fastq.gz
FASTQ   DTG-OmniC-104_R2_001.fastq.gz
```

6. Run
```
java -jar webin-cli-4.3.0.jar -context=reads -manifest=manifestDove.tsv -userName=Webin-56891 -password XXXXXXXX -submit
```


NOTE TO SELF. INSTEAD OF 4/5/6 RISHI SUGGESTED:
```
ml lftp/4.9.1-GCCcore-8.3.0
lftp
open webin.ebi.ac.uk
user Webin-56891
mput *gz
```
