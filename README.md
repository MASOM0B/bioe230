# bioe230 WEEK 3 Assignments


## 1. I made the github and added a README file in a new repository named bioe230.

## 2. 
### (i) I downloaded 2 files from https://www.ncbi.nlm.nih.gov/datasets/ to my local disk (/C:/Users/PTCL/Desktop/1st_sem/BioE230/week_3/FASTA.zip masom0b@ilogin.ibex.kaust.edu.sa:/home/masom0b/ncbi_dataset/week_3). One file was in .tsv format named ncbi_data.tsv. It contained the data of 14 genomes after I applied 2 filters of complete genome and date till 2001. The second file had all the FASTA sequences in a zip format. I moved it to my directory at ibex masom0b@ilogin.ibex.kaust.edu.sa:/home/masom0b/ncbi_dataset/week_3. 
```
scp -r /C:/Users/PTCL/Desktop/1st_sem/BioE230/week_3/FASTA.zip masom0b@ilogin.ibex.kaust.edu.sa:/home/masom0b/ncbi_dataset/week_3       # followed by password input
```
OUTPUT = PICTURE? 2 files one zip one .tsv

### (ii) unzip file
```
unzip FASTA.zip
```
OUTPUT = 
## 3. 
### (i) to find the largest genome
```
cut -f3,11 ncbi_data.tsv | tail -n +2 | sort -t$'\t' -k2n | tail -n 1
```
OUTPUT = Vibrio cholerae O1 biovar El Tor str. N16961    4033464

### (ii) to find the smallest genome 
```
cut -f3,11 ncbi_data.tsv | tail -n +2 | sort -t$'\t' -k2n | head -n 1
```
OUTPUT = Chlamydia trachomatis D/UW-3/CX 1042519

## 4. 
### to find all 2 cs (number)
```
cut -f3 ncbi_data.tsv | uniq | grep -iE 'c.*c'| wc -l
```
OUTPUT = 7

### to find all 2 cs but without coccus (number)
```
cut -f3 ncbi_data.tsv | uniq | grep -iE 'c.*c'| grep -vi 'coccus' | wc -l
```
OUTPUT = 5

## 5. to find .fna files larger than 3Mb
```
find . -name "*.fna" -size +3M | wc -l
```
OUTPUT = 6
