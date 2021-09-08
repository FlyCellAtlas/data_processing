# Make the Nextflow configuration file

```
nextflow config \
   vib-singlecell-nf/vsn-pipelines \
   -profile cellranger_count_metadata,singularity,qsub \
   > nextflow.config
```

# Run the Cell Ranger pipeline

```
nextflow \
   -C nextflow.config \
   run vib-singlecell-nf/vsn-pipelines \
      -entry cellranger_metadata
```

