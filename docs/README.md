# barley_pangenes

Pangenes are clusters of gene models/alleles found in barley assemblies in a similar genomic location.

Click on chromosomes below to browse pangenes and display multiple sequence alignments of encoded proteins.

[chr1H](./chr1H.html) | [chr2H](./chr2H.html) | [chr3H](./chr3H.html) | [chr4H](./chr4H.html) | [chr5H](./chr5H.html) | [chr6H](./chr6H.html) | [chr7H](./chr7H.html) | [chrUn](./chrUn.html) 

## Raw files

You can download the raw pangene matrices at <https://github.com/eead-csic-compbio/barley_pangenes>.

The pangene matrices in BED and TSV format describe clusters of gene models 
found to be collinear across barley assemblies and annotations in the following 
order: 

    MorexV3 Morex Barke HOR10350 HOR3081 HOR9043 OUN333 HOR7552 Igri HOR21599 HOR13942 Akashinriki HOR8148 RGT_Planet HOR13821 B1K-04-12 HOR3365 Hockett ZDM02064 ZDM01467 Golden_Promise BarkeBaRT2v18

The gene annotations come from https://doi.org/10.5447/ipk/2020/24, 
https://doi.org/10.1111/tpj.15871 (BaRTv2)
and https://plants.ensembl.org (MorexV3).
 
The **TSV** file contains one cluster per row, the 1st column being the cluster name.

The **BED** file describes the same clusters with the first four columns indicating the
position of the relevant gene model in the MorexV3 reference and the cluster name.
Clusters that do not include MorexV3 genes do not have an exact position, they are placed
within an interval defined by two MorexV3 genes. Those rows start with '#'.

These were produced by clustering collinear genes with 
[get_pangenes.pl](https://github.com/Ensembl/plant-scripts/tree/master/pangenes) version 11012024 
with the following arguments:

    plant-scripts/pangenes/get_pangenes.pl -d barley -s '^chr\d+H' -m cluster -r MorexV3 -H -t 0 

## Citation

Protocol and files first published at:

Contreras-Moreira, B., Saraf, S., Naamati, G. et al. GET_PANGENES: calling pangenes from plant genome alignments confirms presence-absence variation. Genome Biol 24, 223 (2023). https://doi.org/10.1186/s13059-023-03071-z


