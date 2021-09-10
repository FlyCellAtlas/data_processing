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
executor >  local (213), pbs (1)                                                                                                                                                                                                                                                    
[8c/df8107] process > harmony_scenic:HARMONY:SC__FILE_CONVERTER (1)                                                                                       [100%] 2 of 2 _                                                                                                           
[1a/404f20] process > harmony_scenic:HARMONY:FILTER_AND_ANNOTATE_AND_CLEAN:SC__ANNOTATE_BY_SAMPLE_METADATA (1)                                            [100%] 2 of 2 _                                                                                                           
[81/449285] process > harmony_scenic:HARMONY:QC_FILTER:SC__SCANPY__COMPUTE_QC_STATS (1)                                                                   [100%] 2 of 2 _                                                                                                           
[e2/af32df] process > harmony_scenic:HARMONY:QC_FILTER:SC__SCANPY__CELL_FILTER (1)                                                                        [100%] 2 of 2 _                                                                                                           
[aa/3ab79e] process > harmony_scenic:HARMONY:QC_FILTER:SC__SCANPY__GENE_FILTER (2)                                                                        [100%] 2 of 2 _                                                                                                           
[67/19a53c] process > harmony_scenic:HARMONY:QC_FILTER:GENERATE_DUAL_INPUT_REPORT:SC__SCANPY__GENERATE_DUAL_INPUT_REPORT (2)                              [100%] 2 of 2 _                                                                                                           
[5b/b3e395] process > harmony_scenic:HARMONY:QC_FILTER:GENERATE_DUAL_INPUT_REPORT:SC__SCANPY__REPORT_TO_HTML (2)                                          [100%] 2 of 2 _                                                                                                           
[d3/82f719] process > harmony_scenic:HARMONY:SC__FILE_CONCATENATOR                                                                                        [100%] 1 of 1 _                                                                                                           
[78/42fc72] process > harmony_scenic:HARMONY:NORMALIZE_TRANSFORM:SC__SCANPY__NORMALIZATION                                                                [100%] 1 of 1 _                                                                                                           
[00/311876] process > harmony_scenic:HARMONY:NORMALIZE_TRANSFORM:PUBLISH_H5AD_NORMALIZED:COMPRESS_HDF5                                                    [100%] 1 of 1 _                                                                                                           
[13/921531] process > harmony_scenic:HARMONY:NORMALIZE_TRANSFORM:PUBLISH_H5AD_NORMALIZED:SC__PUBLISH                                                      [100%] 1 of 1 _                                                                                                           
[1b/d28e4a] process > harmony_scenic:HARMONY:NORMALIZE_TRANSFORM:PUBLISH_H5AD_NORMALIZED:SC__PUBLISH_PROXY                                                [100%] 1 of 1 _                                                                                                           
[37/fd7360] process > harmony_scenic:HARMONY:NORMALIZE_TRANSFORM:SC__SCANPY__DATA_TRANSFORMATION                                                          [100%] 1 of 1 _                                                                                                           
[21/5e8ac1] process > harmony_scenic:HARMONY:HVG_SELECTION:SC__SCANPY__FIND_HIGHLY_VARIABLE_GENES                                                         [100%] 1 of 1 _                                                                                                           
[c6/6c3e84] process > harmony_scenic:HARMONY:HVG_SELECTION:SC__SCANPY__SUBSET_HIGHLY_VARIABLE_GENES                                                       [100%] 1 of 1 _                                                                                                           
[fb/5b10ea] process > harmony_scenic:HARMONY:HVG_SELECTION:SC__SCANPY__REGRESS_OUT                                                                        [100%] 1 of 1 _                                                                                                           
[6b/750ed8] process > harmony_scenic:HARMONY:HVG_SELECTION:SC__SCANPY__FEATURE_SCALING                                                                    [100%] 1 of 1 _                                                                                                           
[0b/050dbd] process > harmony_scenic:HARMONY:HVG_SELECTION:PUBLISH_H5AD_HVG_SCALED:COMPRESS_HDF5                                                          [100%] 1 of 1 _                                                                                                           
[60/5f8daf] process > harmony_scenic:HARMONY:HVG_SELECTION:PUBLISH_H5AD_HVG_SCALED:SC__PUBLISH                                                            [100%] 1 of 1 _  
[1e/aab854] process > harmony_scenic:HARMONY:HVG_SELECTION:PUBLISH_H5AD_HVG_SCALED:SC__PUBLISH_PROXY                                                      [100%] 1 of 1 _  
[78/cb1b73] process > harmony_scenic:HARMONY:HVG_SELECTION:GENERATE_REPORT:SC__SCANPY__GENERATE_REPORT                                                    [100%] 1 of 1 _  
[74/60ac7f] process > harmony_scenic:HARMONY:HVG_SELECTION:GENERATE_REPORT:SC__SCANPY__REPORT_TO_HTML                                                     [100%] 1 of 1 _  
[7e/ec1e3f] process > harmony_scenic:HARMONY:DIM_REDUCTION_PCA:PCACV__FIND_OPTIMAL_NPCS                                                                   [100%] 1 of 1 _
[df/84f1e0] process > harmony_scenic:HARMONY:DIM_REDUCTION_PCA:SC__SCANPY__DIM_REDUCTION__PCA (1)                                                         [100%] 1 of 1 _
[f7/dce065] process > harmony_scenic:HARMONY:NEIGHBORHOOD_GRAPH:SC__SCANPY__NEIGHBORHOOD_GRAPH (1)                                                        [100%] 1 of 1 _  
[a6/cd5384] process > harmony_scenic:HARMONY:DIM_REDUCTION_TSNE_UMAP:SC__SCANPY__DIM_REDUCTION__TSNE (1)                                                  [100%] 1 of 1 _  
[a7/f89480] process > harmony_scenic:HARMONY:DIM_REDUCTION_TSNE_UMAP:SC__SCANPY__DIM_REDUCTION__UMAP (1)                                                  [100%] 1 of 1 _  
[2f/cfee96] process > harmony_scenic:HARMONY:DIM_REDUCTION_TSNE_UMAP:GENERATE_REPORT:SC__SCANPY__GENERATE_REPORT (1)                                      [100%] 1 of 1 _  
[07/f6825b] process > harmony_scenic:HARMONY:DIM_REDUCTION_TSNE_UMAP:GENERATE_REPORT:SC__SCANPY__REPORT_TO_HTML (1)                                       [100%] 1 of 1 _  
[a9/ec1adf] process > harmony_scenic:HARMONY:CLUSTER_IDENTIFICATION:SC__SCANPY__PARAM_EXPLORE_CLUSTERING (10)                                             [100%] 11 of 11 _
[c0/66110a] process > harmony_scenic:HARMONY:CLUSTER_IDENTIFICATION:GENERATE_REPORT:SC__SCANPY__PARAM_EXPLORE_CLUSTERING_GENERATE_REPORT (11)             [100%] 11 of 11 _
[94/dc6d1e] process > harmony_scenic:HARMONY:CLUSTER_IDENTIFICATION:GENERATE_REPORT:SC__SCANPY__REPORT_TO_HTML (11)                                       [100%] 11 of 11 _
[13/2bb51f] process > harmony_scenic:HARMONY:CLUSTER_IDENTIFICATION:SC__SCANPY__PARAM_EXPLORE_MARKER_GENES (11)                                           [100%] 11 of 11 _
[34/1bb356] process > harmony_scenic:HARMONY:BEC_HARMONY:SC__HARMONY__HARMONY_MATRIX (1)                                                                  [100%] 1 of 1 _
[71/65b1ae] process > harmony_scenic:HARMONY:BEC_HARMONY:SC__H5AD_UPDATE_X_PCA (1)                                                                        [100%] 1 of 1 _
[59/f87cc6] process > harmony_scenic:HARMONY:BEC_HARMONY:PUBLISH_BEC_OUTPUT:COMPRESS_HDF5 (1)                                                             [100%] 1 of 1 _  
[c8/7541c0] process > harmony_scenic:HARMONY:BEC_HARMONY:PUBLISH_BEC_OUTPUT:SC__PUBLISH (1)                                                               [100%] 1 of 1 _  
[79/fa636b] process > harmony_scenic:HARMONY:BEC_HARMONY:PUBLISH_BEC_OUTPUT:SC__PUBLISH_PROXY (1)                                                         [100%] 1 of 1 _  
[41/c9066c] process > harmony_scenic:HARMONY:BEC_HARMONY:NEIGHBORHOOD_GRAPH:SC__SCANPY__NEIGHBORHOOD_GRAPH (1)                                            [100%] 1 of 1 _  
[34/8e6ce3] process > harmony_scenic:HARMONY:BEC_HARMONY:DIM_REDUCTION_TSNE_UMAP:SC__SCANPY__DIM_REDUCTION__TSNE (1)                                      [100%] 1 of 1 _  
[ce/6b5c0b] process > harmony_scenic:HARMONY:BEC_HARMONY:DIM_REDUCTION_TSNE_UMAP:SC__SCANPY__DIM_REDUCTION__UMAP (1)                                      [100%] 1 of 1 _  
[6c/fe70b1] process > harmony_scenic:HARMONY:BEC_HARMONY:DIM_REDUCTION_TSNE_UMAP:GENERATE_REPORT:SC__SCANPY__GENERATE_REPORT (1)                          [100%] 1 of 1 _  
[05/7ac261] process > harmony_scenic:HARMONY:BEC_HARMONY:DIM_REDUCTION_TSNE_UMAP:GENERATE_REPORT:SC__SCANPY__REPORT_TO_HTML (1)                           [100%] 1 of 1 _
[f8/d646f7] process > harmony_scenic:HARMONY:BEC_HARMONY:PUBLISH_BEC_DIMRED_OUTPUT:COMPRESS_HDF5 (1)                                                      [100%] 1 of 1 _
[a7/47c966] process > harmony_scenic:HARMONY:BEC_HARMONY:PUBLISH_BEC_DIMRED_OUTPUT:SC__PUBLISH (1)                                                        [100%] 1 of 1 _
[4e/cdd49b] process > harmony_scenic:HARMONY:BEC_HARMONY:PUBLISH_BEC_DIMRED_OUTPUT:SC__PUBLISH_PROXY (1)                                                  [100%] 1 of 1 _
[ad/91c613] process > harmony_scenic:HARMONY:BEC_HARMONY:CLUSTER_IDENTIFICATION:SC__SCANPY__PARAM_EXPLORE_CLUSTERING (5)                                  [100%] 11 of 11 _
[3a/046ef7] process > harmony_scenic:HARMONY:BEC_HARMONY:CLUSTER_IDENTIFICATION:GENERATE_REPORT:SC__SCANPY__PARAM_EXPLORE_CLUSTERING_GENERATE_REPORT (11) [100%] 11 of 11 _
[07/95e1d4] process > harmony_scenic:HARMONY:BEC_HARMONY:CLUSTER_IDENTIFICATION:GENERATE_REPORT:SC__SCANPY__REPORT_TO_HTML (11)                           [100%] 11 of 11 _
[f6/afa71d] process > harmony_scenic:HARMONY:BEC_HARMONY:CLUSTER_IDENTIFICATION:SC__SCANPY__PARAM_EXPLORE_MARKER_GENES (11)                               [100%] 11 of 11 _
[0a/635fc0] process > harmony_scenic:HARMONY:BEC_HARMONY:PUBLISH_FINAL_HARMONY_OUTPUT:SC__PUBLISH_PROXY (11)                                              [100%] 11 of 11 _
[00/ae47d4] process > harmony_scenic:HARMONY:BEC_HARMONY:GENERATE_DUAL_INPUT_REPORT:SC__SCANPY__GENERATE_DUAL_INPUT_REPORT (11)                           [100%] 11 of 11 _
[1a/4d834c] process > harmony_scenic:HARMONY:BEC_HARMONY:GENERATE_DUAL_INPUT_REPORT:SC__SCANPY__REPORT_TO_HTML (11)                                       [100%] 11 of 11 _
[1f/1a1189] process > harmony_scenic:HARMONY:FINALIZE:SC__H5AD_TO_FILTERED_LOOM                                                                           [100%] 1 of 1 _
[7f/e2bb59] process > harmony_scenic:HARMONY:FINALIZE:FILE_CONVERTER_TO_SCOPE:SC__H5AD_TO_LOOM (1)                                                        [100%] 1 of 1 _
[cb/25a42e] process > harmony_scenic:HARMONY:FINALIZE:FILE_CONVERTER_TO_SCANPY:SC__H5AD_MERGE (1)                                                         [100%] 1 of 1 _
[15/52682c] process > harmony_scenic:HARMONY:SC__DIRECTS__SELECT_DEFAULT_CLUSTERING (1)                                                                   [100%] 1 of 1 _
[79/6e6d88] process > harmony_scenic:HARMONY:UTILS__GENERATE_WORKFLOW_CONFIG_REPORT                                                                       [100%] 1 of 1 _
[92/e2f790] process > harmony_scenic:HARMONY:SC__SCANPY__MERGE_REPORTS (11)                                                                               [100%] 11 of 11 _
[66/025c4e] process > harmony_scenic:HARMONY:SC__SCANPY__REPORT_TO_HTML (11)                                                                              [100%] 11 of 11 _
[58/73b44f] process > harmony_scenic:PUBLISH_HARMONY:COMPRESS_HDF5 (1)                                                                                    [100%] 1 of 1 _
[43/428666] process > harmony_scenic:PUBLISH_HARMONY:SC__PUBLISH (1)                                                                                      [100%] 1 of 1 _
[3c/f37a29] process > harmony_scenic:PUBLISH_HARMONY:SC__PUBLISH_PROXY (1)                                                                                [100%] 1 of 1 _
[53/0b5289] process > harmony_scenic:SCENIC_APPEND:scenic:ARBORETO_WITH_MULTIPROCESSING (1)                                                               [100%] 1 of 1 _
[95/10410b] process > harmony_scenic:SCENIC_APPEND:scenic:CISTARGET__MOTIF (1)                                                                            [100%] 1 of 1 _
[bf/e7f4dd] process > harmony_scenic:SCENIC_APPEND:scenic:CISTARGET__TRACK (1)                                                                            [100%] 1 of 1 _
[0c/a3e00b] process > harmony_scenic:SCENIC_APPEND:scenic:AUCELL__MOTIF (1)                                                                               [100%] 1 of 1 _
[7b/013552] process > harmony_scenic:SCENIC_APPEND:scenic:AUCELL__TRACK (1)                                                                               [100%] 1 of 1 _
[e7/1f2944] process > harmony_scenic:SCENIC_APPEND:scenic:MERGE_MOTIF_TRACK_LOOMS (1)                                                                     [100%] 1 of 1 _
[07/94010a] process > harmony_scenic:SCENIC_APPEND:scenic:VISUALIZE (1)                                                                                   [100%] 1 of 1 _
[bd/601ce1] process > harmony_scenic:SCENIC_APPEND:scenic:PUBLISH_LOOM (1)                                                                                [100%] 1 of 1 _
[67/b66b4d] process > harmony_scenic:SCENIC_APPEND:APPEND_SCENIC_LOOM (1)                                                                                 [100%] 1 of 1 _
[08/ba2b45] process > harmony_scenic:SCENIC_APPEND:GENERATE_REPORT (1)                                                                                    [100%] 1 of 1 _
[af/de9f0f] process > harmony_scenic:SCENIC_APPEND:REPORT_TO_HTML (1)                                                                                     [100%] 1 of 1 _
[06/0fe31e] process > harmony_scenic:PUBLISH_HARMONY_SCENIC:COMPRESS_HDF5 (1)                                                                             [100%] 1 of 1 _
[72/5990f1] process > harmony_scenic:PUBLISH_HARMONY_SCENIC:SC__PUBLISH (1)                                                                               [100%] 1 of 1 _
[64/b1c7d6] process > harmony_scenic:PUBLISH_HARMONY_SCENIC:SC__PUBLISH_PROXY (1)                                                                         [100%] 1 of 1 _
WARN: To render the execution DAG in the required format it is required to install Graphviz -- See http://www.graphviz.org for more info.
Duration    : 25m 32s
CPU hours   : 4.5
Succeeded   : 214
```
