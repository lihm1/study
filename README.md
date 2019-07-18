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
