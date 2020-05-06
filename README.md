# BioHub Data VSN-Pipelines Runs

Runs performed by VSN-Pipelines on the BioHub data

More info about the VSN-Pipelines can be found [here](https://vsn-pipelines.readthedocs.io/en/latest/)

## 20200422_000__all__d6a0bcb0-84a5-11ea-8bbd-a0000220fe80

Batches: 1 + 2
Samples: all

VSN-Pipeline (v0.18.0): `single_sample_scrublet` (aka Single-sample + Scrublet on each individual sample)

Create the config
```
nextflow -r 3e3a6db8b0 config \
   vib-singlecell-nf/vsn-pipelines \
      tenx,single_sample_scrublet,singularity \
      > nextflow.config
```

Run,
```
nextflow -C nextflow.config \
   run -r 3e3a6db8b0 \
      vib-singlecell-nf/vsn-pipelines \
      -entry single_sample_scrublet
```

Running time: ~40min

This run was performed mainly to remove doublets. The reports related to the doublet removal by Scrublet can be found on the Fly Cell Atlas Nextcloud:

```
analysis/in-house/20200422_000__all__d6a0bcb0-84a5-11ea-8bbd-a0000220fe80/out/notebooks/intermediate/*.SC_Scrublet_doublet_detection_report.{ipynb,html}
```


## 20200424_000__all__4b9e9810-8600-11ea-867e-a0000220fe80

Batches: 1 + 2
Samples: all

VSN-Pipeline (v0.18.0): `bbknn_scenic`. This pipeline runs the `bbknn` workflow above, then runs the `scenic` workflow on the output, generating a comprehensive loom file with the combined results.

Create the config
```
nextflow config \
   vib-singlecell-nf/vsn-pipelines \
      h5ad,pcacv,bbknn,dm6,scenic,scenic_use_cistarget_motifs,scenic_use_cistarget_tracks,singularity \
      > nextflow.config
```

Run,
```
nextflow -C nextflow.config \
   run -r 3e3a6db8b0 \
      vib-singlecell-nf/vsn-pipelines \
      -entry bbknn_scenic
```


Running time: ~3d 21h. (The bottleneck was the GRN inference which took ~5200min).

The reports related to this run can be found on the Fly Cell Atlas Nextcloud:

```
analysis/in-house/20200424_000__all__4b9e9810-8600-11ea-867e-a0000220fe80/out/notebooks/
```
