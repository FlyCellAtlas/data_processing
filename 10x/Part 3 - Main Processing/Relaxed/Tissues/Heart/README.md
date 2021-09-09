# Generate config

```
nextflow config vib-singlecell-nf/vsn-pipelines -profile \
  h5ad,utils_sample_annotate,pcacv,directs,harmony,dm6,scenic,scenic_use_cistarget_motifs,scenic_use_cistarget_tracks,singularity \
  > nextflow.config

```

# Run 

```
nextflow -C nextflow.config run vib-singlecell-nf/vsn-pipelines -entry harmony_scenic
```

