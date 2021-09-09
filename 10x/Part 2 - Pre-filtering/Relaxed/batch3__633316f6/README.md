# Generate config

```{bash}
nextflow config $VSN -profile tenx,single_sample_scrublet,singularity > nextflow.config
```

# Run 

```
nextflow -C nextflow.config run $VSN -entry single_sample_scrublet
```

