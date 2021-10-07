# Metagenomic assemblies
For this assignment you will assemble metagenomes using [MEGAHIT](https://academic.oup.com/bioinformatics/article/31/10/1674/177884), NGS de novo assembler for assembling large and complex metagenomics data in a time- and cost-efficient manner.

In class we will create a conda environment called `megahit`, install [megahit](https://github.com/voutcn/megahit) and check the help menu.

In order to check the quality of the files, you are going to need [Quast](http://quast.sourceforge.net/). In class we will create the environment, install and check the help menu.



## Locate and download the sequences
For your assignement, you will be working with datasets from **Shotgun Sequencing of Tara Oceans DNA samples corresponding to size fractions for prokaryotes** 

Go to the [NCBI](https://www.ncbi.nlm.nih.gov) Biopoject PRJEB1787.

- Download the metadata table; make a folder called `tables` in your Github repo and add it there.

- How many SRA experiments (Runs) it contains and how many BioSamples? Briefly explain the difference between them.

- What is the total volume of data in Gbases and in Tbytes?

- Write a small loop to download the datasets ERR598970, ERR598972, and ERR599021. Provide the code below.

- From which station and depths are these datasets coming from? What are the coordinates of this station?

- Write a small loop to count the number of sequences in the both _1_ and _2_ files for all datasets and provide the code below. Output the results of the loop in a file called `rawseqs_counts` and add it to your `tables` folder.

## Checking the quality of the sequences and trim them

Inspect the quality files of all sequences. 

- Make a sbatch script to trim the sequences of each dataset using `trimgalore` and any parameters you want. Inspect the quality of trimmed sequences. Change the parameters if you are not satisfied with the quality of the trimmed sequences.  Which parameters (final choice if you tried a few) you used and why? Make a new folder in your repo called `scripts` and add the sbatch scripts you submitted on your repo.

- Write a small loop to count the number of sequences in both _1_ and _2_ files for trimmed datasets and provide the code below. Output the results of the loop in a file called `trimmedseqs_counts` and add it to your `tables` folder.

## Assembly

- Use `megahit` to assemble each dataset into contigs. Use sbatch scripts. Work with one of the datasets first. Check the memomy used and the time it took to successful run this dataset. Optimize the usage to memory and time for the subsequent runs. Add the sbatch scripts you submitted on your `scripts` repo folder.

- Use `quast` to calculate basic summary statistics. Give the definition of N50 and L50 and briefly discuss the statistics. Add the `report.tsv` table in your `table` folder. *Hint: you might need to rename your files.* Which of datasets gave the largest total assembly? Which one produced the longest contig?
