# Data

Total number of cells: 26301, genes: 12802.

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
nextflow -C nextflow.config run $VSN -entry harmony_scenic -r 0.21.0
```

# Output

```
executor >  local (253), pbs (1)                                                                                                                                                                                                                                           [16/1420]
[b3/4d0d9f] process > harmony_scenic:HARMONY:SC__FILE_CONVERTER (3)                                            [100%] 4 of 4 _                                                                                                                                                      
[fa/4d9945] process > harmony_scenic:HARMONY:FILTER_AND_ANNOTATE_AND_CLEAN:SC__ANNOTATE_BY_SAMPLE_METADATA (4) [100%] 4 of 4 _                                                                                                                                                      
[2a/5ee066] process > harmony_scenic:HARMONY:QC_FILTER:SC__SCANPY__COMPUTE_QC_STATS (4)                        [100%] 4 of 4 _                                                                                                                                                      
[8f/443001] process > harmony_scenic:HARMONY:QC_FILTER:SC__SCANPY__CELL_FILTER (4)                             [100%] 4 of 4 _                                                                                                                                                      
[da/768932] process > harmony_scenic:HARMONY:QC_FILTER:SC__SCANPY__GENE_FILTER (3)                             [100%] 4 of 4 _                                                                                                                                                      
[88/cfa875] process > harmony_scenic:HARMONY:QC_FILTER:GENERATE_DUAL_INPUT_REPORT:SC__SCANPY__GENERATE_DUAL... [100%] 4 of 4 _                                                                                                                                                      
[c4/427d08] process > harmony_scenic:HARMONY:QC_FILTER:GENERATE_DUAL_INPUT_REPORT:SC__SCANPY__REPORT_TO_HTM... [100%] 4 of 4 _                                                                                                                                                      
[f4/50f722] process > harmony_scenic:HARMONY:SC__FILE_CONCATENATOR                                             [100%] 1 of 1 _                                                                                                                                                      
[e2/667154] process > harmony_scenic:HARMONY:NORMALIZE_TRANSFORM:SC__SCANPY__NORMALIZATION                     [100%] 1 of 1 _                                                                                                                                                      
[78/d4b08a] process > harmony_scenic:HARMONY:NORMALIZE_TRANSFORM:PUBLISH_H5AD_NORMALIZED:COMPRESS_HDF5         [100%] 1 of 1 _                                                                                                                                                      
[d0/874b16] process > harmony_scenic:HARMONY:NORMALIZE_TRANSFORM:PUBLISH_H5AD_NORMALIZED:SC__PUBLISH           [100%] 1 of 1 _                                                                                                                                                      
[9d/0c6835] process > harmony_scenic:HARMONY:NORMALIZE_TRANSFORM:PUBLISH_H5AD_NORMALIZED:SC__PUBLISH_PROXY     [100%] 1 of 1 _                                                                                                                                                      
[a7/6505fc] process > harmony_scenic:HARMONY:NORMALIZE_TRANSFORM:SC__SCANPY__DATA_TRANSFORMATION               [100%] 1 of 1 _                                                                                                                                                      
[fd/3ad602] process > harmony_scenic:HARMONY:HVG_SELECTION:SC__SCANPY__FIND_HIGHLY_VARIABLE_GENES              [100%] 1 of 1 _                                                                                                                                                      
[fa/de8ae4] process > harmony_scenic:HARMONY:HVG_SELECTION:SC__SCANPY__SUBSET_HIGHLY_VARIABLE_GENES            [100%] 1 of 1 _                                                                                                                                                      
[96/b8307e] process > harmony_scenic:HARMONY:HVG_SELECTION:SC__SCANPY__REGRESS_OUT                             [100%] 1 of 1 _                                                                                                                                                      
[58/e4152b] process > harmony_scenic:HARMONY:HVG_SELECTION:SC__SCANPY__FEATURE_SCALING                         [100%] 1 of 1 _
[2d/5104ca] process > harmony_scenic:HARMONY:HVG_SELECTION:PUBLISH_H5AD_HVG_SCALED:COMPRESS_HDF5               [100%] 1 of 1 _
[e8/04c1d1] process > harmony_scenic:HARMONY:HVG_SELECTION:PUBLISH_H5AD_HVG_SCALED:SC__PUBLISH                 [100%] 1 of 1 _
[af/67715d] process > harmony_scenic:HARMONY:HVG_SELECTION:PUBLISH_H5AD_HVG_SCALED:SC__PUBLISH_PROXY           [100%] 1 of 1 _
[c0/820f6f] process > harmony_scenic:HARMONY:HVG_SELECTION:GENERATE_REPORT:SC__SCANPY__GENERATE_REPORT         [100%] 1 of 1 _
[90/13e8ed] process > harmony_scenic:HARMONY:HVG_SELECTION:GENERATE_REPORT:SC__SCANPY__REPORT_TO_HTML          [100%] 1 of 1 _
[eb/1ea9c4] process > harmony_scenic:HARMONY:DIM_REDUCTION_PCA:PCACV__FIND_OPTIMAL_NPCS                        [100%] 1 of 1 _
[b9/3ef4ad] process > harmony_scenic:HARMONY:DIM_REDUCTION_PCA:SC__SCANPY__DIM_REDUCTION__PCA (1)              [100%] 1 of 1 _
[84/e42708] process > harmony_scenic:HARMONY:NEIGHBORHOOD_GRAPH:SC__SCANPY__NEIGHBORHOOD_GRAPH (1)             [100%] 1 of 1 _
[1d/6767e9] process > harmony_scenic:HARMONY:DIM_REDUCTION_TSNE_UMAP:SC__SCANPY__DIM_REDUCTION__TSNE (1)       [100%] 1 of 1 _
[f2/9bde46] process > harmony_scenic:HARMONY:DIM_REDUCTION_TSNE_UMAP:SC__SCANPY__DIM_REDUCTION__UMAP (1)       [100%] 1 of 1 _
[8c/4bae88] process > harmony_scenic:HARMONY:DIM_REDUCTION_TSNE_UMAP:GENERATE_REPORT:SC__SCANPY__GENERATE_R... [100%] 1 of 1 _
[cf/ee984d] process > harmony_scenic:HARMONY:DIM_REDUCTION_TSNE_UMAP:GENERATE_REPORT:SC__SCANPY__REPORT_TO_... [100%] 1 of 1 _
[c2/24cb7b] process > harmony_scenic:HARMONY:CLUSTER_IDENTIFICATION:SC__SCANPY__PARAM_EXPLORE_CLUSTERING (12)  [100%] 13 of 13 _
[d8/e2b6f7] process > harmony_scenic:HARMONY:CLUSTER_IDENTIFICATION:GENERATE_REPORT:SC__SCANPY__PARAM_EXPLO... [100%] 13 of 13 _
[c6/8e4280] process > harmony_scenic:HARMONY:CLUSTER_IDENTIFICATION:GENERATE_REPORT:SC__SCANPY__REPORT_TO_H... [100%] 13 of 13 _
[2b/296aa2] process > harmony_scenic:HARMONY:CLUSTER_IDENTIFICATION:SC__SCANPY__PARAM_EXPLORE_MARKER_GENES ... [100%] 13 of 13 _
[4c/a5ce70] process > harmony_scenic:HARMONY:BEC_HARMONY:SC__HARMONY__HARMONY_MATRIX (1)                       [100%] 1 of 1 _
[7c/bf4973] process > harmony_scenic:HARMONY:BEC_HARMONY:SC__H5AD_UPDATE_X_PCA (1)                             [100%] 1 of 1 _
[d1/98355f] process > harmony_scenic:HARMONY:BEC_HARMONY:PUBLISH_BEC_OUTPUT:COMPRESS_HDF5 (1)                  [100%] 1 of 1 _
[3a/c11d0d] process > harmony_scenic:HARMONY:BEC_HARMONY:PUBLISH_BEC_OUTPUT:SC__PUBLISH (1)                    [100%] 1 of 1 _
[91/b365db] process > harmony_scenic:HARMONY:BEC_HARMONY:PUBLISH_BEC_OUTPUT:SC__PUBLISH_PROXY (1)              [100%] 1 of 1 _
[b3/d3c9e9] process > harmony_scenic:HARMONY:BEC_HARMONY:NEIGHBORHOOD_GRAPH:SC__SCANPY__NEIGHBORHOOD_GRAPH (1) [100%] 1 of 1 _
[0f/a4181b] process > harmony_scenic:HARMONY:BEC_HARMONY:DIM_REDUCTION_TSNE_UMAP:SC__SCANPY__DIM_REDUCTION_... [100%] 1 of 1 _
[4e/123072] process > harmony_scenic:HARMONY:BEC_HARMONY:DIM_REDUCTION_TSNE_UMAP:SC__SCANPY__DIM_REDUCTION_... [100%] 1 of 1 _
[ac/5f110a] process > harmony_scenic:HARMONY:BEC_HARMONY:DIM_REDUCTION_TSNE_UMAP:GENERATE_REPORT:SC__SCANPY... [100%] 1 of 1 _
[6f/470cb1] process > harmony_scenic:HARMONY:BEC_HARMONY:DIM_REDUCTION_TSNE_UMAP:GENERATE_REPORT:SC__SCANPY... [100%] 1 of 1 _
[1f/337aa3] process > harmony_scenic:HARMONY:BEC_HARMONY:PUBLISH_BEC_DIMRED_OUTPUT:COMPRESS_HDF5 (1)           [100%] 1 of 1 _
[27/bc0231] process > harmony_scenic:HARMONY:BEC_HARMONY:PUBLISH_BEC_DIMRED_OUTPUT:SC__PUBLISH (1)             [100%] 1 of 1 _
[57/1c5e46] process > harmony_scenic:HARMONY:BEC_HARMONY:PUBLISH_BEC_DIMRED_OUTPUT:SC__PUBLISH_PROXY (1)       [100%] 1 of 1 _
[ec/b02030] process > harmony_scenic:HARMONY:BEC_HARMONY:CLUSTER_IDENTIFICATION:SC__SCANPY__PARAM_EXPLORE_C... [100%] 13 of 13 _
[95/a180db] process > harmony_scenic:HARMONY:BEC_HARMONY:CLUSTER_IDENTIFICATION:GENERATE_REPORT:SC__SCANPY_... [100%] 13 of 13 _
[2b/547ae8] process > harmony_scenic:HARMONY:BEC_HARMONY:CLUSTER_IDENTIFICATION:GENERATE_REPORT:SC__SCANPY_... [100%] 13 of 13 _
[88/c96f3b] process > harmony_scenic:HARMONY:BEC_HARMONY:CLUSTER_IDENTIFICATION:SC__SCANPY__PARAM_EXPLORE_M... [100%] 13 of 13 _
[26/d8dfc7] process > harmony_scenic:HARMONY:BEC_HARMONY:PUBLISH_FINAL_HARMONY_OUTPUT:SC__PUBLISH_PROXY (13)   [100%] 13 of 13 _
[1b/a416e3] process > harmony_scenic:HARMONY:BEC_HARMONY:GENERATE_DUAL_INPUT_REPORT:SC__SCANPY__GENERATE_DU... [100%] 13 of 13 _
[6f/884f91] process > harmony_scenic:HARMONY:BEC_HARMONY:GENERATE_DUAL_INPUT_REPORT:SC__SCANPY__REPORT_TO_H... [100%] 13 of 13 _
[3a/c29217] process > harmony_scenic:HARMONY:FINALIZE:SC__H5AD_TO_FILTERED_LOOM                                [100%] 1 of 1 _
[65/7f1707] process > harmony_scenic:HARMONY:FINALIZE:FILE_CONVERTER_TO_SCOPE:SC__H5AD_TO_LOOM (1)             [100%] 1 of 1 _
[28/ec680c] process > harmony_scenic:HARMONY:FINALIZE:FILE_CONVERTER_TO_SCANPY:SC__H5AD_MERGE (1)              [100%] 1 of 1 _
[fc/30d5ec] process > harmony_scenic:HARMONY:SC__DIRECTS__SELECT_DEFAULT_CLUSTERING (1)                        [100%] 1 of 1 _
[06/6b8aee] process > harmony_scenic:HARMONY:UTILS__GENERATE_WORKFLOW_CONFIG_REPORT                            [100%] 1 of 1 _
[0c/c31b13] process > harmony_scenic:HARMONY:SC__SCANPY__MERGE_REPORTS (13)                                    [100%] 13 of 13 _
[95/3062c0] process > harmony_scenic:HARMONY:SC__SCANPY__REPORT_TO_HTML (13)                                   [100%] 13 of 13 _
[e9/9ddcd6] process > harmony_scenic:PUBLISH_HARMONY:COMPRESS_HDF5 (1)                                         [100%] 1 of 1 _
[b8/5f4122] process > harmony_scenic:PUBLISH_HARMONY:SC__PUBLISH (1)                                           [100%] 1 of 1 _
[c4/e70292] process > harmony_scenic:PUBLISH_HARMONY:SC__PUBLISH_PROXY (1)                                     [100%] 1 of 1 _
[40/1ea88f] process > harmony_scenic:SCENIC_APPEND:scenic:ARBORETO_WITH_MULTIPROCESSING (1)                    [100%] 1 of 1 _
[2b/059f19] process > harmony_scenic:SCENIC_APPEND:scenic:CISTARGET__MOTIF (1)                                 [100%] 1 of 1 _
[b9/5597e5] process > harmony_scenic:SCENIC_APPEND:scenic:CISTARGET__TRACK (1)                                 [100%] 1 of 1 _
[d9/3e69d9] process > harmony_scenic:SCENIC_APPEND:scenic:AUCELL__MOTIF (1)                                    [100%] 1 of 1 _
[d1/cc98c6] process > harmony_scenic:SCENIC_APPEND:scenic:AUCELL__TRACK (1)                                    [100%] 1 of 1 _
[a3/568f5c] process > harmony_scenic:SCENIC_APPEND:scenic:MERGE_MOTIF_TRACK_LOOMS (1)                          [100%] 1 of 1 _
[a5/1d8a93] process > harmony_scenic:SCENIC_APPEND:scenic:VISUALIZE (1)                                        [100%] 1 of 1 _
[c6/68f948] process > harmony_scenic:SCENIC_APPEND:scenic:PUBLISH_LOOM (1)                                     [100%] 1 of 1 _
[ed/386d66] process > harmony_scenic:SCENIC_APPEND:APPEND_SCENIC_LOOM (1)                                      [100%] 1 of 1 _
[5e/bbe6cd] process > harmony_scenic:SCENIC_APPEND:GENERATE_REPORT (1)                                         [100%] 1 of 1 _
[00/6919cc] process > harmony_scenic:SCENIC_APPEND:REPORT_TO_HTML (1)                                          [100%] 1 of 1 _
[1b/a4f849] process > harmony_scenic:PUBLISH_HARMONY_SCENIC:COMPRESS_HDF5 (1)                                  [100%] 1 of 1 _
[ae/acd5f0] process > harmony_scenic:PUBLISH_HARMONY_SCENIC:SC__PUBLISH (1)                                    [100%] 1 of 1 _
[ab/363497] process > harmony_scenic:PUBLISH_HARMONY_SCENIC:SC__PUBLISH_PROXY (1)                              [100%] 1 of 1 _
WARN: To render the execution DAG in the required format it is required to install Graphviz -- See http://www.graphviz.org for more info.
Duration    : 4h 34m 27s
CPU hours   : 68.2
Succeeded   : 254
```
