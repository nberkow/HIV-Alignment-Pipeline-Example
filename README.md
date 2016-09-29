
### The pipeline

The goal of this assignment is to analyze read coverage of the HIV genome and look for potential relationships between nucleotide composition and sequencing coverage. coverage.py is a wrapper for all the steps involved in the analysis. It runs in python2.7. One specification was that the pipeline would be run at different thresholds of sequencing quality. Each of the pipeline runs is a subdirectory of the output directory.



### Commands for running the pipeline

```
python2.7 coverage.py -1 ../data/test_1.fastq -2 ../data/test_2.fastq -x ../annotation/HXB2.fasta -a ../annotation -p HXB2 -q 10 -o ../output/test > test.log

python2.7 coverage.py -1 ../data/test_1.fastq -2 ../data/test_2.fastq -x ../annotation/HXB2.fasta -a ../annotation -p HXB2 -q 0 -o ../output/HXB2_q0 > q0.log

python2.7 coverage.py -1 ../data/test_1.fastq -2 ../data/test_2.fastq -x ../annotation/HXB2.fasta -a ../annotation -p HXB2 -q 10 -o ../output/HXB2_q10 > q10.log

python2.7 coverage.py -1 ../data/test_1.fastq -2 ../data/test_2.fastq -x ../annotation/HXB2.fasta -a ../annotation -p HXB2 -q 20 -o ../output/HXB2_q20 > q20.log

python2.7 coverage.py -1 ../data/test_1.fastq -2 ../data/test_2.fastq -x ../annotation/HXB2.fasta -a ../annotation -p HXB2 -q 30 -o ../output/HXB2_q30 > q30.log
```

### Arguments

##### Basic arguments specified in the assignment

```
-1  # Sense fastq file
-2  # Antisense fastq file
-x  # Genome fasta
-q  # Minimum mean base quality

```
Currently the pipeline supports only paired end sequencing and the input files must be well formed, with reads in the same order.

##### Additional flags
```
-p  # A user supplied prefix for naming the output
```
This can be any string that is valid as a director name

```
-o  # Output directory. This is the destination of the output files
-a  # Annotation directory. This is where the bowtie2 index files are sent
-d  # Data directory. This is the destination of intermediate data files
```

By default all of these are set to the current working directory. The user can specify a more meaningful project layout if desired. I kept my genome files in a separate annotation directory and all of my fastq and alignment files in a separate data directory. My output, specified by the assignment is sent to its own directory. None of this is required for the pipeline though.


