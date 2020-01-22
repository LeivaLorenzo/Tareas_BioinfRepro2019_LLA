###<span style="color:green">**denovo_map.pl**</span> versus <span style="color:green">**ref_map.pl**</span>

Here are some key differences in running <span style="color:green">**denovo_map.pl**</span> versus <span style="color:green">**ref_map.pl**</span>:
- Both pipelines can be run for either a genetic map or population analysis.

- <span style="color:green">**denovo_map.pl**</span> takes data in FASTQ, or FASTA format, compressed or uncompressed.
- <span style="color:green">**denovo_map.pl**</span> will execute the pipeline, running <span style="color:green">**ustacks**</span> to assemble loci in each individual de novo, calling SNPs in each assembled locus. It will then executing <span style="color:green">**cstacks**</span> to build the catalog followed by <span style="color:green">**sstacks**</span> to match either the parents and progeny, or all the generic samples against the catalog. Next, it will run  <span style="color:green">**tsv2bam**</span> to transpose data from being store per-sample to be stored per-locus, then it will run <span style="color:green">**gstacks**</span> to assemble paired-end contigs (if paired-end data is provided) and re-call SNPs using the population-wide data.

- <span style="color:green">**ref_map.pl**</span> expects data that has been aligned to a reference genome, and accepts either SAM or BAM files.

- <span style="color:green">**ref_map.pl**</span> will execute the pipeline, running <span style="color:green">**gstacks**</span> to build and genotype single- or paired-end data and call SNPs using the population-wide data per locus.

