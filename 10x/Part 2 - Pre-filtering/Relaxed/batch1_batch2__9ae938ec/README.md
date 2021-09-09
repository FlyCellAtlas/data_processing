# Generate config

```{bash}
nextflow config vib-singlecell-nf/vsn-pipelines -profile tenx,single_sample_scrublet,singularity > nextflow.config
```

# Run 

```
nextflow -C nextflow.config run vib-singlecell-nf/vsn-pipelines -entry single_sample_scrublet
```

