# 1. Go to https://www.ebi.ac.uk/ena/submit/sra/#home, and log onto your personal account:
	Login: Webin-56891 (this is my log-in)
	Password: [stored on chrome]

# 2. Register your project by
	2.1 clicking on: "New Submission" -> "Register study (project)" to begin a ENA project .
  This project gets a PRJEB_____ type of accession number.

# 3. Now that the project is registered we ned to upload the raw reads.
	3.1 You can do it via conda (`conda install -c hcc aspera-cli`).
	On Saga (Norwegian supercomputer) you can do: "module spider aspera; ml Aspera-CLI/3.9.0.1326.6985b21"
	`ascp -QT -l3000M -L- path/to/all/reads/*fastq.gz Webin-56891@webin.ebi.ac.uk:.`
  # Notice, you will have to use your Webin-ID and not mine :)
	
	3.2 For all the files you will upload, you will need to know the md5 sum. That's a unique string that verifies that the files were not corrupted during the transfer.
	`md5sum *fastq.gz > md5.tsv`

# 4. We go back to the web interface, and register one sample by clicking on "Submit sequence reads and experiments" and follow the interactive form.
Start by selecting your project. Download the spreadsheet, and file it up like this:

#checklist_accession	ERC000011				
#unique_name_prefix					
sample_alias	tax_id	scientific_name	common_name	sample_title	sample_description
#template	156853	Tetragnatha kauaiensis	NA	Tetragnatha specimen for genome sequencing	NA
#units

# 5. Now we move on and register sequencing runs. For the majority of what we will submit click on Two Fastq files (Paired) (for all the Illumina stuff). And now you can again, either download a template (Download template spreadsheet) fill the template and upload it or fill the table interactively in the browser.

# 6. Submit and it's done.
