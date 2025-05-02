Analysis folder divided by folder per analysis, each folder include .RmD file containing the code and .html file after knitting

00_fastqc:
fastqc and multiqc results run
01_Quality_filtering:
QC filter and trimming with dada2
02_ASVs_Rmd:
Infer an error model for in the filtered sequences, separately on forward and reverse reads.
Assign ASVs on both forward and reverse reads separately by applying the error model.
Merge forward and reverse ASVs into “contiguous ASVs”.
Generate the first draft of ASV count table.
Quality Trimming of ASV lengths.
Remove chimeras.
Assign Taxonomy with Silva Database.
Write out relevant files: asv_table, asvs_fasta, tax_table, and sample_data.

03_Preprocessing_Rmd:
Remove any potential contaminants and evaluate the accuracy and depth of the sequencing run, finish with a raw phyloseq object : "raw_preprocessed_physeq.RData"

04_Phylogenetic_tree:
04_APhylogenetic_Tree_construction:
1.Load in preprocessed phyloseq object 2.Create ASV fasta file from the phyloseq object 3.Align the 16S sequences from fasta file with MAFT 4.Create a tree with FastTree2
04_BPhylogenetic_Tree_Construction:
1.Load the FastTree unrooted tree 2. Add the tree to phyloseq object 3. Visualize and inspect tree with ggtree 4. Prune ASVs, if needed 5. Root out tree 6. Combine newly rooted tree with a phyloseq object 7. Save 2 phyloseq objects: 1. unrooted tree phyloseq object 2. rooted tree phyloseq object

05_Biodiversity:
Run an analysis on the within-sample biodiversity of the samples in our project. 

06_Ordination:
Evaluate sequencing depth and normalize samples with scaling in order to perform between-sample analysis of the data

07_Composition:
Perform compositional analysis of the normalized microbial dataset.

