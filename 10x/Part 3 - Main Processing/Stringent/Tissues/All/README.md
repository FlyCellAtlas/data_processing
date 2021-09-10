# Data

Total number of cells: 506660, genes: 16366.

# Config

```
nextflow config vib-singlecell-nf/vsn-pipelines -profile h5ad,utils_sample_annotate,pcacv,harmony,directs,log,singularity -r 0.21.0 > nextflow.config
```

# Run 

```
nextflow -C nextflow.config run vib-singlecell-nf/vsn-pipelines -entry harmony_scenic -r 0.21.0
```

# Output

```
executor >  local (114)                                                                                                                                                                                                                                                     [6/1691]
[45/7abff7] process > harmony:HARMONY:SC__FILE_CONVERTER (61)                                                                                      [100%] 61 of 61, cached: 61 _                                                                                                    
[fa/e29b53] process > harmony:HARMONY:FILTER_AND_ANNOTATE_AND_CLEAN:SC__ANNOTATE_BY_SAMPLE_METADATA (61)                                           [100%] 61 of 61, cached: 61 _                                                                                                    
[d1/fd8f93] process > harmony:HARMONY:QC_FILTER:SC__SCANPY__COMPUTE_QC_STATS (61)                                                                  [100%] 61 of 61, cached: 61 _                                                                                                    
[8f/bebf20] process > harmony:HARMONY:QC_FILTER:SC__SCANPY__CELL_FILTER (61)                                                                       [100%] 61 of 61, cached: 61 _                                                                                                    
[a5/d85d10] process > harmony:HARMONY:QC_FILTER:SC__SCANPY__GENE_FILTER (61)                                                                       [100%] 61 of 61, cached: 61 _                                                                                                    
[18/f33746] process > harmony:HARMONY:QC_FILTER:GENERATE_DUAL_INPUT_REPORT:SC__SCANPY__GENERATE_DUAL_INPUT_REPORT (61)                             [100%] 61 of 61, cached: 61 _                                                                                                    
[44/b89d32] process > harmony:HARMONY:QC_FILTER:GENERATE_DUAL_INPUT_REPORT:SC__SCANPY__REPORT_TO_HTML (61)                                         [100%] 61 of 61, cached: 61 _
[36/2f94ab] process > harmony:HARMONY:SC__FILE_CONCATENATOR                                                                                        [100%] 1 of 1, cached: 1 _
[fe/f0c08c] process > harmony:HARMONY:NORMALIZE_TRANSFORM:SC__SCANPY__NORMALIZATION                                                                [100%] 1 of 1, cached: 1 _
[7a/1ceec8] process > harmony:HARMONY:NORMALIZE_TRANSFORM:PUBLISH_H5AD_NORMALIZED:COMPRESS_HDF5                                                    [100%] 1 of 1, cached: 1 _
[dd/410f26] process > harmony:HARMONY:NORMALIZE_TRANSFORM:PUBLISH_H5AD_NORMALIZED:SC__PUBLISH                                                      [100%] 1 of 1 _
[11/ae8c64] process > harmony:HARMONY:NORMALIZE_TRANSFORM:PUBLISH_H5AD_NORMALIZED:SC__PUBLISH_PROXY                                                [100%] 1 of 1 _
[3f/8e61c2] process > harmony:HARMONY:NORMALIZE_TRANSFORM:SC__SCANPY__DATA_TRANSFORMATION                                                          [100%] 1 of 1, cached: 1 _
[a6/aee043] process > harmony:HARMONY:HVG_SELECTION:SC__SCANPY__FIND_HIGHLY_VARIABLE_GENES                                                         [100%] 1 of 1, cached: 1 _
[0e/48d167] process > harmony:HARMONY:HVG_SELECTION:SC__SCANPY__SUBSET_HIGHLY_VARIABLE_GENES                                                       [100%] 1 of 1, cached: 1 _
[56/f48981] process > harmony:HARMONY:HVG_SELECTION:SC__SCANPY__REGRESS_OUT                                                                        [100%] 1 of 1, cached: 1 _
[a7/9f1394] process > harmony:HARMONY:HVG_SELECTION:SC__SCANPY__FEATURE_SCALING                                                                    [100%] 1 of 1, cached: 1 _
[b3/dbebc0] process > harmony:HARMONY:HVG_SELECTION:PUBLISH_H5AD_HVG_SCALED:COMPRESS_HDF5                                                          [100%] 1 of 1, cached: 1 _
[05/62c277] process > harmony:HARMONY:HVG_SELECTION:PUBLISH_H5AD_HVG_SCALED:SC__PUBLISH                                                            [100%] 1 of 1 _
[61/1ec11d] process > harmony:HARMONY:HVG_SELECTION:PUBLISH_H5AD_HVG_SCALED:SC__PUBLISH_PROXY                                                      [100%] 1 of 1 _
[42/2ea101] process > harmony:HARMONY:HVG_SELECTION:GENERATE_REPORT:SC__SCANPY__GENERATE_REPORT                                                    [100%] 1 of 1, cached: 1 _
[04/8a26e6] process > harmony:HARMONY:HVG_SELECTION:GENERATE_REPORT:SC__SCANPY__REPORT_TO_HTML                                                     [100%] 1 of 1, cached: 1 _
[ed/a2b4e1] process > harmony:HARMONY:DIM_REDUCTION_PCA:PCACV__FIND_OPTIMAL_NPCS                                                                   [100%] 1 of 1, cached: 1 _
[9c/97f52f] process > harmony:HARMONY:DIM_REDUCTION_PCA:SC__SCANPY__DIM_REDUCTION__PCA (1)                                                         [100%] 1 of 1, cached: 1 _
[97/1ff87d] process > harmony:HARMONY:NEIGHBORHOOD_GRAPH:SC__SCANPY__NEIGHBORHOOD_GRAPH (1)                                                        [100%] 1 of 1, cached: 1 _
[61/6faa0f] process > harmony:HARMONY:DIM_REDUCTION_TSNE_UMAP:SC__SCANPY__DIM_REDUCTION__TSNE (1)                                                  [100%] 1 of 1, cached: 1 _
[0c/9294af] process > harmony:HARMONY:DIM_REDUCTION_TSNE_UMAP:SC__SCANPY__DIM_REDUCTION__UMAP (1)                                                  [100%] 1 of 1, cached: 1 _
[a0/6ee53f] process > harmony:HARMONY:DIM_REDUCTION_TSNE_UMAP:GENERATE_REPORT:SC__SCANPY__GENERATE_REPORT (1)                                      [100%] 1 of 1, cached: 1 _
[9b/6e1d7f] process > harmony:HARMONY:DIM_REDUCTION_TSNE_UMAP:GENERATE_REPORT:SC__SCANPY__REPORT_TO_HTML (1)                                       [100%] 1 of 1, cached: 1 _
[0c/3e91b5] process > harmony:HARMONY:CLUSTER_IDENTIFICATION:SC__SCANPY__PARAM_EXPLORE_CLUSTERING (20)                                             [100%] 20 of 20, cached: 20 _
[0c/0354e8] process > harmony:HARMONY:CLUSTER_IDENTIFICATION:GENERATE_REPORT:SC__SCANPY__PARAM_EXPLORE_CLUSTERING_GENERATE_REPORT (20)             [100%] 20 of 20, cached: 20 _
[93/b5af2b] process > harmony:HARMONY:CLUSTER_IDENTIFICATION:GENERATE_REPORT:SC__SCANPY__REPORT_TO_HTML (20)                                       [100%] 20 of 20, cached: 20 _
[ab/474bc3] process > harmony:HARMONY:CLUSTER_IDENTIFICATION:SC__SCANPY__PARAM_EXPLORE_MARKER_GENES (20)                                           [100%] 20 of 20, cached: 20 _
[13/4a8c42] process > harmony:HARMONY:BEC_HARMONY:SC__HARMONY__HARMONY_MATRIX (1)                                                                  [100%] 1 of 1, cached: 1 _
[6f/e21e2d] process > harmony:HARMONY:BEC_HARMONY:SC__H5AD_UPDATE_X_PCA (1)                                                                        [100%] 1 of 1, cached: 1 _
[cb/caa461] process > harmony:HARMONY:BEC_HARMONY:PUBLISH_BEC_OUTPUT:COMPRESS_HDF5 (1)                                                             [100%] 1 of 1, cached: 1 _
[9f/518726] process > harmony:HARMONY:BEC_HARMONY:PUBLISH_BEC_OUTPUT:SC__PUBLISH (1)                                                               [100%] 1 of 1 _
[28/a46b40] process > harmony:HARMONY:BEC_HARMONY:PUBLISH_BEC_OUTPUT:SC__PUBLISH_PROXY (1)                                                         [100%] 1 of 1 _
[02/e18a46] process > harmony:HARMONY:BEC_HARMONY:NEIGHBORHOOD_GRAPH:SC__SCANPY__NEIGHBORHOOD_GRAPH (1)                                            [100%] 1 of 1, cached: 1 _
[54/b9b76f] process > harmony:HARMONY:BEC_HARMONY:DIM_REDUCTION_TSNE_UMAP:SC__SCANPY__DIM_REDUCTION__TSNE (1)                                      [100%] 1 of 1, cached: 1 _
[db/ca1679] process > harmony:HARMONY:BEC_HARMONY:DIM_REDUCTION_TSNE_UMAP:SC__SCANPY__DIM_REDUCTION__UMAP (1)                                      [100%] 1 of 1, cached: 1 _
[d6/e2f126] process > harmony:HARMONY:BEC_HARMONY:DIM_REDUCTION_TSNE_UMAP:GENERATE_REPORT:SC__SCANPY__GENERATE_REPORT (1)                          [100%] 1 of 1, cached: 1 _
[35/4f0299] process > harmony:HARMONY:BEC_HARMONY:DIM_REDUCTION_TSNE_UMAP:GENERATE_REPORT:SC__SCANPY__REPORT_TO_HTML (1)                           [100%] 1 of 1, cached: 1 _
[ba/fd7c67] process > harmony:HARMONY:BEC_HARMONY:PUBLISH_BEC_DIMRED_OUTPUT:COMPRESS_HDF5 (1)                                                      [100%] 1 of 1, cached: 1 _
[8b/becdb5] process > harmony:HARMONY:BEC_HARMONY:PUBLISH_BEC_DIMRED_OUTPUT:SC__PUBLISH (1)                                                        [100%] 1 of 1 _
[29/163488] process > harmony:HARMONY:BEC_HARMONY:PUBLISH_BEC_DIMRED_OUTPUT:SC__PUBLISH_PROXY (1)                                                  [100%] 1 of 1 _
[0b/de3aa4] process > harmony:HARMONY:BEC_HARMONY:CLUSTER_IDENTIFICATION:SC__SCANPY__PARAM_EXPLORE_CLUSTERING (19)                                 [100%] 20 of 20, cached: 20 _
[2c/1fc83e] process > harmony:HARMONY:BEC_HARMONY:CLUSTER_IDENTIFICATION:GENERATE_REPORT:SC__SCANPY__PARAM_EXPLORE_CLUSTERING_GENERATE_REPORT (20) [100%] 20 of 20, cached: 20 _
[2a/3d73ec] process > harmony:HARMONY:BEC_HARMONY:CLUSTER_IDENTIFICATION:GENERATE_REPORT:SC__SCANPY__REPORT_TO_HTML (19)                           [100%] 20 of 20, cached: 20 _
[30/310c17] process > harmony:HARMONY:BEC_HARMONY:CLUSTER_IDENTIFICATION:SC__SCANPY__PARAM_EXPLORE_MARKER_GENES (20)                               [100%] 20 of 20, cached: 20 _
[ca/b6654e] process > harmony:HARMONY:BEC_HARMONY:PUBLISH_FINAL_HARMONY_OUTPUT:SC__PUBLISH_PROXY (20)                                              [100%] 20 of 20 _
[0a/04238f] process > harmony:HARMONY:BEC_HARMONY:GENERATE_DUAL_INPUT_REPORT:SC__SCANPY__GENERATE_DUAL_INPUT_REPORT (20)                           [100%] 20 of 20 _
[a5/8b4d11] process > harmony:HARMONY:BEC_HARMONY:GENERATE_DUAL_INPUT_REPORT:SC__SCANPY__REPORT_TO_HTML (20)                                       [100%] 20 of 20 _
[6c/8b70d0] process > harmony:HARMONY:FINALIZE:SC__H5AD_TO_FILTERED_LOOM                                                                           [100%] 1 of 1, cached: 1 _
[29/23cf90] process > harmony:HARMONY:FINALIZE:FILE_CONVERTER_TO_SCOPE:SC__H5AD_TO_LOOM (1)                                                        [100%] 1 of 1, cached: 1 _
[3a/e6b86e] process > harmony:HARMONY:FINALIZE:FILE_CONVERTER_TO_SCANPY:SC__H5AD_MERGE (1)                                                         [100%] 1 of 1, cached: 1 _
[c0/41ad64] process > harmony:HARMONY:SC__DIRECTS__SELECT_DEFAULT_CLUSTERING (1)                                                                   [100%] 1 of 1 _
[e3/7f8e8e] process > harmony:HARMONY:UTILS__GENERATE_WORKFLOW_CONFIG_REPORT                                                                       [100%] 1 of 1, cached: 1 _
[e0/10bebe] process > harmony:HARMONY:SC__SCANPY__MERGE_REPORTS (20)                                                                               [100%] 20 of 20 _
[b3/505f8a] process > harmony:HARMONY:SC__SCANPY__REPORT_TO_HTML (20)                                                                              [100%] 20 of 20 _
[7c/4667ed] process > harmony:PUBLISH_SCOPE:COMPRESS_HDF5 (1)                                                                                      [100%] 1 of 1 _
[90/c1b5c2] process > harmony:PUBLISH_SCOPE:SC__PUBLISH (1)                                                                                        [100%] 1 of 1 _
[78/76da8e] process > harmony:PUBLISH_SCOPE:SC__PUBLISH_PROXY (1)                                                                                  [100%] 1 of 1 _
[d1/d4d84b] process > harmony:PUBLISH_SCANPY:COMPRESS_HDF5 (1)                                                                                     [100%] 1 of 1, cached: 1 _
[2d/196b62] process > harmony:PUBLISH_SCANPY:SC__PUBLISH (1)                                                                                       [100%] 1 of 1 _
[38/8dbc4d] process > harmony:PUBLISH_SCANPY:SC__PUBLISH_PROXY (1)                                                                                 [100%] 1 of 1 _
WARN: To render the execution DAG in the required format it is required to install Graphviz -- See http://www.graphviz.org for more info.
Duration    : 6h 15m 23s
CPU hours   : 309.6 (94.5% cached)
Succeeded   : 114
Cached      : 619
```
