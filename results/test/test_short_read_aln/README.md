#!/usr/bin/env bash
curl -L ftp://ftp.sra.ebi.ac.uk/vol1/fastq/SRR789/008/SRR7890828/SRR7890828_1.fastq.gz -o SRR7890828_WGS_cross-site_study_1.fastq.gz &
curl -L ftp://ftp.sra.ebi.ac.uk/vol1/fastq/SRR789/008/SRR7890828/SRR7890828_2.fastq.gz -o SRR7890828_WGS_cross-site_study_2.fastq.gz &
wait


```
nohup /usr/bin/time -v bash s1_vg_giraffe.sh > s1_vg_giraffe.log &
```


```
singularity run  --bind /media/omicsacademy/ ../../../software/vg.1.50.1.sif vg surject -x ../../../data/hprc-v1.1-mc-grch38.gbz test_mapped.gam test_mapped.surject.bam
```
