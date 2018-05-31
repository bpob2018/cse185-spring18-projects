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
3. Downloaded Rsubread into R module on `ieng6` --> will use to build index and align
4. Load Rsubread package into R using `library(Rsubread) `
5. Downloaded fasta file for chromosome 1 of mm10 mouse genome from UCSC genome browser --> to be used to build index.
6. Build the index with command in Rsubread with `buildindex(basename="chr1_mm10", reference="chr1.fa")`
7. Align each of 12 samples (subset of 1000 reads per sample) with command `align("chr1_mm10", fastq.files)`
8. Find out how many reads were mapped to reference genome usin `propmapped` function on BAM files.
Output below:
```
                                                                Samples
1  /home/linux/ieng6/cs185s/bpoblete/Final/SRR1552444.fastq.gz.subread.BAM
2  /home/linux/ieng6/cs185s/bpoblete/Final/SRR1552445.fastq.gz.subread.BAM
3  /home/linux/ieng6/cs185s/bpoblete/Final/SRR1552446.fastq.gz.subread.BAM
4  /home/linux/ieng6/cs185s/bpoblete/Final/SRR1552447.fastq.gz.subread.BAM
5  /home/linux/ieng6/cs185s/bpoblete/Final/SRR1552448.fastq.gz.subread.BAM
6  /home/linux/ieng6/cs185s/bpoblete/Final/SRR1552449.fastq.gz.subread.BAM
7  /home/linux/ieng6/cs185s/bpoblete/Final/SRR1552450.fastq.gz.subread.BAM
8  /home/linux/ieng6/cs185s/bpoblete/Final/SRR1552451.fastq.gz.subread.BAM
9  /home/linux/ieng6/cs185s/bpoblete/Final/SRR1552452.fastq.gz.subread.BAM
10 /home/linux/ieng6/cs185s/bpoblete/Final/SRR1552453.fastq.gz.subread.BAM
11 /home/linux/ieng6/cs185s/bpoblete/Final/SRR1552454.fastq.gz.subread.BAM
12 /home/linux/ieng6/cs185s/bpoblete/Final/SRR1552455.fastq.gz.subread.BAM
   NumTotal NumMapped PropMapped
1      1000       145      0.145
2      1000       136      0.136
3      1000       120      0.120
4      1000       113      0.113
5      1000        55      0.055
6      1000        76      0.076
7      1000       124      0.124
8      1000       161      0.161
9      1000       142      0.142
10     1000       151      0.151
11     1000       133      0.133
12     1000       117      0.117
```
