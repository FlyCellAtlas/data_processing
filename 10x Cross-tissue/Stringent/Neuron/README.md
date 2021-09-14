# Config

```
nextflow config vib-singlecell-nf/vsn-pipelines -profile tenx,utils_sample_annotate,single_sample_decontx_correct_scrublet,log,singularity -r 0.25.0 > nextflow.config
```

# Run

```
nextflow -C nextflow.config run vib-singlecell-nf/vsn-pipelines -entry harmony -r 0.25.0
```
