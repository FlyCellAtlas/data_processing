# Part 1 - Index Hopping Filtering and Cell Ranger

## 1.1. Index Hopping Filter

This step is using the `index-hopping-filter` to remove reads that were likely hopped during sequencing.

The `index_hopping_filter/metadata` folder contains the resulting files of running:

```
./index-hopping-filter mkcsv <INPUT>
```

## 1.2. Cell Ranger

This step is about running the Cell Ranger software using the VSN-Pipelines. The `cell_ranger/batch{1,2,3,4}` folders contains:
- Nextflow config.
- A `metadata.tsv` file used with the Nextflow pipeline containing parameter values to run Cell Ranger (e.g.: path to FASTQ files, number expected cells).
