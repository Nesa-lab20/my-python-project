#week 3 assignment

#1 Write the README file containing all commands you run to complete these tasks, and their output, and commit the README to a new repository (my-python-project)

#2
#2A Copy the files (NCBI database 14 bacteria genomes) to your home directory on IBEX. 

  % scp .\Downloads\ncbi_dataset_bacterialgenome.zip baezvg@ilogin.ibex.kaust.edu.sa:~/
baezvg@ilogin.ibex.kaust.edu.sa's password:
ncbi_dataset_bacterialgenome.zip                                                                                  100%   16MB   9.0MB/s   00:01

  % ssh baezvg@ilogin.ibex.kaust.edu.sa

#2B Uncompress the zip file on IBEX
[baezvg@login509-02-r ~]$ ls
count_genes.py  ecoliGC2.py           genomes                           ncbi_dataset.zip      sorted-genomes.txt  submit_ibex.sh
ecoli.faa       extracted_gene.fasta  grep                              read_ecoli.py         sorted-list.txt     translated_gene.fasta
ecoli.fasta     GCecoli.py            in_class                          script2.py            sorted_list.txt     translated.py
ecoli.fna       genepick.py           my-python                         script.py             SRR30669799
ecoli.gbk       genome-lenghts.txt    ncbi_dataset_bacterialgenome.zip  seq_utils_example.py  SRR30669799.fastq


[baezvg@login509-02-r ~]$ unzip ncbi_dataset_bacterialgenome.zip
Archive:  ncbi_dataset_bacterialgenome.zip
  inflating: README.md
  inflating: ncbi_dataset/data/data_summary.tsv
  inflating: ncbi_dataset/data/assembly_data_report.jsonl
  inflating: ncbi_dataset/data/GCA_000008525.1/GCA_000008525.1_ASM852v1_genomic.fna
  inflating: ncbi_dataset/data/GCA_000008605.1/GCA_000008605.1_ASM860v1_genomic.fna
  inflating: ncbi_dataset/data/GCA_000008625.1/GCA_000008625.1_ASM862v1_genomic.fna
  inflating: ncbi_dataset/data/GCA_000008745.1/GCA_000008745.1_ASM874v1_genomic.fna
  inflating: ncbi_dataset/data/GCA_000027305.1/GCA_000027305.1_ASM2730v1_genomic.fna
  inflating: ncbi_dataset/data/GCF_000008525.1/GCF_000008525.1_ASM852v1_genomic.fna
  inflating: ncbi_dataset/data/GCF_000008605.1/GCF_000008605.1_ASM860v1_genomic.fna
  inflating: ncbi_dataset/data/GCF_000008625.1/GCF_000008625.1_ASM862v1_genomic.fna
  inflating: ncbi_dataset/data/GCF_000008745.1/GCF_000008745.1_ASM874v1_genomic.fna
  inflating: ncbi_dataset/data/GCF_000027305.1/GCF_000027305.1_ASM2730v1_genomic.fna
  inflating: ncbi_dataset/data/GCA_000006745.1/GCA_000006745.1_ASM674v1_genomic.fna
  inflating: ncbi_dataset/data/GCA_000008545.1/GCA_000008545.1_ASM854v1_genomic.fna
  inflating: ncbi_dataset/data/GCA_000008565.1/GCA_000008565.1_ASM856v1_genomic.fna
  inflating: ncbi_dataset/data/GCA_000008725.1/GCA_000008725.1_ASM872v1_genomic.fna
  inflating: ncbi_dataset/data/GCA_000008785.1/GCA_000008785.1_ASM878v1_genomic.fna
  inflating: ncbi_dataset/data/GCF_000006745.1/GCF_000006745.1_ASM674v1_genomic.fna
  inflating: ncbi_dataset/data/GCF_000008545.1/GCF_000008545.1_ASM854v1_genomic.fna
  inflating: ncbi_dataset/data/GCF_000008565.1/GCF_000008565.1_ASM856v1_genomic.fna
  inflating: ncbi_dataset/data/GCF_000008725.1/GCF_000008725.1_ASM872v1_genomic.fna
  inflating: ncbi_dataset/data/GCF_000008785.1/GCF_000008785.1_ASM878v1_genomic.fna
  inflating: ncbi_dataset/data/GCA_000006825.1/GCA_000006825.1_ASM682v1_genomic.fna
  inflating: ncbi_dataset/data/GCA_000006865.1/GCA_000006865.1_ASM686v1_genomic.fna
  inflating: ncbi_dataset/data/GCA_000007125.1/GCA_000007125.1_ASM712v1_genomic.fna
  inflating: ncbi_dataset/data/GCA_000091085.2/GCA_000091085.2_ASM9108v2_genomic.fna
  inflating: ncbi_dataset/data/GCF_000006825.1/GCF_000006825.1_ASM682v1_genomic.fna
  inflating: ncbi_dataset/data/GCF_000006865.1/GCF_000006865.1_ASM686v1_genomic.fna
  inflating: ncbi_dataset/data/GCF_000007125.1/GCF_000007125.1_ASM712v1_genomic.fna
  inflating: ncbi_dataset/data/GCF_000091085.2/GCF_000091085.2_ASM9108v2_genomic.fna
  inflating: ncbi_dataset/data/dataset_catalog.json
  inflating: md5sum.txt

[baezvg@login509-02-r ~]$ ls ncbi_dataset/data
assembly_data_report.jsonl  GCA_000006825.1  GCA_000008545.1  GCA_000008725.1  GCA_000091085.2  GCF_000007125.1  GCF_000008605.1  GCF_000008785.1
dataset_catalog.json        GCA_000006865.1  GCA_000008565.1  GCA_000008745.1  GCF_000006745.1  GCF_000008525.1  GCF_000008625.1  GCF_000027305.1
data_summary.tsv            GCA_000007125.1  GCA_000008605.1  GCA_000008785.1  GCF_000006825.1  GCF_000008545.1  GCF_000008725.1  GCF_000091085.2
GCA_000006745.1             GCA_000008525.1  GCA_000008625.1  GCA_000027305.1  GCF_000006865.1  GCF_000008565.1  GCF_000008745.1



#3 What is the smallest and what is the largest genome in the ones you just downloaded? 
#3A Write a command that outputs only the line with the smallest (largest) genome. 

#3B How large are these genomes? Expand your command to output only the genome size. (Note: You should use shell commands, not write a Python program.)

#4
#4A Find the number of genomes that contain at least two “c” in the species name. 

#4B How many of the species names contain two or more “c” but do not contain the word “coccus”? Your command should be a single line and output a number.

#5 Use the find command to find all genome files (FASTA) larger than 3 megabyte. How many are there (output only the number).
