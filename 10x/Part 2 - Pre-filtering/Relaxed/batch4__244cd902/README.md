# Generate config

```{bash}
nextflow config \
	vib-singlecell-nf/vsn-pipelines \
	-profile tenx,single_sample_scrublet,singularity \
	-r 0.21.0 \
	> nextflow.config
```

# Run 

```
nextflow \
	-C nextflow.config \
	run vib-singlecell-nf/vsn-pipelines \
	-r 0.21.0 \
	-entry single_sample_scrublet
```

