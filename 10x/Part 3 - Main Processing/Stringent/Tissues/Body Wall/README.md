# Data

Total number of cells: 16551, genes: 12924.

# Config

```
nextflow config \
   $VSN \
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
[a9/0ac26f] process > harmony_scenic:HARMONY:SC__FILE_CONVERTER (2)                                                                                       [100%] 2 of 2 _                                                                                                           
[cb/b02c42] process > harmony_scenic:HARMONY:FILTER_AND_ANNOTATE_AND_CLEAN:SC__ANNOTATE_BY_SAMPLE_METADATA (2)                                            [100%] 2 of 2 _                                                                                                           
[2b/a95089] process > harmony_scenic:HARMONY:QC_FILTER:SC__SCANPY__COMPUTE_QC_STATS (2)                                                                   [100%] 2 of 2 _                                                                                                           
[af/696e21] process > harmony_scenic:HARMONY:QC_FILTER:SC__SCANPY__CELL_FILTER (2)                                                                        [100%] 2 of 2 _                                                                                                           
[de/bf2faf] process > harmony_scenic:HARMONY:QC_FILTER:SC__SCANPY__GENE_FILTER (2)                                                                        [100%] 2 of 2 _                                                                                                           
[52/4fd12e] process > harmony_scenic:HARMONY:QC_FILTER:GENERATE_DUAL_INPUT_REPORT:SC__SCANPY__GENERATE_DUAL_INPUT_REPORT (2)                              [100%] 2 of 2 _                                                                                                           
[b5/151f8a] process > harmony_scenic:HARMONY:QC_FILTER:GENERATE_DUAL_INPUT_REPORT:SC__SCANPY__REPORT_TO_HTML (2)                                          [100%] 2 of 2 _                                                                                                           
[43/f71d99] process > harmony_scenic:HARMONY:SC__FILE_CONCATENATOR                                                                                        [100%] 1 of 1 _                                                                                                           
[b4/19ed09] process > harmony_scenic:HARMONY:NORMALIZE_TRANSFORM:SC__SCANPY__NORMALIZATION                                                                [100%] 1 of 1 _                                                                                                           
[be/42592b] process > harmony_scenic:HARMONY:NORMALIZE_TRANSFORM:PUBLISH_H5AD_NORMALIZED:COMPRESS_HDF5                                                    [100%] 1 of 1 _                                                                                                           
[4d/9076f9] process > harmony_scenic:HARMONY:NORMALIZE_TRANSFORM:PUBLISH_H5AD_NORMALIZED:SC__PUBLISH                                                      [100%] 1 of 1 _                                                                                                           
[99/64dd5d] process > harmony_scenic:HARMONY:NORMALIZE_TRANSFORM:PUBLISH_H5AD_NORMALIZED:SC__PUBLISH_PROXY                                                [100%] 1 of 1 _                                                                                                           
[c0/e88a3a] process > harmony_scenic:HARMONY:NORMALIZE_TRANSFORM:SC__SCANPY__DATA_TRANSFORMATION                                                          [100%] 1 of 1 _                                                                                                           
[c8/eb58aa] process > harmony_scenic:HARMONY:HVG_SELECTION:SC__SCANPY__FIND_HIGHLY_VARIABLE_GENES                                                         [100%] 1 of 1 _                                                                                                           
[5c/f83c4a] process > harmony_scenic:HARMONY:HVG_SELECTION:SC__SCANPY__SUBSET_HIGHLY_VARIABLE_GENES                                                       [100%] 1 of 1 _                                                                                                           
[a1/8c14b2] process > harmony_scenic:HARMONY:HVG_SELECTION:SC__SCANPY__REGRESS_OUT                                                                        [100%] 1 of 1 _                                                                                                           
[a3/707c26] process > harmony_scenic:HARMONY:HVG_SELECTION:SC__SCANPY__FEATURE_SCALING                                                                    [100%] 1 of 1 _  
[92/b8e913] process > harmony_scenic:HARMONY:HVG_SELECTION:PUBLISH_H5AD_HVG_SCALED:COMPRESS_HDF5                                                          [100%] 1 of 1 _
[17/5b9218] process > harmony_scenic:HARMONY:HVG_SELECTION:PUBLISH_H5AD_HVG_SCALED:SC__PUBLISH                                                            [100%] 1 of 1 _
[0d/8c9e78] process > harmony_scenic:HARMONY:HVG_SELECTION:PUBLISH_H5AD_HVG_SCALED:SC__PUBLISH_PROXY                                                      [100%] 1 of 1 _  
[5c/95d7ea] process > harmony_scenic:HARMONY:HVG_SELECTION:GENERATE_REPORT:SC__SCANPY__GENERATE_REPORT                                                    [100%] 1 of 1 _  
[0c/b5400f] process > harmony_scenic:HARMONY:HVG_SELECTION:GENERATE_REPORT:SC__SCANPY__REPORT_TO_HTML                                                     [100%] 1 of 1 _  
[f9/4f8535] process > harmony_scenic:HARMONY:DIM_REDUCTION_PCA:PCACV__FIND_OPTIMAL_NPCS                                                                   [100%] 1 of 1 _  
[2d/9dbf6b] process > harmony_scenic:HARMONY:DIM_REDUCTION_PCA:SC__SCANPY__DIM_REDUCTION__PCA (1)                                                         [100%] 1 of 1 _  
[2a/db6e05] process > harmony_scenic:HARMONY:NEIGHBORHOOD_GRAPH:SC__SCANPY__NEIGHBORHOOD_GRAPH (1)                                                        [100%] 1 of 1 _  
[88/0ec392] process > harmony_scenic:HARMONY:DIM_REDUCTION_TSNE_UMAP:SC__SCANPY__DIM_REDUCTION__TSNE (1)                                                  [100%] 1 of 1 _  
[6e/ad935f] process > harmony_scenic:HARMONY:DIM_REDUCTION_TSNE_UMAP:SC__SCANPY__DIM_REDUCTION__UMAP (1)                                                  [100%] 1 of 1 _
[56/56b796] process > harmony_scenic:HARMONY:DIM_REDUCTION_TSNE_UMAP:GENERATE_REPORT:SC__SCANPY__GENERATE_REPORT (1)                                      [100%] 1 of 1 _
[ea/f3f95b] process > harmony_scenic:HARMONY:DIM_REDUCTION_TSNE_UMAP:GENERATE_REPORT:SC__SCANPY__REPORT_TO_HTML (1)                                       [100%] 1 of 1 _  
[95/aa3d3b] process > harmony_scenic:HARMONY:CLUSTER_IDENTIFICATION:SC__SCANPY__PARAM_EXPLORE_CLUSTERING (9)                                              [100%] 13 of 13 _
[e4/270e46] process > harmony_scenic:HARMONY:CLUSTER_IDENTIFICATION:GENERATE_REPORT:SC__SCANPY__PARAM_EXPLORE_CLUSTERING_GENERATE_REPORT (13)             [100%] 13 of 13 _
[d9/ff623c] process > harmony_scenic:HARMONY:CLUSTER_IDENTIFICATION:GENERATE_REPORT:SC__SCANPY__REPORT_TO_HTML (13)                                       [100%] 13 of 13 _
[c8/9b5403] process > harmony_scenic:HARMONY:CLUSTER_IDENTIFICATION:SC__SCANPY__PARAM_EXPLORE_MARKER_GENES (12)                                           [100%] 13 of 13 _
[5f/18a8c4] process > harmony_scenic:HARMONY:BEC_HARMONY:SC__HARMONY__HARMONY_MATRIX (1)                                                                  [100%] 1 of 1 _  
[97/3bd48d] process > harmony_scenic:HARMONY:BEC_HARMONY:SC__H5AD_UPDATE_X_PCA (1)                                                                        [100%] 1 of 1 _  
[33/c224f1] process > harmony_scenic:HARMONY:BEC_HARMONY:PUBLISH_BEC_OUTPUT:COMPRESS_HDF5 (1)                                                             [100%] 1 of 1 _
[d6/8c9e5b] process > harmony_scenic:HARMONY:BEC_HARMONY:PUBLISH_BEC_OUTPUT:SC__PUBLISH (1)                                                               [100%] 1 of 1 _
[df/2614bc] process > harmony_scenic:HARMONY:BEC_HARMONY:PUBLISH_BEC_OUTPUT:SC__PUBLISH_PROXY (1)                                                         [100%] 1 of 1 _  
[0f/b97820] process > harmony_scenic:HARMONY:BEC_HARMONY:NEIGHBORHOOD_GRAPH:SC__SCANPY__NEIGHBORHOOD_GRAPH (1)                                            [100%] 1 of 1 _  
[52/b60736] process > harmony_scenic:HARMONY:BEC_HARMONY:DIM_REDUCTION_TSNE_UMAP:SC__SCANPY__DIM_REDUCTION__TSNE (1)                                      [100%] 1 of 1 _  
[01/d3ba3c] process > harmony_scenic:HARMONY:BEC_HARMONY:DIM_REDUCTION_TSNE_UMAP:SC__SCANPY__DIM_REDUCTION__UMAP (1)                                      [100%] 1 of 1 _  
[87/802819] process > harmony_scenic:HARMONY:BEC_HARMONY:DIM_REDUCTION_TSNE_UMAP:GENERATE_REPORT:SC__SCANPY__GENERATE_REPORT (1)                          [100%] 1 of 1 _  
[b6/03afae] process > harmony_scenic:HARMONY:BEC_HARMONY:DIM_REDUCTION_TSNE_UMAP:GENERATE_REPORT:SC__SCANPY__REPORT_TO_HTML (1)                           [100%] 1 of 1 _  
[4a/57c596] process > harmony_scenic:HARMONY:BEC_HARMONY:PUBLISH_BEC_DIMRED_OUTPUT:COMPRESS_HDF5 (1)                                                      [100%] 1 of 1 _  
[d4/8d04c4] process > harmony_scenic:HARMONY:BEC_HARMONY:PUBLISH_BEC_DIMRED_OUTPUT:SC__PUBLISH (1)                                                        [100%] 1 of 1 _
[9b/5a7464] process > harmony_scenic:HARMONY:BEC_HARMONY:PUBLISH_BEC_DIMRED_OUTPUT:SC__PUBLISH_PROXY (1)                                                  [100%] 1 of 1 _
[c5/a3138b] process > harmony_scenic:HARMONY:BEC_HARMONY:CLUSTER_IDENTIFICATION:SC__SCANPY__PARAM_EXPLORE_CLUSTERING (13)                                 [100%] 13 of 13 _
[d1/10240f] process > harmony_scenic:HARMONY:BEC_HARMONY:CLUSTER_IDENTIFICATION:GENERATE_REPORT:SC__SCANPY__PARAM_EXPLORE_CLUSTERING_GENERATE_REPORT (13) [100%] 13 of 13 _
[fe/c903cb] process > harmony_scenic:HARMONY:BEC_HARMONY:CLUSTER_IDENTIFICATION:GENERATE_REPORT:SC__SCANPY__REPORT_TO_HTML (13)                           [100%] 13 of 13 _
[ea/f28e79] process > harmony_scenic:HARMONY:BEC_HARMONY:CLUSTER_IDENTIFICATION:SC__SCANPY__PARAM_EXPLORE_MARKER_GENES (13)                               [100%] 13 of 13 _
[b3/592785] process > harmony_scenic:HARMONY:BEC_HARMONY:PUBLISH_FINAL_HARMONY_OUTPUT:SC__PUBLISH_PROXY (13)                                              [100%] 13 of 13 _
[1e/e7a2f8] process > harmony_scenic:HARMONY:BEC_HARMONY:GENERATE_DUAL_INPUT_REPORT:SC__SCANPY__GENERATE_DUAL_INPUT_REPORT (13)                           [100%] 13 of 13 _
[61/bebc57] process > harmony_scenic:HARMONY:BEC_HARMONY:GENERATE_DUAL_INPUT_REPORT:SC__SCANPY__REPORT_TO_HTML (13)                                       [100%] 13 of 13 _
[49/0e90af] process > harmony_scenic:HARMONY:FINALIZE:SC__H5AD_TO_FILTERED_LOOM                                                                           [100%] 1 of 1 _
[63/35132a] process > harmony_scenic:HARMONY:FINALIZE:FILE_CONVERTER_TO_SCOPE:SC__H5AD_TO_LOOM (1)                                                        [100%] 1 of 1 _
[1b/a9e217] process > harmony_scenic:HARMONY:FINALIZE:FILE_CONVERTER_TO_SCANPY:SC__H5AD_MERGE (1)                                                         [100%] 1 of 1 _
[e9/0ea442] process > harmony_scenic:HARMONY:SC__DIRECTS__SELECT_DEFAULT_CLUSTERING (1)                                                                   [100%] 1 of 1 _
[a2/c5b67b] process > harmony_scenic:HARMONY:UTILS__GENERATE_WORKFLOW_CONFIG_REPORT                                                                       [100%] 1 of 1 _
[90/5bc126] process > harmony_scenic:HARMONY:SC__SCANPY__MERGE_REPORTS (13)                                                                               [100%] 13 of 13 _
[04/989eb2] process > harmony_scenic:HARMONY:SC__SCANPY__REPORT_TO_HTML (13)                                                                              [100%] 13 of 13 _
[8d/96a0f1] process > harmony_scenic:PUBLISH_HARMONY:COMPRESS_HDF5 (1)                                                                                    [100%] 1 of 1 _
[9f/f37575] process > harmony_scenic:PUBLISH_HARMONY:SC__PUBLISH (1)                                                                                      [100%] 1 of 1 _
[e6/8e0d96] process > harmony_scenic:PUBLISH_HARMONY:SC__PUBLISH_PROXY (1)                                                                                [100%] 1 of 1 _
[f8/c4819a] process > harmony_scenic:SCENIC_APPEND:scenic:ARBORETO_WITH_MULTIPROCESSING (1)                                                               [100%] 1 of 1 _
[ae/8a2070] process > harmony_scenic:SCENIC_APPEND:scenic:CISTARGET__MOTIF (1)                                                                            [100%] 1 of 1 _
[d3/640b3e] process > harmony_scenic:SCENIC_APPEND:scenic:CISTARGET__TRACK (1)                                                                            [100%] 1 of 1 _
[f3/e0d107] process > harmony_scenic:SCENIC_APPEND:scenic:AUCELL__MOTIF (1)                                                                               [100%] 1 of 1 _
[b8/e1c009] process > harmony_scenic:SCENIC_APPEND:scenic:AUCELL__TRACK (1)                                                                               [100%] 1 of 1 _
[9b/929373] process > harmony_scenic:SCENIC_APPEND:scenic:MERGE_MOTIF_TRACK_LOOMS (1)                                                                     [100%] 1 of 1 _
[34/da920e] process > harmony_scenic:SCENIC_APPEND:scenic:VISUALIZE (1)                                                                                   [100%] 1 of 1 _
[17/de3a3d] process > harmony_scenic:SCENIC_APPEND:scenic:PUBLISH_LOOM (1)                                                                                [100%] 1 of 1 _
[c4/e28a42] process > harmony_scenic:SCENIC_APPEND:APPEND_SCENIC_LOOM (1)                                                                                 [100%] 1 of 1 _
[b1/11ecaf] process > harmony_scenic:SCENIC_APPEND:GENERATE_REPORT (1)                                                                                    [100%] 1 of 1 _
[89/6e63bc] process > harmony_scenic:SCENIC_APPEND:REPORT_TO_HTML (1)                                                                                     [100%] 1 of 1 _
[ba/20b5fd] process > harmony_scenic:PUBLISH_HARMONY_SCENIC:COMPRESS_HDF5 (1)                                                                             [100%] 1 of 1 _
[71/22620d] process > harmony_scenic:PUBLISH_HARMONY_SCENIC:SC__PUBLISH (1)                                                                               [100%] 1 of 1 _
[f0/99496a] process > harmony_scenic:PUBLISH_HARMONY_SCENIC:SC__PUBLISH_PROXY (1)                                                                         [100%] 1 of 1 _
WARN: To render the execution DAG in the required format it is required to install Graphviz -- See http://www.graphviz.org for more info.
Duration    : 2h 58m 39s
CPU hours   : 42.4
Succeeded   : 240
```
