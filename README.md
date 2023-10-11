# Metagenomic assemblies
For this assignment you will assemble metagenomes using [MEGAHIT](https://academic.oup.com/bioinformatics/article/31/10/1674/177884), NGS de novo assembler for assembling large and complex metagenomics data in a time- and cost-efficient manner.

In class we created a conda environment called `megahit`, installed  [megahit](https://github.com/voutcn/megahit) and checked the help menu. We noticed that the kmer size needs to be an odd number. This is actually a requirement that all (kmer) assemblers have
- Please briefly explain what issues an even number kmer would cause.

In order to check the quality of the files, you are going to need [Quast](http://quast.sourceforge.net/). In class we will create the environment, install and check the help menu.



## Locate and download the sequences
For your assignment, you will be working with datasets from **Shotgun Sequencing of Tara Oceans DNA samples corresponding to size fractions for prokaryotes** 

Go to the [NCBI](https://www.ncbi.nlm.nih.gov) and search for Bioproject PRJEB1787.

- Download the metadata table; make a folder called `tables` in the Github repo that you have cloned for the homework assignment and upload the metadata to this folder.

- How many SRA experiments (Runs) does this project contain, and how many BioSamples? Briefly explain the difference between them.

- What is the total volume of data in Gbases and in Tbytes?

- Write a small loop to download the datasets ERR598970, ERR598972, and ERR599021. Provide the code you used to do this below.

- From checking the metadata, which station and depths do these datasets come from? What are the latitude and longitude coordinates of this station?

- Write a small loop to count the number of sequences in the both _1 and _2 files for all datasets and provide the code below. Output the results of the loop in a file called `rawseqs_counts` and add it to your `tables` folder in the GitHub repository.

## Check the quality of the sequences and trim them

- Inspect the quality of all sequences.

- Make an `sbatch` script to trim the sequences of each dataset using `trimgalore` and any parameters you want. Inspect the quality of all of the trimmed sequences. Change the parameters if you are not satisfied with the quality of the trimmed sequences.  Which parameters (final choice if you tried a few) did you use and why? Make a new folder in GitHub your repo called `scripts` and add the sbatch scripts you submitted to this new `scripts` folder.

- Write a small loop to count the number of sequences in both the _1 and _2 files for the trimmed datasets. Output the results of the loop in a file called `trimmedseqs_counts` and add it to your `tables` folder.

## Assembly

- Use `megahit` to assemble each dataset into contigs. Write `sbatch` scripts to run `megahit`. Work with only one of the datasets first. Check the memomy used and the time it took to successful run this dataset (*Hint: [WHOI-IS webpage](https://whoi-it.whoi.edu/managing-and-monitoring-jobs-on-poseidon/) might be able to help). Optimize the usage to memory and time for the subsequent runs. Add the sbatch scripts you submitted on your `scripts` repo folder.

- Use `quast` to calculate the basic summary statistics. Report your code (you can either use srun or sbatch for this task). Concatenate all three `report.tsv` tables to a new table called `combined_report.tsv` (in the appropriate format: first column should contain the descriptor of the values followed by the columns of the reported numbers for each dataset; do not forget to remane the columns). You can use bash, python, R :) but report what which program you used and your code. Add the `combined_report.tsv` table in your `tables` folder. Give the definition of N50 and L50 and briefly discuss the statistics. Which of the datasets gave the largest total assembly? Which one produced the longest contig?



____________________________________________________________________________________________________________________________________________

### For successful completion of your homework, your Github repo should contain:
- an updated README file with answers to the questions
- a directory called `tables` that contains: the SRA metadata file, the rawseqs_counts, trimmedseqs_counts, and combined_report.tsv
- a directory called `scripts` that contains: the sbatch scripts you used for the trimming and assembly


Do not hesitate to contact us if you have any questions!

