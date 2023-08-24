wget https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.1-mc-grch38/hprc-v1.1-mc-grch38.gbz
wget https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.1-mc-grch38/hprc-v1.1-mc-grch38.dist
wget https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.1-mc-grch38/hprc-v1.1-mc-grch38.min
wget https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.1-mc-grch38/hprc-v1.1-mc-grch38.snarls


##
 /usr/bin/time -v ~/bin/gfatools view -R chr12:25200000-25300000 ./hprc-v1.1-mc-grch38.gfa 2> test_chr12.gfa 1> test_chr12.log &


singularity run --bind /media/omicsacademy/ ../software/vg.1.50.1.sif vg autoindex -g hprc-v1.1-mc-grch38.gfa -p hprc-v1.1-mc-grch38 > hprc-v1.1-mc-grch38.log



 singularity run --bind /media/omicsacademy/ ../software/vg.1.50.1.sif vg index -x hprc-v1.1-mc-grch38.xg hprc-v1.1-mc-grch38.gfa > hprc-v1.1-mc-grch38.xg.log
