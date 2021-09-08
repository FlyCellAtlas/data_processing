# Make the Nextflow configuration file

```
nextflow config \
   /staging/leuven/stg_00002/lcb/dwmax/documents/aertslab/GitHub/vib-singlecell-nf/vsn-pipelines \
   -profile cellranger_count_metadata,singularity,qsub \
   > nextflow.config
```

# Run the Cell Ranger pipeline

```
nextflow \
   -C nextflow.config \
   run /ddn1/vol1/staging/leuven/stg_00002/lcb/dwmax/documents/aertslab/GitHub/vib-singlecell-nf/vsn-pipelines \
      -entry cellranger_metadata
```

