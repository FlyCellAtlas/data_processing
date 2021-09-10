# Data

Total number of cells: 31401, genes: 12460.

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
[9b/01a172] process > harmony_scenic:HARMONY:SC__FILE_CONVERTER (1)                                                                                       [100%] 2 of 2 _                                                                                                           
[5f/0a2122] process > harmony_scenic:HARMONY:FILTER_AND_ANNOTATE_AND_CLEAN:SC__ANNOTATE_BY_SAMPLE_METADATA (2)                                            [100%] 2 of 2 _                                                                                                           
[4f/81f601] process > harmony_scenic:HARMONY:QC_FILTER:SC__SCANPY__COMPUTE_QC_STATS (2)                                                                   [100%] 2 of 2 _                                                                                                           
[77/3102f3] process > harmony_scenic:HARMONY:QC_FILTER:SC__SCANPY__CELL_FILTER (2)                                                                        [100%] 2 of 2 _                                                                                                           
[9b/1eb93f] process > harmony_scenic:HARMONY:QC_FILTER:SC__SCANPY__GENE_FILTER (2)                                                                        [100%] 2 of 2 _                                                                                                           
[8a/8e5a7d] process > harmony_scenic:HARMONY:QC_FILTER:GENERATE_DUAL_INPUT_REPORT:SC__SCANPY__GENERATE_DUAL_INPUT_REPORT (2)                              [100%] 2 of 2 _                                                                                                           
[45/a74d27] process > harmony_scenic:HARMONY:QC_FILTER:GENERATE_DUAL_INPUT_REPORT:SC__SCANPY__REPORT_TO_HTML (2)                                          [100%] 2 of 2 _                                                                                                           
[bb/178ffb] process > harmony_scenic:HARMONY:SC__FILE_CONCATENATOR                                                                                        [100%] 1 of 1 _                                                                                                           
[67/24fb4d] process > harmony_scenic:HARMONY:NORMALIZE_TRANSFORM:SC__SCANPY__NORMALIZATION                                                                [100%] 1 of 1 _                                                                                                           
[dc/99578d] process > harmony_scenic:HARMONY:NORMALIZE_TRANSFORM:PUBLISH_H5AD_NORMALIZED:COMPRESS_HDF5                                                    [100%] 1 of 1 _                                                                                                           
[61/e81fc1] process > harmony_scenic:HARMONY:NORMALIZE_TRANSFORM:PUBLISH_H5AD_NORMALIZED:SC__PUBLISH                                                      [100%] 1 of 1 _                                                                                                           
[23/87dbd8] process > harmony_scenic:HARMONY:NORMALIZE_TRANSFORM:PUBLISH_H5AD_NORMALIZED:SC__PUBLISH_PROXY                                                [100%] 1 of 1 _                                                                                                           
[e2/8eb539] process > harmony_scenic:HARMONY:NORMALIZE_TRANSFORM:SC__SCANPY__DATA_TRANSFORMATION                                                          [100%] 1 of 1 _                                                                                                           
[7f/7d4b7d] process > harmony_scenic:HARMONY:HVG_SELECTION:SC__SCANPY__FIND_HIGHLY_VARIABLE_GENES                                                         [100%] 1 of 1 _                                                                                                           
[51/8284cc] process > harmony_scenic:HARMONY:HVG_SELECTION:SC__SCANPY__SUBSET_HIGHLY_VARIABLE_GENES                                                       [100%] 1 of 1 _                                                                                                           
[06/d32d09] process > harmony_scenic:HARMONY:HVG_SELECTION:SC__SCANPY__REGRESS_OUT                                                                        [100%] 1 of 1 _                                                                                                           
[23/6b8b6d] process > harmony_scenic:HARMONY:HVG_SELECTION:SC__SCANPY__FEATURE_SCALING                                                                    [100%] 1 of 1 _  
[58/2da5c9] process > harmony_scenic:HARMONY:HVG_SELECTION:PUBLISH_H5AD_HVG_SCALED:COMPRESS_HDF5                                                          [100%] 1 of 1 _
[93/481b50] process > harmony_scenic:HARMONY:HVG_SELECTION:PUBLISH_H5AD_HVG_SCALED:SC__PUBLISH                                                            [100%] 1 of 1 _
[32/c92797] process > harmony_scenic:HARMONY:HVG_SELECTION:PUBLISH_H5AD_HVG_SCALED:SC__PUBLISH_PROXY                                                      [100%] 1 of 1 _  
[cd/43820a] process > harmony_scenic:HARMONY:HVG_SELECTION:GENERATE_REPORT:SC__SCANPY__GENERATE_REPORT                                                    [100%] 1 of 1 _  
[5d/f0c1f0] process > harmony_scenic:HARMONY:HVG_SELECTION:GENERATE_REPORT:SC__SCANPY__REPORT_TO_HTML                                                     [100%] 1 of 1 _  
[94/591186] process > harmony_scenic:HARMONY:DIM_REDUCTION_PCA:PCACV__FIND_OPTIMAL_NPCS                                                                   [100%] 1 of 1 _  
[c0/1dda9e] process > harmony_scenic:HARMONY:DIM_REDUCTION_PCA:SC__SCANPY__DIM_REDUCTION__PCA (1)                                                         [100%] 1 of 1 _  
[7d/1ec7e1] process > harmony_scenic:HARMONY:NEIGHBORHOOD_GRAPH:SC__SCANPY__NEIGHBORHOOD_GRAPH (1)                                                        [100%] 1 of 1 _  
[f9/aeea76] process > harmony_scenic:HARMONY:DIM_REDUCTION_TSNE_UMAP:SC__SCANPY__DIM_REDUCTION__TSNE (1)                                                  [100%] 1 of 1 _  
[1c/4e3ca5] process > harmony_scenic:HARMONY:DIM_REDUCTION_TSNE_UMAP:SC__SCANPY__DIM_REDUCTION__UMAP (1)                                                  [100%] 1 of 1 _
[97/eb3085] process > harmony_scenic:HARMONY:DIM_REDUCTION_TSNE_UMAP:GENERATE_REPORT:SC__SCANPY__GENERATE_REPORT (1)                                      [100%] 1 of 1 _
[ac/3f7c64] process > harmony_scenic:HARMONY:DIM_REDUCTION_TSNE_UMAP:GENERATE_REPORT:SC__SCANPY__REPORT_TO_HTML (1)                                       [100%] 1 of 1 _  
[f7/25ba96] process > harmony_scenic:HARMONY:CLUSTER_IDENTIFICATION:SC__SCANPY__PARAM_EXPLORE_CLUSTERING (10)                                             [100%] 13 of 13 _
[42/9da2b3] process > harmony_scenic:HARMONY:CLUSTER_IDENTIFICATION:GENERATE_REPORT:SC__SCANPY__PARAM_EXPLORE_CLUSTERING_GENERATE_REPORT (13)             [100%] 13 of 13 _
[ba/eb076b] process > harmony_scenic:HARMONY:CLUSTER_IDENTIFICATION:GENERATE_REPORT:SC__SCANPY__REPORT_TO_HTML (13)                                       [100%] 13 of 13 _
[f6/26d9e2] process > harmony_scenic:HARMONY:CLUSTER_IDENTIFICATION:SC__SCANPY__PARAM_EXPLORE_MARKER_GENES (13)                                           [100%] 13 of 13 _
[d3/f7b10a] process > harmony_scenic:HARMONY:BEC_HARMONY:SC__HARMONY__HARMONY_MATRIX (1)                                                                  [100%] 1 of 1 _  
[94/29f675] process > harmony_scenic:HARMONY:BEC_HARMONY:SC__H5AD_UPDATE_X_PCA (1)                                                                        [100%] 1 of 1 _  
[e4/dc670a] process > harmony_scenic:HARMONY:BEC_HARMONY:PUBLISH_BEC_OUTPUT:COMPRESS_HDF5 (1)                                                             [100%] 1 of 1 _
[d8/229ee4] process > harmony_scenic:HARMONY:BEC_HARMONY:PUBLISH_BEC_OUTPUT:SC__PUBLISH (1)                                                               [100%] 1 of 1 _
[7f/386636] process > harmony_scenic:HARMONY:BEC_HARMONY:PUBLISH_BEC_OUTPUT:SC__PUBLISH_PROXY (1)                                                         [100%] 1 of 1 _  
[69/5b786a] process > harmony_scenic:HARMONY:BEC_HARMONY:NEIGHBORHOOD_GRAPH:SC__SCANPY__NEIGHBORHOOD_GRAPH (1)                                            [100%] 1 of 1 _  
[5b/6831e2] process > harmony_scenic:HARMONY:BEC_HARMONY:DIM_REDUCTION_TSNE_UMAP:SC__SCANPY__DIM_REDUCTION__TSNE (1)                                      [100%] 1 of 1 _  
[ca/24f7a7] process > harmony_scenic:HARMONY:BEC_HARMONY:DIM_REDUCTION_TSNE_UMAP:SC__SCANPY__DIM_REDUCTION__UMAP (1)                                      [100%] 1 of 1 _  
[84/0e0ac2] process > harmony_scenic:HARMONY:BEC_HARMONY:DIM_REDUCTION_TSNE_UMAP:GENERATE_REPORT:SC__SCANPY__GENERATE_REPORT (1)                          [100%] 1 of 1 _  
[ac/6c8b74] process > harmony_scenic:HARMONY:BEC_HARMONY:DIM_REDUCTION_TSNE_UMAP:GENERATE_REPORT:SC__SCANPY__REPORT_TO_HTML (1)                           [100%] 1 of 1 _  
[9c/538bbb] process > harmony_scenic:HARMONY:BEC_HARMONY:PUBLISH_BEC_DIMRED_OUTPUT:COMPRESS_HDF5 (1)                                                      [100%] 1 of 1 _  
[ef/ecb1f4] process > harmony_scenic:HARMONY:BEC_HARMONY:PUBLISH_BEC_DIMRED_OUTPUT:SC__PUBLISH (1)                                                        [100%] 1 of 1 _
[9e/85a285] process > harmony_scenic:HARMONY:BEC_HARMONY:PUBLISH_BEC_DIMRED_OUTPUT:SC__PUBLISH_PROXY (1)                                                  [100%] 1 of 1 _
[25/885349] process > harmony_scenic:HARMONY:BEC_HARMONY:CLUSTER_IDENTIFICATION:SC__SCANPY__PARAM_EXPLORE_CLUSTERING (9)                                  [100%] 13 of 13 _
[37/db6c9a] process > harmony_scenic:HARMONY:BEC_HARMONY:CLUSTER_IDENTIFICATION:GENERATE_REPORT:SC__SCANPY__PARAM_EXPLORE_CLUSTERING_GENERATE_REPORT (13) [100%] 13 of 13 _
[49/c51d45] process > harmony_scenic:HARMONY:BEC_HARMONY:CLUSTER_IDENTIFICATION:GENERATE_REPORT:SC__SCANPY__REPORT_TO_HTML (13)                           [100%] 13 of 13 _
[24/9c823a] process > harmony_scenic:HARMONY:BEC_HARMONY:CLUSTER_IDENTIFICATION:SC__SCANPY__PARAM_EXPLORE_MARKER_GENES (12)                               [100%] 13 of 13 _
[eb/8e379f] process > harmony_scenic:HARMONY:BEC_HARMONY:PUBLISH_FINAL_HARMONY_OUTPUT:SC__PUBLISH_PROXY (13)                                              [100%] 13 of 13 _
[48/20a0c3] process > harmony_scenic:HARMONY:BEC_HARMONY:GENERATE_DUAL_INPUT_REPORT:SC__SCANPY__GENERATE_DUAL_INPUT_REPORT (13)                           [100%] 13 of 13 _
[99/5344eb] process > harmony_scenic:HARMONY:BEC_HARMONY:GENERATE_DUAL_INPUT_REPORT:SC__SCANPY__REPORT_TO_HTML (13)                                       [100%] 13 of 13 _
[e2/b21841] process > harmony_scenic:HARMONY:FINALIZE:SC__H5AD_TO_FILTERED_LOOM                                                                           [100%] 1 of 1 _
[c2/8307ab] process > harmony_scenic:HARMONY:FINALIZE:FILE_CONVERTER_TO_SCOPE:SC__H5AD_TO_LOOM (1)                                                        [100%] 1 of 1 _
[a7/7e5473] process > harmony_scenic:HARMONY:FINALIZE:FILE_CONVERTER_TO_SCANPY:SC__H5AD_MERGE (1)                                                         [100%] 1 of 1 _
[52/163a28] process > harmony_scenic:HARMONY:SC__DIRECTS__SELECT_DEFAULT_CLUSTERING (1)                                                                   [100%] 1 of 1 _
[96/d22ca8] process > harmony_scenic:HARMONY:UTILS__GENERATE_WORKFLOW_CONFIG_REPORT                                                                       [100%] 1 of 1 _
[55/aeabb4] process > harmony_scenic:HARMONY:SC__SCANPY__MERGE_REPORTS (13)                                                                               [100%] 13 of 13 _
[96/d418c4] process > harmony_scenic:HARMONY:SC__SCANPY__REPORT_TO_HTML (13)                                                                              [100%] 13 of 13 _
[d5/179e13] process > harmony_scenic:PUBLISH_HARMONY:COMPRESS_HDF5 (1)                                                                                    [100%] 1 of 1 _
[cc/758a66] process > harmony_scenic:PUBLISH_HARMONY:SC__PUBLISH (1)                                                                                      [100%] 1 of 1 _
[02/4f41b5] process > harmony_scenic:PUBLISH_HARMONY:SC__PUBLISH_PROXY (1)                                                                                [100%] 1 of 1 _
[0e/27ccc5] process > harmony_scenic:SCENIC_APPEND:scenic:ARBORETO_WITH_MULTIPROCESSING (1)                                                               [100%] 1 of 1 _
[0d/ac2fae] process > harmony_scenic:SCENIC_APPEND:scenic:CISTARGET__MOTIF (1)                                                                            [100%] 1 of 1 _
[83/089091] process > harmony_scenic:SCENIC_APPEND:scenic:CISTARGET__TRACK (1)                                                                            [100%] 1 of 1 _
[43/f5ee08] process > harmony_scenic:SCENIC_APPEND:scenic:AUCELL__MOTIF (1)                                                                               [100%] 1 of 1 _
[9a/11c905] process > harmony_scenic:SCENIC_APPEND:scenic:AUCELL__TRACK (1)                                                                               [100%] 1 of 1 _
[5b/2c17a1] process > harmony_scenic:SCENIC_APPEND:scenic:MERGE_MOTIF_TRACK_LOOMS (1)                                                                     [100%] 1 of 1 _
[c7/51db72] process > harmony_scenic:SCENIC_APPEND:scenic:VISUALIZE (1)                                                                                   [100%] 1 of 1 _
[07/779687] process > harmony_scenic:SCENIC_APPEND:scenic:PUBLISH_LOOM (1)                                                                                [100%] 1 of 1 _
[63/f7c071] process > harmony_scenic:SCENIC_APPEND:APPEND_SCENIC_LOOM (1)                                                                                 [100%] 1 of 1 _
[09/0c3334] process > harmony_scenic:SCENIC_APPEND:GENERATE_REPORT (1)                                                                                    [100%] 1 of 1 _
[69/79e3f9] process > harmony_scenic:SCENIC_APPEND:REPORT_TO_HTML (1)                                                                                     [100%] 1 of 1 _
[5e/80db47] process > harmony_scenic:PUBLISH_HARMONY_SCENIC:COMPRESS_HDF5 (1)                                                                             [100%] 1 of 1 _
[6a/059b8f] process > harmony_scenic:PUBLISH_HARMONY_SCENIC:SC__PUBLISH (1)                                                                               [100%] 1 of 1 _
[a0/5c1a55] process > harmony_scenic:PUBLISH_HARMONY_SCENIC:SC__PUBLISH_PROXY (1)                                                                         [100%] 1 of 1 _
WARN: To render the execution DAG in the required format it is required to install Graphviz -- See http://www.graphviz.org for more info.
Duration    : 5h 52m 1s
CPU hours   : 99.9
Succeeded   : 240
```
