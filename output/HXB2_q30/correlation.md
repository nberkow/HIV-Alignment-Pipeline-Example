
## Correlation Between Read Coverage and Sequence Content





### Nucleotide Content of Genome
Check the background nucleotide content of the genome. Note any extreme nucleotide biases.


```
## 
##    a    c    g    t 
## 3411 1772 2373 2163
```

### Percent Nucleotide Content
Nucleotide content as a percentage of all bases in the genome


```
## 
##     a     c     g     t 
## 35.10 18.23 24.42 22.26
```

![plot of chunk unnamed-chunk-4](../output/test/figure/unnamed-chunk-4-1.png)

### Read Coverage
Look at the distribution of read coverage scores across the genome. Also examine the distributions for each nucleotide.

![plot of chunk unnamed-chunk-5](../output/test/figure/unnamed-chunk-5-1.png)![plot of chunk unnamed-chunk-5](../output/test/figure/unnamed-chunk-5-2.png)


### Average Read Coverage Per Nucleotide
Check the naive average read coverage at each nucleotide, without normalizing to genomic nucleotide bias

![plot of chunk unnamed-chunk-6](../output/test/figure/unnamed-chunk-6-1.png)

### Pairwise Nucleotide Coverage Differences
Checking for significant coverage differences between the nucleotides. This uses a non-parametric Mann-Whitney-Wilcoxon test because read coverages are unlikely to be normally distributed.

The null hypothesis is that any two nucleotides have the same average read coverage. In general we will reject this hypothesis if the p-value is less than $\alpha$ after correction for multiple testing. For an experiment wide $\alpha$ of 0.05, the p-value threshold is 0.0083 after a Bonferonni correction ($\alpha$ = 0.05/6).


```
## n1 	 vs 	 n2 	 p-value
```

```
## a 	 vs 	 c 	 2.695545e-05 
## a 	 vs 	 g 	 3.327225e-05 
## a 	 vs 	 t 	 0.0001316622 
## c 	 vs 	 g 	 0.7489494 
## c 	 vs 	 t 	 0.6322539 
## g 	 vs 	 t 	 0.8940316
```

### Sliding Window Analysis
Checking nucleotide enrichment vs coverage in a 100nt sliding window across the genome. This reveals whether regions of the genome with a higher than average representation of one nucleotide, compared to that nucleotide's genomic representation, tend to have higher coverage.


![plot of chunk unnamed-chunk-8](../output/test/figure/unnamed-chunk-8-1.png)




















