# Data


# Config

```
nextflow config \
   vib-singlecell-nf/vsn-pipelines \
   -profile h5ad,utils_sample_annotate,scanpy_regress_out,pcacv,directs,harmony,dm6,scenic,scenic_use_cistarget_motifs,scenic_use_cistarget_tracks,log,singularity \
   -r 0.21.0 \
   > nextflow.config
```

# Run 

```
nextflow -C nextflow.config run vib-singlecell-nf/vsn-pipelines -entry harmony_scenic -r 0.21.0
```

# Output

```
executor >  local (116), pbs (1)
[83/c00019] process > single_sample_scenic:SINGLE_SAMPLE:SC__FILE_CONVERTER (1)                                                                                                 [100%] 1 of 1 _
[74/ddada3] process > single_sample_scenic:SINGLE_SAMPLE:SCANPY__SINGLE_SAMPLE:FILTER_AND_ANNOTATE_AND_CLEAN:SC__ANNOTATE_BY_SAMPLE_METADATA (1)                                [100%] 1 of 1 _
[99/3c3462] process > single_sample_scenic:SINGLE_SAMPLE:SCANPY__SINGLE_SAMPLE:QC_FILTER:SC__SCANPY__COMPUTE_QC_STATS (1)                                                       [100%] 1 of 1 _
[7b/cc52bd] process > single_sample_scenic:SINGLE_SAMPLE:SCANPY__SINGLE_SAMPLE:QC_FILTER:SC__SCANPY__CELL_FILTER (1)                                                            [100%] 1 of 1 _
[6f/dd0b91] process > single_sample_scenic:SINGLE_SAMPLE:SCANPY__SINGLE_SAMPLE:QC_FILTER:SC__SCANPY__GENE_FILTER (1)                                                            [100%] 1 of 1 _
[2b/ff4c1d] process > single_sample_scenic:SINGLE_SAMPLE:SCANPY__SINGLE_SAMPLE:QC_FILTER:GENERATE_DUAL_INPUT_REPORT:SC__SCANPY__GENERATE_DUAL_INPUT_REPORT (1)                  [100%] 1 of 1 _
[2b/f05fe4] process > single_sample_scenic:SINGLE_SAMPLE:SCANPY__SINGLE_SAMPLE:QC_FILTER:GENERATE_DUAL_INPUT_REPORT:SC__SCANPY__REPORT_TO_HTML (1)                              [100%] 1 of 1 _
[54/c5f447] process > single_sample_scenic:SINGLE_SAMPLE:SCANPY__SINGLE_SAMPLE:NORMALIZE_TRANSFORM:SC__SCANPY__NORMALIZATION (1)                                                [100%] 1 of 1 _
[ec/7c3638] process > single_sample_scenic:SINGLE_SAMPLE:SCANPY__SINGLE_SAMPLE:NORMALIZE_TRANSFORM:PUBLISH_H5AD_NORMALIZED:COMPRESS_HDF5 (1)                                    [100%] 1 of 1 _
[38/66f606] process > single_sample_scenic:SINGLE_SAMPLE:SCANPY__SINGLE_SAMPLE:NORMALIZE_TRANSFORM:PUBLISH_H5AD_NORMALIZED:SC__PUBLISH (1)                                      [100%] 1 of 1 _
[04/3b5d7a] process > single_sample_scenic:SINGLE_SAMPLE:SCANPY__SINGLE_SAMPLE:NORMALIZE_TRANSFORM:PUBLISH_H5AD_NORMALIZED:SC__PUBLISH_PROXY (1)                                [100%] 1 of 1 _
[eb/13eae5] process > single_sample_scenic:SINGLE_SAMPLE:SCANPY__SINGLE_SAMPLE:NORMALIZE_TRANSFORM:SC__SCANPY__DATA_TRANSFORMATION (1)                                          [100%] 1 of 1 _
[c7/97ff77] process > single_sample_scenic:SINGLE_SAMPLE:SCANPY__SINGLE_SAMPLE:HVG_SELECTION:SC__SCANPY__FIND_HIGHLY_VARIABLE_GENES (1)                                         [100%] 1 of 1 _
[58/a7c7de] process > single_sample_scenic:SINGLE_SAMPLE:SCANPY__SINGLE_SAMPLE:HVG_SELECTION:SC__SCANPY__SUBSET_HIGHLY_VARIABLE_GENES (1)                                       [100%] 1 of 1 _
[12/dd2401] process > single_sample_scenic:SINGLE_SAMPLE:SCANPY__SINGLE_SAMPLE:HVG_SELECTION:SC__SCANPY__REGRESS_OUT (1)                                                        [100%] 1 of 1 _
[42/24a653] process > single_sample_scenic:SINGLE_SAMPLE:SCANPY__SINGLE_SAMPLE:HVG_SELECTION:SC__SCANPY__FEATURE_SCALING (1)                                                    [100%] 1 of 1 _
[86/49abe8] process > single_sample_scenic:SINGLE_SAMPLE:SCANPY__SINGLE_SAMPLE:HVG_SELECTION:PUBLISH_H5AD_HVG_SCALED:COMPRESS_HDF5 (1)                                          [100%] 1 of 1 _
[ef/b53869] process > single_sample_scenic:SINGLE_SAMPLE:SCANPY__SINGLE_SAMPLE:HVG_SELECTION:PUBLISH_H5AD_HVG_SCALED:SC__PUBLISH (1)                                            [100%] 1 of 1 _
[63/4dcd6e] process > single_sample_scenic:SINGLE_SAMPLE:SCANPY__SINGLE_SAMPLE:HVG_SELECTION:PUBLISH_H5AD_HVG_SCALED:SC__PUBLISH_PROXY (1)                                      [100%] 1 of 1 _
[55/0f1a62] process > single_sample_scenic:SINGLE_SAMPLE:SCANPY__SINGLE_SAMPLE:HVG_SELECTION:GENERATE_REPORT:SC__SCANPY__GENERATE_REPORT (1)                                    [100%] 1 of 1 _
[39/d50fc7] process > single_sample_scenic:SINGLE_SAMPLE:SCANPY__SINGLE_SAMPLE:HVG_SELECTION:GENERATE_REPORT:SC__SCANPY__REPORT_TO_HTML (1)                                     [100%] 1 of 1 _
[ab/37f8d0] process > single_sample_scenic:SINGLE_SAMPLE:SCANPY__SINGLE_SAMPLE:DIM_REDUCTION_PCA:PCACV__FIND_OPTIMAL_NPCS (1)                                                   [100%] 1 of 1 _
[38/5d7229] process > single_sample_scenic:SINGLE_SAMPLE:SCANPY__SINGLE_SAMPLE:DIM_REDUCTION_PCA:SC__SCANPY__DIM_REDUCTION__PCA (1)                                             [100%] 1 of 1 _
[e6/6c22ae] process > single_sample_scenic:SINGLE_SAMPLE:SCANPY__SINGLE_SAMPLE:NEIGHBORHOOD_GRAPH:SC__SCANPY__NEIGHBORHOOD_GRAPH (1)                                            [100%] 1 of 1 _
[f7/e64ec2] process > single_sample_scenic:SINGLE_SAMPLE:SCANPY__SINGLE_SAMPLE:DIM_REDUCTION_TSNE_UMAP:SC__SCANPY__DIM_REDUCTION__TSNE (1)                                      [100%] 1 of 1 _
[10/372044] process > single_sample_scenic:SINGLE_SAMPLE:SCANPY__SINGLE_SAMPLE:DIM_REDUCTION_TSNE_UMAP:SC__SCANPY__DIM_REDUCTION__UMAP (1)                                      [100%] 1 of 1 _
[a6/ac5663] process > single_sample_scenic:SINGLE_SAMPLE:SCANPY__SINGLE_SAMPLE:DIM_REDUCTION_TSNE_UMAP:GENERATE_REPORT:SC__SCANPY__GENERATE_REPORT (1)                          [100%] 1 of 1 _
[c7/5572d4] process > single_sample_scenic:SINGLE_SAMPLE:SCANPY__SINGLE_SAMPLE:DIM_REDUCTION_TSNE_UMAP:GENERATE_REPORT:SC__SCANPY__REPORT_TO_HTML (1)                           [100%] 1 of 1 _
[12/6e520d] process > single_sample_scenic:SINGLE_SAMPLE:SCANPY__SINGLE_SAMPLE:CLUSTER_IDENTIFICATION:SC__SCANPY__PARAM_EXPLORE_CLUSTERING (13)                                 [100%] 13 of 13 _
[9b/95b644] process > single_sample_scenic:SINGLE_SAMPLE:SCANPY__SINGLE_SAMPLE:CLUSTER_IDENTIFICATION:GENERATE_REPORT:SC__SCANPY__PARAM_EXPLORE_CLUSTERING_GENERATE_REPORT (13) [100%] 13 of 13 _
[31/6cfbf5] process > single_sample_scenic:SINGLE_SAMPLE:SCANPY__SINGLE_SAMPLE:CLUSTER_IDENTIFICATION:GENERATE_REPORT:SC__SCANPY__REPORT_TO_HTML (13)                           [100%] 13 of 13 _
[d9/81d42a] process > single_sample_scenic:SINGLE_SAMPLE:SCANPY__SINGLE_SAMPLE:CLUSTER_IDENTIFICATION:SC__SCANPY__PARAM_EXPLORE_MARKER_GENES (13)                               [100%] 13 of 13 _
[9d/120927] process > single_sample_scenic:SINGLE_SAMPLE:SCANPY__SINGLE_SAMPLE:UTILS__GENERATE_WORKFLOW_CONFIG_REPORT                                                           [100%] 1 of 1 _
[47/3788fb] process > single_sample_scenic:SINGLE_SAMPLE:SCANPY__SINGLE_SAMPLE:SC__SCANPY__MERGE_REPORTS (1)                                                                    [100%] 1 of 1 _
[85/68925e] process > single_sample_scenic:SINGLE_SAMPLE:SCANPY__SINGLE_SAMPLE:SC__SCANPY__REPORT_TO_HTML (1)                                                                   [100%] 1 of 1 _
[d7/cf6fa3] process > single_sample_scenic:SINGLE_SAMPLE:SCANPY__SINGLE_SAMPLE:FINALIZE:SC__H5AD_TO_FILTERED_LOOM (1)                                                           [100%] 1 of 1 _
[cb/13e990] process > single_sample_scenic:SINGLE_SAMPLE:SCANPY__SINGLE_SAMPLE:FINALIZE:FILE_CONVERTER_TO_SCOPE:SC__H5AD_TO_LOOM (1)                                            [100%] 1 of 1 _
[67/256351] process > single_sample_scenic:SINGLE_SAMPLE:SCANPY__SINGLE_SAMPLE:FINALIZE:FILE_CONVERTER_TO_SCANPY:SC__H5AD_MERGE (1)                                             [100%] 1 of 1 _
[58/05ca52] process > single_sample_scenic:SINGLE_SAMPLE:SCANPY__SINGLE_SAMPLE:PUBLISH:SC__PUBLISH_PROXY (13)                                                                   [100%] 13 of 13 _
[93/9cd095] process > single_sample_scenic:SINGLE_SAMPLE:SC__DIRECTS__SELECT_DEFAULT_CLUSTERING (1)                                                                             [100%] 1 of 1 _
[e7/e16717] process > single_sample_scenic:PUBLISH_SCANPY:COMPRESS_HDF5 (1)                                                                                                     [100%] 1 of 1 _
[9d/1a6053] process > single_sample_scenic:PUBLISH_SCANPY:SC__PUBLISH (1)                                                                                                       [100%] 1 of 1 _
[a0/712e4e] process > single_sample_scenic:PUBLISH_SCANPY:SC__PUBLISH_PROXY (1)                                                                                                 [100%] 1 of 1 _
[fc/c50a1f] process > single_sample_scenic:SCENIC_APPEND:scenic:ARBORETO_WITH_MULTIPROCESSING (1)                                                                               [100%] 1 of 1 _
[33/45ccea] process > single_sample_scenic:SCENIC_APPEND:scenic:CISTARGET__MOTIF (1)                                                                                            [100%] 1 of 1 _
[db/9f44a3] process > single_sample_scenic:SCENIC_APPEND:scenic:CISTARGET__TRACK (1)                                                                                            [100%] 1 of 1 _
[4f/1e29f0] process > single_sample_scenic:SCENIC_APPEND:scenic:AUCELL__MOTIF (1)                                                                                               [100%] 1 of 1 _
[be/864ff5] process > single_sample_scenic:SCENIC_APPEND:scenic:AUCELL__TRACK (1)                                                                                               [100%] 1 of 1 _
[18/ba8adc] process > single_sample_scenic:SCENIC_APPEND:scenic:MERGE_MOTIF_TRACK_LOOMS (1)                                                                                     [100%] 1 of 1 _
[0d/9ae10b] process > single_sample_scenic:SCENIC_APPEND:scenic:VISUALIZE (1)                                                                                                   [100%] 1 of 1 _
[56/fe932f] process > single_sample_scenic:SCENIC_APPEND:scenic:PUBLISH_LOOM (1)                                                                                                [100%] 1 of 1 _
[38/599ffc] process > single_sample_scenic:SCENIC_APPEND:APPEND_SCENIC_LOOM (1)                                                                                                 [100%] 1 of 1 _
[2f/10dc2a] process > single_sample_scenic:SCENIC_APPEND:GENERATE_REPORT (1)                                                                                                    [100%] 1 of 1 _
[53/6515c6] process > single_sample_scenic:SCENIC_APPEND:REPORT_TO_HTML (1)                                                                                                     [100%] 1 of 1 _
[d9/1374fd] process > single_sample_scenic:PUBLISH_SCOPE:COMPRESS_HDF5 (1)                                                                                                      [100%] 1 of 1 _
[24/34569e] process > single_sample_scenic:PUBLISH_SCOPE:SC__PUBLISH (1)                                                                                                        [100%] 1 of 1 _
[1f/13cb43] process > single_sample_scenic:PUBLISH_SCOPE:SC__PUBLISH_PROXY (1)                                                                                                  [100%] 1 of 1 _
WARN: To render the execution DAG in the required format it is required to install Graphviz -- See http://www.graphviz.org for more info.
Duration    : 2h 54m 54s
CPU hours   : 35.8
Succeeded   : 117
```
