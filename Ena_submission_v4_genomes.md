# Ignore 1-3 if you already did the raw data (v3).
1. Go to https://www.ebi.ac.uk/ena/submit/webin/ ; and log in.
2. Click on ' register study ' and complete the fields.
3. Click on ' register sample ' and complete the fields. For the taxonomic ID, you'll need to:
3.1 go on [NCBI taxonomy](https://www.ncbi.nlm.nih.gov/taxonomy).
3.2 search after your organism. Say, Scalesia atractyloides.
3.3 This will give you a taxonomic ID. For ours it is: 2708596

1. Download the web-in plugin [from here](https://github.com/enasequence/webin-cli/releases) and load java on the cluster.
2. Make a manifest file, for each pair of libraries.

Assembly example:
```
STUDY   PRJEB52418
SAMPLE  ERS11818460
ASSEMBLYNAME    scalesia_atractyloides_v1
ASSEMBLY_TYPE   isolate
COVERAGE        200
PROGRAM wtdbg2, DoveTailHiRise
PLATFORM        Pacbio, Dovetail
MOLECULETYPE    genomic DNA
FASTA   scalesia_atractyloides.renamed.fasta.gz
```

3. Run
```
java -jar webin-cli-5.1.0.jar -username=Webin-56891 -password=XXX -context genome -manifest manifest.txt -validate
java -jar webin-cli-5.1.0.jar -username=Webin-56891 -password=XXX -context genome -manifest manifest.txt -submit
```
