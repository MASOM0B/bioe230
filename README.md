# bioE230 WEEK 3 Assignments


## 1. I made the github and 

## 2. Moving files from local storage to ibex

```
scp -r /C:/Users/PTCL/Desktop/1st_sem/BioE230/week_3/FASTA.zip masom0b@ilogin.ibex.kaust.edu.sa:/home/masom0b/ncbi_dataset/week_3       # followed by password input
```
## unzip file
```
unzip FASTA.zip
```
## 3. 
### to find largest genome
```
cut -f3,11 ncbi_data.tsv | tail -n +2 | sort -t$'\t' -k2n | tail -n 1
```
### to find smallest genome 
```
cut -f3,11 ncbi_data.tsv | tail -n +2 | sort -t$'\t' -k2n | head -n 1
```
## 4. 
### to find all 2 cs (number)
```
cut -f3 ncbi_data.tsv | uniq | grep -iE 'c.*c'| wc -l
```

### to find all 2 cs but without coccus (number)
```
cut -f3 ncbi_data.tsv | uniq | grep -iE 'c.*c'| grep -vi 'coccus' | wc -l
```

## 5. to find .fna files larger than 3Mb
```
find . -name "*.fna" -size +3M | wc -l
```
