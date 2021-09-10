# Data

Total number of cells: 100527, genes: 13056.

# Config

```
nextflow config \
   vib-singlecell-nf/vsn-pipelines \
   -profile h5ad,utils_sample_annotate,scanpy_regress_out,pcacv,directs,harmony,dm6,scenic,scenic_use_cistarget_motifs,scenic_use_cistarget_tracks,log,singularity \
   > nextflow.config
```

# Run 

```
nextflow -C nextflow.config run vib-singlecell-nf/vsn-pipelines -entry harmony_scenic -r 0.21.0
```

# Output

```
executor >  local (405), pbs (1)                                                                                                                                                                                                                                                    
[f7/ff5027] process > harmony_scenic:HARMONY:SC__FILE_CONVERTER (4)                                                                                       [100%] 13 of 13 _                                                                                                         
[54/3e805d] process > harmony_scenic:HARMONY:FILTER_AND_ANNOTATE_AND_CLEAN:SC__ANNOTATE_BY_SAMPLE_METADATA (12)                                           [100%] 13 of 13 _                                                                                                         
[5d/0b9b23] process > harmony_scenic:HARMONY:QC_FILTER:SC__SCANPY__COMPUTE_QC_STATS (12)                                                                  [100%] 13 of 13 _                                                                                                         
[d2/d79391] process > harmony_scenic:HARMONY:QC_FILTER:SC__SCANPY__CELL_FILTER (12)                                                                       [100%] 13 of 13 _                                                                                                         
[f1/409170] process > harmony_scenic:HARMONY:QC_FILTER:SC__SCANPY__GENE_FILTER (12)                                                                       [100%] 13 of 13 _                                                                                                         
[72/3b5ed8] process > harmony_scenic:HARMONY:QC_FILTER:GENERATE_DUAL_INPUT_REPORT:SC__SCANPY__GENERATE_DUAL_INPUT_REPORT (13)                             [100%] 13 of 13 _                                                                                                         
[ec/4a1d05] process > harmony_scenic:HARMONY:QC_FILTER:GENERATE_DUAL_INPUT_REPORT:SC__SCANPY__REPORT_TO_HTML (13)                                         [100%] 13 of 13 _                                                                                                         
[14/e9bb55] process > harmony_scenic:HARMONY:SC__FILE_CONCATENATOR                                                                                        [100%] 1 of 1 _                                                                                                           
[c8/fe9e01] process > harmony_scenic:HARMONY:NORMALIZE_TRANSFORM:SC__SCANPY__NORMALIZATION                                                                [100%] 1 of 1 _                                                                                                           
[7d/2ec6d8] process > harmony_scenic:HARMONY:NORMALIZE_TRANSFORM:PUBLISH_H5AD_NORMALIZED:COMPRESS_HDF5                                                    [100%] 1 of 1 _                                                                                                           
[98/eed8c7] process > harmony_scenic:HARMONY:NORMALIZE_TRANSFORM:PUBLISH_H5AD_NORMALIZED:SC__PUBLISH                                                      [100%] 1 of 1 _                                                                                                           
[46/b57517] process > harmony_scenic:HARMONY:NORMALIZE_TRANSFORM:PUBLISH_H5AD_NORMALIZED:SC__PUBLISH_PROXY                                                [100%] 1 of 1 _                                                                                                           
[3b/eb3e16] process > harmony_scenic:HARMONY:NORMALIZE_TRANSFORM:SC__SCANPY__DATA_TRANSFORMATION                                                          [100%] 1 of 1 _                                                                                                           
[df/9bfeda] process > harmony_scenic:HARMONY:HVG_SELECTION:SC__SCANPY__FIND_HIGHLY_VARIABLE_GENES                                                         [100%] 1 of 1 _                                                                                                           
[99/03bb33] process > harmony_scenic:HARMONY:HVG_SELECTION:SC__SCANPY__SUBSET_HIGHLY_VARIABLE_GENES                                                       [100%] 1 of 1 _  
[e8/67a776] process > harmony_scenic:HARMONY:HVG_SELECTION:SC__SCANPY__REGRESS_OUT                                                                        [100%] 1 of 1 _  
[64/0b2757] process > harmony_scenic:HARMONY:HVG_SELECTION:SC__SCANPY__FEATURE_SCALING                                                                    [100%] 1 of 1 _  
[2f/1145b0] process > harmony_scenic:HARMONY:HVG_SELECTION:PUBLISH_H5AD_HVG_SCALED:COMPRESS_HDF5                                                          [100%] 1 of 1 _  
[85/aec363] process > harmony_scenic:HARMONY:HVG_SELECTION:PUBLISH_H5AD_HVG_SCALED:SC__PUBLISH                                                            [100%] 1 of 1 _  
[00/cbea97] process > harmony_scenic:HARMONY:HVG_SELECTION:PUBLISH_H5AD_HVG_SCALED:SC__PUBLISH_PROXY                                                      [100%] 1 of 1 _  
[80/afa96f] process > harmony_scenic:HARMONY:HVG_SELECTION:GENERATE_REPORT:SC__SCANPY__GENERATE_REPORT                                                    [100%] 1 of 1 _  
[0c/f46e77] process > harmony_scenic:HARMONY:HVG_SELECTION:GENERATE_REPORT:SC__SCANPY__REPORT_TO_HTML                                                     [100%] 1 of 1 _  
[18/09fa09] process > harmony_scenic:HARMONY:DIM_REDUCTION_PCA:PCACV__FIND_OPTIMAL_NPCS                                                                   [100%] 1 of 1 _  
[5a/958c0f] process > harmony_scenic:HARMONY:DIM_REDUCTION_PCA:SC__SCANPY__DIM_REDUCTION__PCA (1)                                                         [100%] 1 of 1 _  
[db/e4a13c] process > harmony_scenic:HARMONY:NEIGHBORHOOD_GRAPH:SC__SCANPY__NEIGHBORHOOD_GRAPH (1)                                                        [100%] 1 of 1 _  
[94/ad400d] process > harmony_scenic:HARMONY:DIM_REDUCTION_TSNE_UMAP:SC__SCANPY__DIM_REDUCTION__TSNE (1)                                                  [100%] 1 of 1 _  
[c6/bd8d50] process > harmony_scenic:HARMONY:DIM_REDUCTION_TSNE_UMAP:SC__SCANPY__DIM_REDUCTION__UMAP (1)                                                  [100%] 1 of 1 _  
[89/e184d3] process > harmony_scenic:HARMONY:DIM_REDUCTION_TSNE_UMAP:GENERATE_REPORT:SC__SCANPY__GENERATE_REPORT (1)                                      [100%] 1 of 1 _  
[38/779ac1] process > harmony_scenic:HARMONY:DIM_REDUCTION_TSNE_UMAP:GENERATE_REPORT:SC__SCANPY__REPORT_TO_HTML (1)                                       [100%] 1 of 1 _  
[11/3d4fe0] process > harmony_scenic:HARMONY:CLUSTER_IDENTIFICATION:SC__SCANPY__PARAM_EXPLORE_CLUSTERING (20)                                             [100%] 20 of 20 _
[08/14db46] process > harmony_scenic:HARMONY:CLUSTER_IDENTIFICATION:GENERATE_REPORT:SC__SCANPY__PARAM_EXPLORE_CLUSTERING_GENERATE_REPORT (20)             [100%] 20 of 20 _
[d0/82ca38] process > harmony_scenic:HARMONY:CLUSTER_IDENTIFICATION:GENERATE_REPORT:SC__SCANPY__REPORT_TO_HTML (20)                                       [100%] 20 of 20 _
[53/a5348e] process > harmony_scenic:HARMONY:CLUSTER_IDENTIFICATION:SC__SCANPY__PARAM_EXPLORE_MARKER_GENES (20)                                           [100%] 20 of 20 _
[f6/4a35fa] process > harmony_scenic:HARMONY:BEC_HARMONY:SC__HARMONY__HARMONY_MATRIX (1)                                                                  [100%] 1 of 1 _  
[57/18ad40] process > harmony_scenic:HARMONY:BEC_HARMONY:SC__H5AD_UPDATE_X_PCA (1)                                                                        [100%] 1 of 1 _  
[14/4b5e08] process > harmony_scenic:HARMONY:BEC_HARMONY:PUBLISH_BEC_OUTPUT:COMPRESS_HDF5 (1)                                                             [100%] 1 of 1 _  
[39/602e4f] process > harmony_scenic:HARMONY:BEC_HARMONY:PUBLISH_BEC_OUTPUT:SC__PUBLISH (1)                                                               [100%] 1 of 1 _  
[2d/337380] process > harmony_scenic:HARMONY:BEC_HARMONY:PUBLISH_BEC_OUTPUT:SC__PUBLISH_PROXY (1)                                                         [100%] 1 of 1 _  
[b6/dd5fde] process > harmony_scenic:HARMONY:BEC_HARMONY:NEIGHBORHOOD_GRAPH:SC__SCANPY__NEIGHBORHOOD_GRAPH (1)                                            [100%] 1 of 1 _  
[3f/3ec657] process > harmony_scenic:HARMONY:BEC_HARMONY:DIM_REDUCTION_TSNE_UMAP:SC__SCANPY__DIM_REDUCTION__TSNE (1)                                      [100%] 1 of 1 _  
[14/d16743] process > harmony_scenic:HARMONY:BEC_HARMONY:DIM_REDUCTION_TSNE_UMAP:SC__SCANPY__DIM_REDUCTION__UMAP (1)                                      [100%] 1 of 1 _  
[b6/705df2] process > harmony_scenic:HARMONY:BEC_HARMONY:DIM_REDUCTION_TSNE_UMAP:GENERATE_REPORT:SC__SCANPY__GENERATE_REPORT (1)                          [100%] 1 of 1 _  
[cb/f64e83] process > harmony_scenic:HARMONY:BEC_HARMONY:DIM_REDUCTION_TSNE_UMAP:GENERATE_REPORT:SC__SCANPY__REPORT_TO_HTML (1)                           [100%] 1 of 1 _  
[d9/185b8f] process > harmony_scenic:HARMONY:BEC_HARMONY:PUBLISH_BEC_DIMRED_OUTPUT:COMPRESS_HDF5 (1)                                                      [100%] 1 of 1 _  
[e1/f6ce13] process > harmony_scenic:HARMONY:BEC_HARMONY:PUBLISH_BEC_DIMRED_OUTPUT:SC__PUBLISH (1)                                                        [100%] 1 of 1 _  
[f3/b814ec] process > harmony_scenic:HARMONY:BEC_HARMONY:PUBLISH_BEC_DIMRED_OUTPUT:SC__PUBLISH_PROXY (1)                                                  [100%] 1 of 1 _  
[97/973004] process > harmony_scenic:HARMONY:BEC_HARMONY:CLUSTER_IDENTIFICATION:SC__SCANPY__PARAM_EXPLORE_CLUSTERING (20)                                 [100%] 20 of 20 _
[41/b74412] process > harmony_scenic:HARMONY:BEC_HARMONY:CLUSTER_IDENTIFICATION:GENERATE_REPORT:SC__SCANPY__PARAM_EXPLORE_CLUSTERING_GENERATE_REPORT (20) [100%] 20 of 20 _
[16/82ce8c] process > harmony_scenic:HARMONY:BEC_HARMONY:CLUSTER_IDENTIFICATION:GENERATE_REPORT:SC__SCANPY__REPORT_TO_HTML (20)                           [100%] 20 of 20 _
[71/cfc779] process > harmony_scenic:HARMONY:BEC_HARMONY:CLUSTER_IDENTIFICATION:SC__SCANPY__PARAM_EXPLORE_MARKER_GENES (20)                               [100%] 20 of 20 _
[f6/d55e59] process > harmony_scenic:HARMONY:BEC_HARMONY:PUBLISH_FINAL_HARMONY_OUTPUT:SC__PUBLISH_PROXY (20)                                              [100%] 20 of 20 _
[14/1e8ada] process > harmony_scenic:HARMONY:BEC_HARMONY:GENERATE_DUAL_INPUT_REPORT:SC__SCANPY__GENERATE_DUAL_INPUT_REPORT (20)                           [100%] 20 of 20 _
[22/ad399a] process > harmony_scenic:HARMONY:BEC_HARMONY:GENERATE_DUAL_INPUT_REPORT:SC__SCANPY__REPORT_TO_HTML (20)                                       [100%] 20 of 20 _
[ac/dbffe4] process > harmony_scenic:HARMONY:FINALIZE:SC__H5AD_TO_FILTERED_LOOM                                                                           [100%] 1 of 1 _
[37/b78c00] process > harmony_scenic:HARMONY:FINALIZE:FILE_CONVERTER_TO_SCOPE:SC__H5AD_TO_LOOM (1)                                                        [100%] 1 of 1 _
[75/419e6d] process > harmony_scenic:HARMONY:FINALIZE:FILE_CONVERTER_TO_SCANPY:SC__H5AD_MERGE (1)                                                         [100%] 1 of 1 _
[3b/ba34d5] process > harmony_scenic:HARMONY:SC__DIRECTS__SELECT_DEFAULT_CLUSTERING (1)                                                                   [100%] 1 of 1 _
[f3/7235b3] process > harmony_scenic:HARMONY:UTILS__GENERATE_WORKFLOW_CONFIG_REPORT                                                                       [100%] 1 of 1 _
[65/63015f] process > harmony_scenic:HARMONY:SC__SCANPY__MERGE_REPORTS (20)                                                                               [100%] 20 of 20 _
[91/7a6ce1] process > harmony_scenic:HARMONY:SC__SCANPY__REPORT_TO_HTML (20)                                                                              [100%] 20 of 20 _
[ea/815a60] process > harmony_scenic:PUBLISH_HARMONY:COMPRESS_HDF5 (1)                                                                                    [100%] 1 of 1 _
[0b/e68c31] process > harmony_scenic:PUBLISH_HARMONY:SC__PUBLISH (1)                                                                                      [100%] 1 of 1 _
[0a/e4c4fe] process > harmony_scenic:PUBLISH_HARMONY:SC__PUBLISH_PROXY (1)                                                                                [100%] 1 of 1 _
[f9/44c928] process > harmony_scenic:SCENIC_APPEND:scenic:ARBORETO_WITH_MULTIPROCESSING (1)                                                               [100%] 1 of 1 _
[66/4c6fa4] process > harmony_scenic:SCENIC_APPEND:scenic:CISTARGET__MOTIF (1)                                                                            [100%] 1 of 1 _
[65/517e50] process > harmony_scenic:SCENIC_APPEND:scenic:CISTARGET__TRACK (1)                                                                            [100%] 1 of 1 _
[90/92e404] process > harmony_scenic:SCENIC_APPEND:scenic:AUCELL__MOTIF (1)                                                                               [100%] 1 of 1 _
[5d/06a328] process > harmony_scenic:SCENIC_APPEND:scenic:AUCELL__TRACK (1)                                                                               [100%] 1 of 1 _
[90/3139d9] process > harmony_scenic:SCENIC_APPEND:scenic:MERGE_MOTIF_TRACK_LOOMS (1)                                                                     [100%] 1 of 1 _
[51/4ab41d] process > harmony_scenic:SCENIC_APPEND:scenic:VISUALIZE (1)                                                                                   [100%] 1 of 1 _
[9d/06bb19] process > harmony_scenic:SCENIC_APPEND:scenic:PUBLISH_LOOM (1)                                                                                [100%] 1 of 1 _
[9a/d7dbee] process > harmony_scenic:SCENIC_APPEND:APPEND_SCENIC_LOOM (1)                                                                                 [100%] 1 of 1 _
[a0/8f34bb] process > harmony_scenic:PUBLISH_HARMONY_SCENIC:COMPRESS_HDF5 (1)                                                                             [100%] 1 of 1 _
[de/91cf27] process > harmony_scenic:PUBLISH_HARMONY_SCENIC:SC__PUBLISH (1)                                                                               [100%] 1 of 1 _
[9c/4aa4c5] process > harmony_scenic:PUBLISH_HARMONY_SCENIC:SC__PUBLISH_PROXY (1)                                                                         [100%] 1 of 1 _
WARN: To render the execution DAG in the required format it is required to install Graphviz -- See http://www.graphviz.org for more info.
Completed at: 02-Nov-2020 12:48:17
Duration    : 17h 17m 25s
CPU hours   : 369.1
Succeeded   : 406
```
