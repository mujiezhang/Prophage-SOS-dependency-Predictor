# Prophage-SOS-dependency-Predictor(PSP) 
PSP is a novel bioinformatics tool to predict prophage induction modes by analyzing the heterology index (HI) of LexA protein binding to target DNA, classifying prophages into SOS-dependent (SdPs) and SOS-independent (SiPs).

## Dependencies
* PSP is a Python script that relies on:
```Biopython
DIAMOND
MEME
Python3
scikit-learn
```

## Installation
(1) git
```
git clone https://github.com/mujiezhang/PSP.git
cd PSP
python psp.py -h
```

(2) conda
```
conda create -n PSP python=3.12
conda activate PSP
conda install PSP
```
usage: ```psp -h```

## Input files
PSP needs four files as inputs,i.e.,
* ```-hf```: a host genome in fasta format
* ```-vf```: a single viral genome in fasta format
* ```-motif```: a motif file provided by psp as ```19-motifs-meme.txt``` 
* ```-lexa```: lexa database for diamond blastp provided by psp as ```uniprot_swiss_prot_LexA.dmnd``` 

other parameters
*```-wd```: woking path to save result files

## How to run
The users can only specify the required parameters:
```
python psp.py -hf host-genome.fasta -vf virus-genome.fasta -motif 19-motifs-meme.txt -lexa uniprot_swiss_prot_LexA.dmnd -wd output_dir
```

for example:
```
python psp.py -hf E.coli-HS.fasta -vf phiECO1.fasta -motif 19-motifs-meme.txt -lexa uniprot_swiss_prot_LexA.dmnd -wd .
```

Running this example with one core takes approximately two minutes. And you will get two files: ```host_whole_genome_HI.tsv``` and ```prediction.tsv```

## Attention
* PSP is designed for complete host and corresponding complete virus for that host. Using incomplete genome as input may influence the prediction accuracy.

## Citation
''''''
