# Generate config

```
nextflow pull vib-singlecell-nf/vsn-pipelines -r 0.19.0
nextflow config vib-singlecell-nf/vsn-pipelines -profile \
  h5ad,utils_sample_annotate,pcacv,directs,harmony,dm6,scenic,scenic_use_cistarget_motifs,scenic_use_cistarget_tracks,singularity \
  -r 0.19.0 \
  > nextflow.config
```

# Run 

```
nextflow -C nextflow.config run vib-singlecell-nf/vsn-pipelines -entry harmony_scenic -r 0.19.0
```

# Output

```
Duration    : 1h 20m 45s
CPU hours   : 3.7
Succeeded   : 275
```
