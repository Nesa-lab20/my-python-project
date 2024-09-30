## week 3 assignment

## 1 Write the README file containing all commands you run to complete these tasks, and their output, and commit the README to a new repository (my-python-project)

## 2
% scp .\Downloads\ncbi_dataset_bacterialgenome.zip baezvg@ilogin.ibex.kaust.edu.sa:~/
baezvg@ilogin.ibex.kaust.edu.sa's password:
ncbi_dataset_bacterialgenome.zip                                                                                  100%   16MB   9.0MB/s   00:01

% ssh baezvg@ilogin.ibex.kaust.edu.sa

#2B Uncompress the zip file on IBEX
%ls

%unzip ncbi_dataset_bacterialgenome.zip
###Archive:  ncbi_dataset_bacterialgenome.zip
  
%ls ncbi_dataset/data

#3A Write a command that outputs only the line with the smallest (largest) genome. 

##file path ncbi_dataset/data/data_summary.tsv
#To see the first lines and the column headers
% head ncbi_dataset/data/data_summary.tsv

#- the sizes of the genomes are in column 11
% cut -f11 ncbi_dataset/data/data_summary.tsv

#3A.1 Find the smallest genome and output the entire line:
% cat ncbi_dataset/data/data_summary.tsv | tail -n +2 | sort -t $'\t' -k11,11n | head -n 1

#3A.2. Find the largest genome and output the entire line:
% cat ncbi_dataset/data/data_summary.tsv | tail -n +2 | sort -t $'\t' -k11,11nr | head -n 1

#3B.1. Output only the genome size (smallest genome):
%cut -f11 ncbi_dataset/data/data_summary.tsv | tail -n +2 | sort -n | head -n 1

#3B.2. Output only the genome size (largest genome):
%cut -f11 ncbi_dataset/data/data_summary.tsv | tail -n +2 | sort -nr | head -n 1

## 4
#4A Find the number of genomes that contain at least two “c” in the species name.   
% grep -i 'c.*c' ncbi_dataset/data/data_summary.tsv | wc -l

#4B How many of the species names contain two or more “c” but do not contain the word “coccus”? Your command should be a single line and output a number.
%grep -i 'c.*c' ncbi_dataset/data/data_summary.tsv | grep -vi 'coccus' | wc -l

# 5 Use the find command to find all genome files (FASTA) larger than 3 megabyte. How many are there (output only the number).

%find ncbi_dataset/data -type f -name "*.fna" -size +3M | wc -l

