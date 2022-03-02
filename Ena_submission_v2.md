## 1. Let's start
### 1.1 Go to https://www.ebi.ac.uk/ena/submit/sra/#home
### 1.2 Log onto your personal account:
	Login: Webin-56891 (this is my log-in)
	Password: [stored on chrome]

## 2. Register your project
### 2.1 This is done by clicking: "New Submission" -> "Register study (project)".
##3 This project gets a PRJEB_____ accession number.

## 3. Uploading the raw reads.
### 3.1 Now that your project is registered, we do the raw reads.
### 3.2 - Install option A, using conda:
`conda install -c hcc aspera-cli`
### 3.2 - Install option B, on Saga (Norwegian supercomputer):
`module spider aspera; ml Aspera-CLI/3.9.0.1326.6985b21`

### 3.3 Use ASCP to push the data
#### Notice, you will have to use your Webin-ID and not mine :)
`ascp -QT -l3000M -L- path/to/all/reads/*fastq.gz Webin-56891@webin.ebi.ac.uk:.`

### 3.4 You will need to generate a 'md5 sum' file for each uploaded file. Say you have 50 individuals (50 forward reads, 50 reverse reads) - you'll need 100 md5 sums. Each md5 sum is a unique string that verifies that the files were not corrupted during the transfer - like a passport for that file.
`md5sum *fastq.gz > md5.tsv`

## 4. Register sample info
### 4.1 We go back to the web interface (see 1.1), and register one sample by clicking on "Submit sequence reads and experiments" and follow the interactive form.
### 4.2 Start by selecting your project.
### 4.3 Download the spreadsheet, and file it up like this:

#checklist_accession	ERC000011				
#unique_name_prefix					
sample_alias	tax_id	scientific_name	common_name	sample_title	sample_description
#template	156853	Tetragnatha kauaiensis	NA	Tetragnatha specimen for genome sequencing	NA
#units

## 5. Registering sequencing runs
### 5.1 Now we move on and register sequencing runs. Click on Two Fastq files (Paired) (for Illumina).
### 5.2 Option a - Now again, either download a template ("Download template spreadsheet") and fill the template and upload the sheet
### 5.2 Option b - Fill the table interactively in the browser.

## 6. Submit!
### 6.1 done
