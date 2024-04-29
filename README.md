# binding_FASTQs

When outsourcing the sequencing, it may happen that more than one FASTQ (pair) is returned per sample. This is due to the sequencing center running a second sequencing with our samples, after not meeting the requested depth with the first run.

## Bind Single End FASTQs

The simplest scenario, simply bind all the FASTQs related to our samples. To do so:

```bash
zcat MY_SAMPLE_*.fastq.gz | gzip > binded_MY_SAMPLE.fastq.gz
```

## Bind Pair End FASTQs

Here, the same logic applies. However, make sure to bind forward with forward and reverse with reverse. If both strands follow the same name order, there should be no porblem.

```bash
zcat MY_SAMPLE_*_R1.fastq.gz | gzip > binded_MY_SAMPLE_R1.fastq.gz
zcat MY_SAMPLE_*_R2.fastq.gz | gzip > binded_MY_SAMPLE_R2.fastq.gz
```
