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

# Notes

FCA53 (`0ece9e7a`) was re-sequenced separetely from this batch. For practical reason, we have included the latest successfull sequecing run of this sample here in this table.