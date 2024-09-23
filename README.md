# bioe230
# to find smallest genome 
cut -f3,11 ncbi_data.tsv | tail -n +2 | sort -t$'\t' -k2,2n | tail -n 1
# to find largest genome 
cut -f3,11 ncbi_data.tsv | tail -n +2 | sort -t$'\t' -k2,2n | head -n 1
# to find all 2 cs 
cut -f3 ncbi_data.tsv | grep -E 'c.*c'
# to find all 2 cs (number)
cut -f3 ncbi_data.tsv | grep -E 'c.*c' | wc -l
# to find all 2 cs but omit cocus 
cut -f3 ncbi_data.tsv | grep -E 'c.*c' | grep -vi 'coccus'
# to find all 2 cs but without coccus (number)
cut -f3 ncbi_data.tsv | grep -E 'c.*c' | grep -vi 'coccus' | wc -l
