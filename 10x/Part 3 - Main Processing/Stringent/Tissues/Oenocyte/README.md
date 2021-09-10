# Data

Total number of cells: 14410, genes: 14644.

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
nextflow -C nextflow.config run vib-singlecell-nf/vsn-pipelines -entry harmony_scenic
```

# Output

```
executor >  local (239), pbs (1)                                                                                                                                                                                                                                                    
[8c/47e74b] process > harmony_scenic:HARMONY:SC__FILE_CONVERTER (2)                                            [100%] 2 of 2 _                                                                                                                                                      
[37/a98380] process > harmony_scenic:HARMONY:FILTER_AND_ANNOTATE_AND_CLEAN:SC__ANNOTATE_BY_SAMPLE_METADATA (2) [100%] 2 of 2 _                                                                                                                                                      
[ba/2dd086] process > harmony_scenic:HARMONY:QC_FILTER:SC__SCANPY__COMPUTE_QC_STATS (2)                        [100%] 2 of 2 _                                                                                                                                                      
[aa/f15796] process > harmony_scenic:HARMONY:QC_FILTER:SC__SCANPY__CELL_FILTER (2)                             [100%] 2 of 2 _                                                                                                                                                      
[77/ff5a1c] process > harmony_scenic:HARMONY:QC_FILTER:SC__SCANPY__GENE_FILTER (2)                             [100%] 2 of 2 _                                                                                                                                                      
[4b/7145d0] process > harmony_scenic:HARMONY:QC_FILTER:GENERATE_DUAL_INPUT_REPORT:SC__SCANPY__GENERATE_DUAL... [100%] 2 of 2 _                                                                                                                                                      
[0c/bb66bb] process > harmony_scenic:HARMONY:QC_FILTER:GENERATE_DUAL_INPUT_REPORT:SC__SCANPY__REPORT_TO_HTM... [100%] 2 of 2 _                                                                                                                                                      
[0a/66f72e] process > harmony_scenic:HARMONY:SC__FILE_CONCATENATOR                                             [100%] 1 of 1 _                                                                                                                                                      
[ea/d25626] process > harmony_scenic:HARMONY:NORMALIZE_TRANSFORM:SC__SCANPY__NORMALIZATION                     [100%] 1 of 1 _                                                                                                                                                      
[a3/576b6d] process > harmony_scenic:HARMONY:NORMALIZE_TRANSFORM:PUBLISH_H5AD_NORMALIZED:COMPRESS_HDF5         [100%] 1 of 1 _                                                                                                                                                      
[3d/acec69] process > harmony_scenic:HARMONY:NORMALIZE_TRANSFORM:PUBLISH_H5AD_NORMALIZED:SC__PUBLISH           [100%] 1 of 1 _                                                                                                                                                      
[f9/15a2e5] process > harmony_scenic:HARMONY:NORMALIZE_TRANSFORM:PUBLISH_H5AD_NORMALIZED:SC__PUBLISH_PROXY     [100%] 1 of 1 _                                                                                                                                                      
[25/787129] process > harmony_scenic:HARMONY:NORMALIZE_TRANSFORM:SC__SCANPY__DATA_TRANSFORMATION               [100%] 1 of 1 _                                                                                                                                                      
[ea/0d3fcb] process > harmony_scenic:HARMONY:HVG_SELECTION:SC__SCANPY__FIND_HIGHLY_VARIABLE_GENES              [100%] 1 of 1 _                                                                                                                                                      
[99/c0c6cb] process > harmony_scenic:HARMONY:HVG_SELECTION:SC__SCANPY__SUBSET_HIGHLY_VARIABLE_GENES            [100%] 1 of 1 _                                                                                                                                                      
[3e/d84a7a] process > harmony_scenic:HARMONY:HVG_SELECTION:SC__SCANPY__REGRESS_OUT                             [100%] 1 of 1 _                                                                                                                                                      
[91/67eb60] process > harmony_scenic:HARMONY:HVG_SELECTION:SC__SCANPY__FEATURE_SCALING                         [100%] 1 of 1 _
[61/4080bf] process > harmony_scenic:HARMONY:HVG_SELECTION:PUBLISH_H5AD_HVG_SCALED:COMPRESS_HDF5               [100%] 1 of 1 _
[6c/5da1ab] process > harmony_scenic:HARMONY:HVG_SELECTION:PUBLISH_H5AD_HVG_SCALED:SC__PUBLISH                 [100%] 1 of 1 _
[31/3982ef] process > harmony_scenic:HARMONY:HVG_SELECTION:PUBLISH_H5AD_HVG_SCALED:SC__PUBLISH_PROXY           [100%] 1 of 1 _
[7c/6affac] process > harmony_scenic:HARMONY:HVG_SELECTION:GENERATE_REPORT:SC__SCANPY__GENERATE_REPORT         [100%] 1 of 1 _
[2f/442602] process > harmony_scenic:HARMONY:HVG_SELECTION:GENERATE_REPORT:SC__SCANPY__REPORT_TO_HTML          [100%] 1 of 1 _
[79/26c5a9] process > harmony_scenic:HARMONY:DIM_REDUCTION_PCA:PCACV__FIND_OPTIMAL_NPCS                        [100%] 1 of 1 _
[22/e01915] process > harmony_scenic:HARMONY:DIM_REDUCTION_PCA:SC__SCANPY__DIM_REDUCTION__PCA (1)              [100%] 1 of 1 _
[c1/3bf54b] process > harmony_scenic:HARMONY:NEIGHBORHOOD_GRAPH:SC__SCANPY__NEIGHBORHOOD_GRAPH (1)             [100%] 1 of 1 _
[47/7de02d] process > harmony_scenic:HARMONY:DIM_REDUCTION_TSNE_UMAP:SC__SCANPY__DIM_REDUCTION__TSNE (1)       [100%] 1 of 1 _
[df/18034c] process > harmony_scenic:HARMONY:DIM_REDUCTION_TSNE_UMAP:SC__SCANPY__DIM_REDUCTION__UMAP (1)       [100%] 1 of 1 _
[1f/60eb35] process > harmony_scenic:HARMONY:DIM_REDUCTION_TSNE_UMAP:GENERATE_REPORT:SC__SCANPY__GENERATE_R... [100%] 1 of 1 _
[84/fde197] process > harmony_scenic:HARMONY:DIM_REDUCTION_TSNE_UMAP:GENERATE_REPORT:SC__SCANPY__REPORT_TO_... [100%] 1 of 1 _
[70/06c780] process > harmony_scenic:HARMONY:CLUSTER_IDENTIFICATION:SC__SCANPY__PARAM_EXPLORE_CLUSTERING (12)  [100%] 13 of 13 _
[d6/15eb64] process > harmony_scenic:HARMONY:CLUSTER_IDENTIFICATION:GENERATE_REPORT:SC__SCANPY__PARAM_EXPLO... [100%] 13 of 13 _
[98/cfe796] process > harmony_scenic:HARMONY:CLUSTER_IDENTIFICATION:GENERATE_REPORT:SC__SCANPY__REPORT_TO_H... [100%] 13 of 13 _
[9e/490175] process > harmony_scenic:HARMONY:CLUSTER_IDENTIFICATION:SC__SCANPY__PARAM_EXPLORE_MARKER_GENES (7) [100%] 13 of 13 _
[bd/2537cf] process > harmony_scenic:HARMONY:BEC_HARMONY:SC__HARMONY__HARMONY_MATRIX (1)                       [100%] 1 of 1 _
[22/b8918b] process > harmony_scenic:HARMONY:BEC_HARMONY:SC__H5AD_UPDATE_X_PCA (1)                             [100%] 1 of 1 _
[05/bf3e9b] process > harmony_scenic:HARMONY:BEC_HARMONY:PUBLISH_BEC_OUTPUT:COMPRESS_HDF5 (1)                  [100%] 1 of 1 _
[a5/906139] process > harmony_scenic:HARMONY:BEC_HARMONY:PUBLISH_BEC_OUTPUT:SC__PUBLISH (1)                    [100%] 1 of 1 _
[c4/452707] process > harmony_scenic:HARMONY:BEC_HARMONY:PUBLISH_BEC_OUTPUT:SC__PUBLISH_PROXY (1)              [100%] 1 of 1 _
[2b/fd2731] process > harmony_scenic:HARMONY:BEC_HARMONY:NEIGHBORHOOD_GRAPH:SC__SCANPY__NEIGHBORHOOD_GRAPH (1) [100%] 1 of 1 _
[62/fc8d06] process > harmony_scenic:HARMONY:BEC_HARMONY:DIM_REDUCTION_TSNE_UMAP:SC__SCANPY__DIM_REDUCTION_... [100%] 1 of 1 _
[36/9bc4ea] process > harmony_scenic:HARMONY:BEC_HARMONY:DIM_REDUCTION_TSNE_UMAP:SC__SCANPY__DIM_REDUCTION_... [100%] 1 of 1 _
[62/4f7a63] process > harmony_scenic:HARMONY:BEC_HARMONY:DIM_REDUCTION_TSNE_UMAP:GENERATE_REPORT:SC__SCANPY... [100%] 1 of 1 _
[86/a95dba] process > harmony_scenic:HARMONY:BEC_HARMONY:DIM_REDUCTION_TSNE_UMAP:GENERATE_REPORT:SC__SCANPY... [100%] 1 of 1 _
[4c/e5cbd9] process > harmony_scenic:HARMONY:BEC_HARMONY:PUBLISH_BEC_DIMRED_OUTPUT:COMPRESS_HDF5 (1)           [100%] 1 of 1 _
[21/5e0765] process > harmony_scenic:HARMONY:BEC_HARMONY:PUBLISH_BEC_DIMRED_OUTPUT:SC__PUBLISH (1)             [100%] 1 of 1 _
[fc/ab344f] process > harmony_scenic:HARMONY:BEC_HARMONY:PUBLISH_BEC_DIMRED_OUTPUT:SC__PUBLISH_PROXY (1)       [100%] 1 of 1 _
[41/491d73] process > harmony_scenic:HARMONY:BEC_HARMONY:CLUSTER_IDENTIFICATION:SC__SCANPY__PARAM_EXPLORE_C... [100%] 13 of 13 _
[41/7b570c] process > harmony_scenic:HARMONY:BEC_HARMONY:CLUSTER_IDENTIFICATION:GENERATE_REPORT:SC__SCANPY_... [100%] 13 of 13 _
[37/89ef4b] process > harmony_scenic:HARMONY:BEC_HARMONY:CLUSTER_IDENTIFICATION:GENERATE_REPORT:SC__SCANPY_... [100%] 13 of 13 _
[72/b060a4] process > harmony_scenic:HARMONY:BEC_HARMONY:CLUSTER_IDENTIFICATION:SC__SCANPY__PARAM_EXPLORE_M... [100%] 13 of 13 _
[b9/c8eb5a] process > harmony_scenic:HARMONY:BEC_HARMONY:PUBLISH_FINAL_HARMONY_OUTPUT:SC__PUBLISH_PROXY (13)   [100%] 13 of 13 _
[27/96652d] process > harmony_scenic:HARMONY:BEC_HARMONY:GENERATE_DUAL_INPUT_REPORT:SC__SCANPY__GENERATE_DU... [100%] 13 of 13 _
[d1/a5d35e] process > harmony_scenic:HARMONY:BEC_HARMONY:GENERATE_DUAL_INPUT_REPORT:SC__SCANPY__REPORT_TO_H... [100%] 13 of 13 _
[15/d5cf33] process > harmony_scenic:HARMONY:FINALIZE:SC__H5AD_TO_FILTERED_LOOM                                [100%] 1 of 1 _
[32/58fd1d] process > harmony_scenic:HARMONY:FINALIZE:FILE_CONVERTER_TO_SCOPE:SC__H5AD_TO_LOOM (1)             [100%] 1 of 1 _
[3e/fd8df0] process > harmony_scenic:HARMONY:FINALIZE:FILE_CONVERTER_TO_SCANPY:SC__H5AD_MERGE (1)              [100%] 1 of 1 _
[eb/914d31] process > harmony_scenic:HARMONY:SC__DIRECTS__SELECT_DEFAULT_CLUSTERING (1)                        [100%] 1 of 1 _
[81/2d2573] process > harmony_scenic:HARMONY:UTILS__GENERATE_WORKFLOW_CONFIG_REPORT                            [100%] 1 of 1 _
[35/10d62e] process > harmony_scenic:HARMONY:SC__SCANPY__MERGE_REPORTS (13)                                    [100%] 13 of 13 _
[d2/4860cc] process > harmony_scenic:HARMONY:SC__SCANPY__REPORT_TO_HTML (13)                                   [100%] 13 of 13 _
[be/dd9235] process > harmony_scenic:PUBLISH_HARMONY:COMPRESS_HDF5 (1)                                         [100%] 1 of 1 _
[2e/4af607] process > harmony_scenic:PUBLISH_HARMONY:SC__PUBLISH (1)                                           [100%] 1 of 1 _
[71/b71820] process > harmony_scenic:PUBLISH_HARMONY:SC__PUBLISH_PROXY (1)                                     [100%] 1 of 1 _
[e0/a69877] process > harmony_scenic:SCENIC_APPEND:scenic:ARBORETO_WITH_MULTIPROCESSING (1)                    [100%] 1 of 1 _
[8f/8caf37] process > harmony_scenic:SCENIC_APPEND:scenic:CISTARGET__MOTIF (1)                                 [100%] 1 of 1 _
[6d/223d75] process > harmony_scenic:SCENIC_APPEND:scenic:CISTARGET__TRACK (1)                                 [100%] 1 of 1 _
[c8/5a0d3d] process > harmony_scenic:SCENIC_APPEND:scenic:AUCELL__MOTIF (1)                                    [100%] 1 of 1 _
[8b/13e9df] process > harmony_scenic:SCENIC_APPEND:scenic:AUCELL__TRACK (1)                                    [100%] 1 of 1 _
[29/378acb] process > harmony_scenic:SCENIC_APPEND:scenic:MERGE_MOTIF_TRACK_LOOMS (1)                          [100%] 1 of 1 _
[29/378acb] process > harmony_scenic:SCENIC_APPEND:scenic:MERGE_MOTIF_TRACK_LOOMS (1)                          [100%] 1 of 1 _
[2d/65817a] process > harmony_scenic:SCENIC_APPEND:scenic:VISUALIZE (1)                                        [100%] 1 of 1 _
[2d/6f867c] process > harmony_scenic:SCENIC_APPEND:scenic:PUBLISH_LOOM (1)                                     [100%] 1 of 1 _
[3f/f75a87] process > harmony_scenic:SCENIC_APPEND:APPEND_SCENIC_LOOM (1)                                      [100%] 1 of 1 _
[53/abddfb] process > harmony_scenic:SCENIC_APPEND:GENERATE_REPORT (1)                                         [100%] 1 of 1 _
[ba/98952e] process > harmony_scenic:SCENIC_APPEND:REPORT_TO_HTML (1)                                          [100%] 1 of 1 _
[b7/489fe8] process > harmony_scenic:PUBLISH_HARMONY_SCENIC:COMPRESS_HDF5 (1)                                  [100%] 1 of 1 _
[72/277383] process > harmony_scenic:PUBLISH_HARMONY_SCENIC:SC__PUBLISH (1)                                    [100%] 1 of 1 _
[95/c81307] process > harmony_scenic:PUBLISH_HARMONY_SCENIC:SC__PUBLISH_PROXY (1)                              [100%] 1 of 1 _
WARN: To render the execution DAG in the required format it is required to install Graphviz -- See http://www.graphviz.org for more info.
Duration    : 3h 48m 30s
CPU hours   : 53.2
Succeeded   : 240
```
