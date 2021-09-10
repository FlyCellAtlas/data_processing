# Data

Total number of cells: 11788, genes: 13407.

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
executor >  local (239), pbs (1)                                                                                                                                                                                                                                                    
[32/e1c2b4] process > harmony_scenic:HARMONY:SC__FILE_CONVERTER (1)                                            [100%] 2 of 2 _                                                                                                                                                      
[9a/594412] process > harmony_scenic:HARMONY:FILTER_AND_ANNOTATE_AND_CLEAN:SC__ANNOTATE_BY_SAMPLE_METADATA (2) [100%] 2 of 2 _                                                                                                                                                      
[da/5f3801] process > harmony_scenic:HARMONY:QC_FILTER:SC__SCANPY__COMPUTE_QC_STATS (1)                        [100%] 2 of 2 _                                                                                                                                                      
[59/5149a2] process > harmony_scenic:HARMONY:QC_FILTER:SC__SCANPY__CELL_FILTER (1)                             [100%] 2 of 2 _                                                                                                                                                      
[82/1a001e] process > harmony_scenic:HARMONY:QC_FILTER:SC__SCANPY__GENE_FILTER (2)                             [100%] 2 of 2 _                                                                                                                                                      
[17/b42057] process > harmony_scenic:HARMONY:QC_FILTER:GENERATE_DUAL_INPUT_REPORT:SC__SCANPY__GENERATE_DUAL... [100%] 2 of 2 _                                                                                                                                                      
[40/a1eb3e] process > harmony_scenic:HARMONY:QC_FILTER:GENERATE_DUAL_INPUT_REPORT:SC__SCANPY__REPORT_TO_HTM... [100%] 2 of 2 _                                                                                                                                                      
[b3/e8744f] process > harmony_scenic:HARMONY:SC__FILE_CONCATENATOR                                             [100%] 1 of 1 _                                                                                                                                                      
[af/289359] process > harmony_scenic:HARMONY:NORMALIZE_TRANSFORM:SC__SCANPY__NORMALIZATION                     [100%] 1 of 1 _                                                                                                                                                      
[9e/b34d74] process > harmony_scenic:HARMONY:NORMALIZE_TRANSFORM:PUBLISH_H5AD_NORMALIZED:COMPRESS_HDF5         [100%] 1 of 1 _                                                                                                                                                      
[f1/eef7d9] process > harmony_scenic:HARMONY:NORMALIZE_TRANSFORM:PUBLISH_H5AD_NORMALIZED:SC__PUBLISH           [100%] 1 of 1 _                                                                                                                                                      
[2a/2bfc60] process > harmony_scenic:HARMONY:NORMALIZE_TRANSFORM:PUBLISH_H5AD_NORMALIZED:SC__PUBLISH_PROXY     [100%] 1 of 1 _                                                                                                                                                      
[3b/0456f1] process > harmony_scenic:HARMONY:NORMALIZE_TRANSFORM:SC__SCANPY__DATA_TRANSFORMATION               [100%] 1 of 1 _                                                                                                                                                      
[58/8b73c2] process > harmony_scenic:HARMONY:HVG_SELECTION:SC__SCANPY__FIND_HIGHLY_VARIABLE_GENES              [100%] 1 of 1 _                                                                                                                                                      
[8a/29c9e9] process > harmony_scenic:HARMONY:HVG_SELECTION:SC__SCANPY__SUBSET_HIGHLY_VARIABLE_GENES            [100%] 1 of 1 _                                                                                                                                                      
[bd/4520a2] process > harmony_scenic:HARMONY:HVG_SELECTION:SC__SCANPY__REGRESS_OUT                             [100%] 1 of 1 _
[f8/2a1c98] process > harmony_scenic:HARMONY:HVG_SELECTION:SC__SCANPY__FEATURE_SCALING                         [100%] 1 of 1 _
[2f/b028e0] process > harmony_scenic:HARMONY:HVG_SELECTION:PUBLISH_H5AD_HVG_SCALED:COMPRESS_HDF5               [100%] 1 of 1 _
[f2/8fad08] process > harmony_scenic:HARMONY:HVG_SELECTION:PUBLISH_H5AD_HVG_SCALED:SC__PUBLISH                 [100%] 1 of 1 _
[6b/3c9cb1] process > harmony_scenic:HARMONY:HVG_SELECTION:PUBLISH_H5AD_HVG_SCALED:SC__PUBLISH_PROXY           [100%] 1 of 1 _
[82/917f99] process > harmony_scenic:HARMONY:HVG_SELECTION:GENERATE_REPORT:SC__SCANPY__GENERATE_REPORT         [100%] 1 of 1 _
[a4/abc0d1] process > harmony_scenic:HARMONY:HVG_SELECTION:GENERATE_REPORT:SC__SCANPY__REPORT_TO_HTML          [100%] 1 of 1 _
[b4/eea0f6] process > harmony_scenic:HARMONY:DIM_REDUCTION_PCA:PCACV__FIND_OPTIMAL_NPCS                        [100%] 1 of 1 _
[7d/a17f07] process > harmony_scenic:HARMONY:DIM_REDUCTION_PCA:SC__SCANPY__DIM_REDUCTION__PCA (1)              [100%] 1 of 1 _
[c1/7ff180] process > harmony_scenic:HARMONY:NEIGHBORHOOD_GRAPH:SC__SCANPY__NEIGHBORHOOD_GRAPH (1)             [100%] 1 of 1 _
[27/9ee331] process > harmony_scenic:HARMONY:DIM_REDUCTION_TSNE_UMAP:SC__SCANPY__DIM_REDUCTION__TSNE (1)       [100%] 1 of 1 _
[a1/f848d9] process > harmony_scenic:HARMONY:DIM_REDUCTION_TSNE_UMAP:SC__SCANPY__DIM_REDUCTION__UMAP (1)       [100%] 1 of 1 _
[0f/15823c] process > harmony_scenic:HARMONY:DIM_REDUCTION_TSNE_UMAP:GENERATE_REPORT:SC__SCANPY__GENERATE_R... [100%] 1 of 1 _
[09/afe85e] process > harmony_scenic:HARMONY:DIM_REDUCTION_TSNE_UMAP:GENERATE_REPORT:SC__SCANPY__REPORT_TO_... [100%] 1 of 1 _
[b7/573e75] process > harmony_scenic:HARMONY:CLUSTER_IDENTIFICATION:SC__SCANPY__PARAM_EXPLORE_CLUSTERING (13)  [100%] 13 of 13 _
[ac/5e3379] process > harmony_scenic:HARMONY:CLUSTER_IDENTIFICATION:GENERATE_REPORT:SC__SCANPY__PARAM_EXPLO... [100%] 13 of 13 _
[50/8386f4] process > harmony_scenic:HARMONY:CLUSTER_IDENTIFICATION:GENERATE_REPORT:SC__SCANPY__REPORT_TO_H... [100%] 13 of 13 _
[55/d8ae81] process > harmony_scenic:HARMONY:CLUSTER_IDENTIFICATION:SC__SCANPY__PARAM_EXPLORE_MARKER_GENES ... [100%] 13 of 13 _
[b3/6469a9] process > harmony_scenic:HARMONY:BEC_HARMONY:SC__HARMONY__HARMONY_MATRIX (1)                       [100%] 1 of 1 _
[68/921ba4] process > harmony_scenic:HARMONY:BEC_HARMONY:SC__H5AD_UPDATE_X_PCA (1)                             [100%] 1 of 1 _
[c6/3c44cd] process > harmony_scenic:HARMONY:BEC_HARMONY:PUBLISH_BEC_OUTPUT:COMPRESS_HDF5 (1)                  [100%] 1 of 1 _
[d5/3c613e] process > harmony_scenic:HARMONY:BEC_HARMONY:PUBLISH_BEC_OUTPUT:SC__PUBLISH (1)                    [100%] 1 of 1 _
[02/8fa7e3] process > harmony_scenic:HARMONY:BEC_HARMONY:PUBLISH_BEC_OUTPUT:SC__PUBLISH_PROXY (1)              [100%] 1 of 1 _
[49/7eb8c2] process > harmony_scenic:HARMONY:BEC_HARMONY:NEIGHBORHOOD_GRAPH:SC__SCANPY__NEIGHBORHOOD_GRAPH (1) [100%] 1 of 1 _
[6b/4bbd5a] process > harmony_scenic:HARMONY:BEC_HARMONY:DIM_REDUCTION_TSNE_UMAP:SC__SCANPY__DIM_REDUCTION_... [100%] 1 of 1 _
[91/7cd1dd] process > harmony_scenic:HARMONY:BEC_HARMONY:DIM_REDUCTION_TSNE_UMAP:SC__SCANPY__DIM_REDUCTION_... [100%] 1 of 1 _
[1a/f5c70a] process > harmony_scenic:HARMONY:BEC_HARMONY:DIM_REDUCTION_TSNE_UMAP:GENERATE_REPORT:SC__SCANPY... [100%] 1 of 1 _
[06/e89b7b] process > harmony_scenic:HARMONY:BEC_HARMONY:DIM_REDUCTION_TSNE_UMAP:GENERATE_REPORT:SC__SCANPY... [100%] 1 of 1 _
[d7/77a810] process > harmony_scenic:HARMONY:BEC_HARMONY:PUBLISH_BEC_DIMRED_OUTPUT:COMPRESS_HDF5 (1)           [100%] 1 of 1 _
[5a/5f81c9] process > harmony_scenic:HARMONY:BEC_HARMONY:PUBLISH_BEC_DIMRED_OUTPUT:SC__PUBLISH (1)             [100%] 1 of 1 _
[b5/41089d] process > harmony_scenic:HARMONY:BEC_HARMONY:PUBLISH_BEC_DIMRED_OUTPUT:SC__PUBLISH_PROXY (1)       [100%] 1 of 1 _
[73/f423ba] process > harmony_scenic:HARMONY:BEC_HARMONY:CLUSTER_IDENTIFICATION:SC__SCANPY__PARAM_EXPLORE_C... [100%] 13 of 13 _
[ae/0d7221] process > harmony_scenic:HARMONY:BEC_HARMONY:CLUSTER_IDENTIFICATION:GENERATE_REPORT:SC__SCANPY_... [100%] 13 of 13 _
[47/1bee65] process > harmony_scenic:HARMONY:BEC_HARMONY:CLUSTER_IDENTIFICATION:GENERATE_REPORT:SC__SCANPY_... [100%] 13 of 13 _
[d8/b0be84] process > harmony_scenic:HARMONY:BEC_HARMONY:CLUSTER_IDENTIFICATION:SC__SCANPY__PARAM_EXPLORE_M... [100%] 13 of 13 _
[cb/448ca1] process > harmony_scenic:HARMONY:BEC_HARMONY:PUBLISH_FINAL_HARMONY_OUTPUT:SC__PUBLISH_PROXY (13)   [100%] 13 of 13 _
[87/ce867d] process > harmony_scenic:HARMONY:BEC_HARMONY:GENERATE_DUAL_INPUT_REPORT:SC__SCANPY__GENERATE_DU... [100%] 13 of 13 _
[89/cbf9cb] process > harmony_scenic:HARMONY:BEC_HARMONY:GENERATE_DUAL_INPUT_REPORT:SC__SCANPY__REPORT_TO_H... [100%] 13 of 13 _
[bb/7507c6] process > harmony_scenic:HARMONY:FINALIZE:SC__H5AD_TO_FILTERED_LOOM                                [100%] 1 of 1 _
[42/643127] process > harmony_scenic:HARMONY:FINALIZE:FILE_CONVERTER_TO_SCOPE:SC__H5AD_TO_LOOM (1)             [100%] 1 of 1 _
[88/bed1d7] process > harmony_scenic:HARMONY:FINALIZE:FILE_CONVERTER_TO_SCANPY:SC__H5AD_MERGE (1)              [100%] 1 of 1 _
[39/4626bc] process > harmony_scenic:HARMONY:SC__DIRECTS__SELECT_DEFAULT_CLUSTERING (1)                        [100%] 1 of 1 _
[14/3547ca] process > harmony_scenic:HARMONY:UTILS__GENERATE_WORKFLOW_CONFIG_REPORT                            [100%] 1 of 1 _
[29/d806e7] process > harmony_scenic:HARMONY:SC__SCANPY__MERGE_REPORTS (13)                                    [100%] 13 of 13 _
[8d/800ee6] process > harmony_scenic:HARMONY:SC__SCANPY__REPORT_TO_HTML (13)                                   [100%] 13 of 13 _
[6f/acf3a6] process > harmony_scenic:PUBLISH_HARMONY:COMPRESS_HDF5 (1)                                         [100%] 1 of 1 _
[16/f40e1f] process > harmony_scenic:PUBLISH_HARMONY:SC__PUBLISH (1)                                           [100%] 1 of 1 _
[e9/8d774f] process > harmony_scenic:PUBLISH_HARMONY:SC__PUBLISH_PROXY (1)                                     [100%] 1 of 1 _
[01/e874ae] process > harmony_scenic:SCENIC_APPEND:scenic:ARBORETO_WITH_MULTIPROCESSING (1)                    [100%] 1 of 1 _
[de/c57d0e] process > harmony_scenic:SCENIC_APPEND:scenic:CISTARGET__MOTIF (1)                                 [100%] 1 of 1 _
[de/4168dc] process > harmony_scenic:SCENIC_APPEND:scenic:CISTARGET__TRACK (1)                                 [100%] 1 of 1 _
[00/6a9f25] process > harmony_scenic:SCENIC_APPEND:scenic:AUCELL__MOTIF (1)                                    [100%] 1 of 1 _
[2f/576207] process > harmony_scenic:SCENIC_APPEND:scenic:AUCELL__TRACK (1)                                    [100%] 1 of 1 _
[18/e1dfba] process > harmony_scenic:SCENIC_APPEND:scenic:MERGE_MOTIF_TRACK_LOOMS (1)                          [100%] 1 of 1 _
[57/93a227] process > harmony_scenic:SCENIC_APPEND:scenic:VISUALIZE (1)                                        [100%] 1 of 1 _
[fa/2e2b14] process > harmony_scenic:SCENIC_APPEND:scenic:PUBLISH_LOOM (1)                                     [100%] 1 of 1 _
[7e/5f9504] process > harmony_scenic:SCENIC_APPEND:APPEND_SCENIC_LOOM (1)                                      [100%] 1 of 1 _
[f2/86a04a] process > harmony_scenic:SCENIC_APPEND:GENERATE_REPORT (1)                                         [100%] 1 of 1 _
[fd/aa1f9f] process > harmony_scenic:SCENIC_APPEND:REPORT_TO_HTML (1)                                          [100%] 1 of 1 _
[10/8f6162] process > harmony_scenic:PUBLISH_HARMONY_SCENIC:COMPRESS_HDF5 (1)                                  [100%] 1 of 1 _
[db/20249d] process > harmony_scenic:PUBLISH_HARMONY_SCENIC:SC__PUBLISH (1)                                    [100%] 1 of 1 _
[d0/be5d9d] process > harmony_scenic:PUBLISH_HARMONY_SCENIC:SC__PUBLISH_PROXY (1)                              [100%] 1 of 1 _
WARN: To render the execution DAG in the required format it is required to install Graphviz -- See http://www.graphviz.org for more info.
Duration    : 3h 50m 55s
CPU hours   : 42.8
Succeeded   : 240
```
