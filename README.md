# barley_pangenes

Pangenes are clusters of gene models/alleles found in barley assemblies in a similar genomic location.

![example pangene](https://media.springernature.com/lw685/springer-static/image/art%3A10.1186%2Fs13059-023-03071-z/MediaObjects/13059_2023_3071_Fig4_HTML.png)

## Website

You can browse pangenes and display multiple sequence alignments of encoded proteins at <https://eead-csic-compbio.github.io/barley_pangenes>.

## Raw files

The pangene matrices in BED and TAB format describe clusters of gene models 
found to be collinear across barley assemblies and annotations in the following 
order: 

    MorexV3 Morex Barke HOR10350 HOR3081 HOR9043 OUN333 HOR7552 Igri HOR21599 HOR13942 Akashinriki HOR8148 RGT_Planet HOR13821 B1K-04-12 HOR3365 Hockett ZDM02064 ZDM01467 Golden_Promise BarkeBaRT2v18

The gene annotations come from https://doi.org/10.5447/ipk/2020/24, 
https://doi.org/10.1111/tpj.15871 (BaRTv2)
and https://plants.ensembl.org (MorexV3).
 
The **TAB** file contains one cluster per row, the 1st column being the cluster name.

The **BED** file describes the same clusters with the first four columns indicating the
position of the relevant gene model in the MorexV3 reference and the cluster name.
Clusters that do not include MorexV3 genes do not have an exact position, they are placed
within an interval defined by two MorexV3 genes. Those rows start with '#'.

These were produced by clustering collinear genes with 
[get_pangenes.pl](https://github.com/Ensembl/plant-scripts/tree/master/pangenes) version 28022024 
with the following arguments:

    plant-scripts/pangenes/get_pangenes.pl -d barley -s '^chr\d+H' -m cluster -r MorexV3 -H -t 0 

The log file is available [here](log.barley.H.t0.MorexV3.txt).

## Citation

Protocol and files first published at:

Contreras-Moreira B, Saraf S, Naamati G et al (2023) GET_PANGENES: calling pangenes from plant genome alignments confirms presence-absence variation. Genome Biol 24, 223. https://doi.org/10.1186/s13059-023-03071-z

Multiple sequence alignments produced with clustal-omega v1.2.4:

Sievers F, Wilm A, Dineen D, et al (2011) Fast, scalable generation of high-quality protein multiple sequence alignments using Clustal Omega. Mol Syst Biol 7:539. https://doi.org/10.1038%2Fmsb.2011.75

## Funding 

Multiple alignments of coding sequences from barley pangenes were computed within [PRIMA project GENDIBAR](https://www.era-learn.eu/network-information/networks/prima/section-2-call-multi-topic-2018/use-of-local-genetic-diversity-to-understand-and-exploit-barley-adaptation-to-harsh-environments-and-for-pre-breeding).
