# COVIDAnalysisPipeline

COVID analysis pipeline for Single-end and Paired-end reads.
The pipeline uses two different approaches: 1. Aligning directly on microbial genome. 2. Removing human-mapped reads and then aligning specifically on SARS-CoV2 genome.
The pipeline also includes SARS-CoV2 variants anad preparing data for phylogeny analysis.

./run_SE.sh -d <Directory of fastq files> -t <Directory where tools are installed> -r <Human_Reference_Genome.fa> -c <Covid_refernce_genome.fa> -g <GISAID Genome Path> -m <MAO file path> -n <output folder name> -h <help>


Pipeline includes:

1. FastQC : for quality filter of reads
2. Trimmomatic: Trimming reads
3. KRAKEN2: Aligning reads on microbial genomes and identifying reads mapped on SARS-CoV2 genome.
4. Filtering out Human Reads using HISAT2
5. Extracting unmapped reads from Human Alignment.
6. Mapping the unmapped reads on SARS CoV2 genome
7. Converting Sam to Bam
8. Variant calling using VARSCAN.
9. Asssembly of COV2 reads using MEGAHIT and SPAdes.
