# samtools-sort-
### samtools sort code
-n 代表按照queryname 排序与picard sortsam 的so=queryname 相同
[问题](https://www.biostars.org/p/102735/)
~~~
#PBS -N ssmtool
#PBS -l nodes=1:ppn=4
#PBS -l walltime=15:00:00
#PBS -l mem=20gb
#PBS -S /bin/bash
#PBS -q normal_8
#PBS -j oe

source activate wes

samtools sort -n -o /public/home/liuxs/ncbi/dbGaP-21926/signature/bam/SRR5876745.sort -O bam /public/home/liuxs/ncbi/dbGaP-21926/dnaseq/bam/SRR5876745.bam 
~~~
##染色体顺序重排
~~~
for i in $(seq 1 22) X Y M; do cat chr${i}.fa >> hg38.fasta; done

samtools faidx hg38.fa chr2>chr2.fa

for i in $(cat sample);do samtools faidx hg38.fa $i >> /home/lihm/rnaseq/hh/$i.fa;done

cat `ls  *.fa | sort -V | grep -i -v chrM ` chrM.fa > b32.fa
~~~
