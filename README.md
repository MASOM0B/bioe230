# bioe230 WEEK 3
#1 I made the new repository

#2 Moving files from computer to ibex
```bash
scp -r /C:/Users/PTCL/Desktop/1st_sem/BioE230/week_3/FASTA.zip masom0b@ilogin.ibex.kaust.edu.sa:/home/masom0b/ncbi_dataset/week_3       # followed by password input
```
# unzip file
```bash
unzip FASTA.zip
```
# to find largest genome 
```bash
cut -f3,11 ncbi_data.tsv | tail -n +2 | sort -t$'\t' -k2n | tail -n 1
```
# to find smallest genome 
```bash
cut -f3,11 ncbi_data.tsv | tail -n +2 | sort -t$'\t' -k2n | head -n 1
```
# to find all 2 cs (number)
```bash
cut -f3 ncbi_data.tsv | grep -E 'c.*c' | wc -l
```
# to find all 2 cs but without coccus (number)
```bash
cut -f3 ncbi_data.tsv | grep -E 'c.*c' | grep -vi 'coccus' | wc -l
```
# to find the sizes of the genome 
```bash
cut -f11 ncbi_data.tsv | tail -n +2 | sort -n | uniq
```
# to find .fna files larger than 3Mb
```bash
find . -type f -size +3M | wc -l 
#OR 
find . -name "*.fna" -size +3M | wc -l
```
