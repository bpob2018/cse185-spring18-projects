# Lab notebook for CSE185 Final Project
## Beverlie Poblete
## PID A11334034

### Lab Session 1.  May 22, 2018.
#### Goal: list at least 3 datasets you're interested in (accession #'s and a brief description)
1. Find possible papers I want to elaborate upon:
* [http://jvi.asm.org/content/87/1/503.full] Deep RNA Sequencing Reveals Complex Transcriptional Landscape of a Bat Adenovirus
* [https://academic.oup.com/bioinformatics/article/25/9/1105/203994] TopHat: discovering splice junctions with RNA-Seq 
* [https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3245950/] Ultrasensitive detection of rare mutations using next-generation targeted resequencing.
* [https://www.sciencedirect.com/science/article/pii/S0012160615301305#f0005] Epigenetic modification maintains intrinsic limb-cell identity in Xenopus limb bud regeneration
* __Chosen Paper:__ https://www.nature.com/articles/srep08747#methods: "Completing bacterial genome assemblies: strategy and performance comparisons"

2. Find 3 relevant datasets:
* SRA access #: SRR447685  -  E. coli K-12 MG1655 2x101 bp, 180 bp insert Fragment reads
* SRA access #: SRR401827 and SRR492488 - E. coli K-12 MG1655 2x93 bp, 3000 bp insert Jump reads
* SRA access #: SRX255228 - E. coli K-12 MG1655 10 Kbp, 17 SMRT cell Long read
__Plan to use all these datasets lisetd above__

### Lab Session 2.  May 24, 2018.
#### Goal: one sentence about the biological question for the dataset you chose; also sign up for lightning talks
1. __Question to answer:__ As in the paper by Liao *et al*, I sought to also provide a comprehensive comparison of assembly methodologies mentioend in this paper, most likely between one mentioned hybrid and one mentioned non-hybrid methodology.  If time persists, I'd like to compare these two methodologies to the method/approach we took in our week 3 lab tutorial when assembling the reference genome.  I might use ALLPATHS-LG approach for my hybrid study and then Hierarchical genome-assembly process (HGAP) for my non-hybrid study.

### Lab Session 3.  May 29, 2018.
Link about ALLPATHS-LG: http://schatzlab.cshl.edu/teaching/2011/2011-11-15.Assembly%20Tutorial.pdf
1. Downloaded ALLPATHS-LG v. 44837
Manual found here: ftp://ftp.broadinstitute.org/pub/crd/ALLPATHS/Release-LG/AllPaths-LG_Manual.pdf

2. While ALLPATHS-LG installing, write out steps from lab 3 tutorial for comparison purposes.
Week 3 Assembly:
1. Inspect the data and run fastqc
2. Used frag fastq files to assemble genome, using a de Brujin graph strategy which breaks reads up into k-mers to facilitate assembly of correctly connected contigs.

### Lab Session 4.  May 31, 2018.
*Note:* I changed my topic to RNA-Seq inspired by this paper in this link: https://www.nature.com/articles/ncb3117 
1. Looked at tutorial of RNA-Seq in R listed here https://bioinformatics-core-shared-training.github.io/RNAseq-R/align-and-count.nb.html
2. Downloaded all 12 fastq sets from SRA for my RNA-seq analysis in R.  SRA Accession Number: SRP045534
