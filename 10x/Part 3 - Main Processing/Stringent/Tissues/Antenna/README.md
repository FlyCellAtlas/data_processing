# Data

Total number of cells: 37254, genes: 13203.

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
executor >  local (260), pbs (1)                                                                                                                                                                                                                                                    
[34/cc5bff] process > harmony_scenic:HARMONY:SC__FILE_CONVERTER (1)                                            [100%] 5 of 5 _                                                                                                                                                      
[85/81cf24] process > harmony_scenic:HARMONY:FILTER_AND_ANNOTATE_AND_CLEAN:SC__ANNOTATE_BY_SAMPLE_METADATA (3) [100%] 5 of 5 _                                                                                                                                                      
[84/156430] process > harmony_scenic:HARMONY:QC_FILTER:SC__SCANPY__COMPUTE_QC_STATS (5)                        [100%] 5 of 5 _                                                                                                                                                      
[c3/3eb493] process > harmony_scenic:HARMONY:QC_FILTER:SC__SCANPY__CELL_FILTER (5)                             [100%] 5 of 5 _                                                                                                                                                      
[06/eb17a9] process > harmony_scenic:HARMONY:QC_FILTER:SC__SCANPY__GENE_FILTER (5)                             [100%] 5 of 5 _                                                                                                                                                      
[4d/0a2a37] process > harmony_scenic:HARMONY:QC_FILTER:GENERATE_DUAL_INPUT_REPORT:SC__SCANPY__GENERATE_DUAL... [100%] 5 of 5 _                                                                                                                                                      
[01/d50f38] process > harmony_scenic:HARMONY:QC_FILTER:GENERATE_DUAL_INPUT_REPORT:SC__SCANPY__REPORT_TO_HTM... [100%] 5 of 5 _                                                                                                                                                      
[91/d770ae] process > harmony_scenic:HARMONY:SC__FILE_CONCATENATOR                                             [100%] 1 of 1 _                                                                                                                                                      
[88/98cd7b] process > harmony_scenic:HARMONY:NORMALIZE_TRANSFORM:SC__SCANPY__NORMALIZATION                     [100%] 1 of 1 _                                                                                                                                                      
[fd/9c8cbf] process > harmony_scenic:HARMONY:NORMALIZE_TRANSFORM:PUBLISH_H5AD_NORMALIZED:COMPRESS_HDF5         [100%] 1 of 1 _                                                                                                                                                      
[24/b24cc3] process > harmony_scenic:HARMONY:NORMALIZE_TRANSFORM:PUBLISH_H5AD_NORMALIZED:SC__PUBLISH           [100%] 1 of 1 _                                                                                                                                                      
[1f/9e0bc1] process > harmony_scenic:HARMONY:NORMALIZE_TRANSFORM:PUBLISH_H5AD_NORMALIZED:SC__PUBLISH_PROXY     [100%] 1 of 1 _                                                                                                                                                      
[56/ca6f42] process > harmony_scenic:HARMONY:NORMALIZE_TRANSFORM:SC__SCANPY__DATA_TRANSFORMATION               [100%] 1 of 1 _                                                                                                                                                      
[f4/5c1bc3] process > harmony_scenic:HARMONY:HVG_SELECTION:SC__SCANPY__FIND_HIGHLY_VARIABLE_GENES              [100%] 1 of 1 _                                                                                                                                                      
[cc/baae1c] process > harmony_scenic:HARMONY:HVG_SELECTION:SC__SCANPY__SUBSET_HIGHLY_VARIABLE_GENES            [100%] 1 of 1 _                                                                                                                                                      
[ac/10aacc] process > harmony_scenic:HARMONY:HVG_SELECTION:SC__SCANPY__REGRESS_OUT                             [100%] 1 of 1 _                                                                                                                                                      
[bc/cce217] process > harmony_scenic:HARMONY:HVG_SELECTION:SC__SCANPY__FEATURE_SCALING                         [100%] 1 of 1 _                                                                                                                                                      
[92/d56fcf] process > harmony_scenic:HARMONY:HVG_SELECTION:PUBLISH_H5AD_HVG_SCALED:COMPRESS_HDF5               [100%] 1 of 1 _                                                                                                                                                      
[a8/9eeae6] process > harmony_scenic:HARMONY:HVG_SELECTION:PUBLISH_H5AD_HVG_SCALED:SC__PUBLISH                 [100%] 1 of 1 _                                                                                                                                                      
[37/8d014d] process > harmony_scenic:HARMONY:HVG_SELECTION:PUBLISH_H5AD_HVG_SCALED:SC__PUBLISH_PROXY           [100%] 1 of 1 _
[c4/1f9a0a] process > harmony_scenic:HARMONY:HVG_SELECTION:GENERATE_REPORT:SC__SCANPY__GENERATE_REPORT         [100%] 1 of 1 _
[a9/71ac37] process > harmony_scenic:HARMONY:HVG_SELECTION:GENERATE_REPORT:SC__SCANPY__REPORT_TO_HTML          [100%] 1 of 1 _
[b0/0ed8e8] process > harmony_scenic:HARMONY:DIM_REDUCTION_PCA:PCACV__FIND_OPTIMAL_NPCS                        [100%] 1 of 1 _
[c2/166876] process > harmony_scenic:HARMONY:DIM_REDUCTION_PCA:SC__SCANPY__DIM_REDUCTION__PCA (1)              [100%] 1 of 1 _
[94/e83958] process > harmony_scenic:HARMONY:NEIGHBORHOOD_GRAPH:SC__SCANPY__NEIGHBORHOOD_GRAPH (1)             [100%] 1 of 1 _
[25/865809] process > harmony_scenic:HARMONY:DIM_REDUCTION_TSNE_UMAP:SC__SCANPY__DIM_REDUCTION__TSNE (1)       [100%] 1 of 1 _
[38/5c55ff] process > harmony_scenic:HARMONY:DIM_REDUCTION_TSNE_UMAP:SC__SCANPY__DIM_REDUCTION__UMAP (1)       [100%] 1 of 1 _
[01/544365] process > harmony_scenic:HARMONY:DIM_REDUCTION_TSNE_UMAP:GENERATE_REPORT:SC__SCANPY__GENERATE_R... [100%] 1 of 1 _
[d4/bc03f8] process > harmony_scenic:HARMONY:DIM_REDUCTION_TSNE_UMAP:GENERATE_REPORT:SC__SCANPY__REPORT_TO_... [100%] 1 of 1 _
[a7/260b98] process > harmony_scenic:HARMONY:CLUSTER_IDENTIFICATION:SC__SCANPY__PARAM_EXPLORE_CLUSTERING (6)   [100%] 13 of 13 _
[74/a6e06b] process > harmony_scenic:HARMONY:CLUSTER_IDENTIFICATION:GENERATE_REPORT:SC__SCANPY__PARAM_EXPLO... [100%] 13 of 13 _
[f2/1c997d] process > harmony_scenic:HARMONY:CLUSTER_IDENTIFICATION:GENERATE_REPORT:SC__SCANPY__REPORT_TO_H... [100%] 13 of 13 _
[42/7cece7] process > harmony_scenic:HARMONY:CLUSTER_IDENTIFICATION:SC__SCANPY__PARAM_EXPLORE_MARKER_GENES ... [100%] 13 of 13 _
[84/f3b0aa] process > harmony_scenic:HARMONY:BEC_HARMONY:SC__HARMONY__HARMONY_MATRIX (1)                       [100%] 1 of 1 _
[ee/aa70a9] process > harmony_scenic:HARMONY:BEC_HARMONY:SC__H5AD_UPDATE_X_PCA (1)                             [100%] 1 of 1 _
[b7/33c2e9] process > harmony_scenic:HARMONY:BEC_HARMONY:PUBLISH_BEC_OUTPUT:COMPRESS_HDF5 (1)                  [100%] 1 of 1 _
[c7/bf9b66] process > harmony_scenic:HARMONY:BEC_HARMONY:PUBLISH_BEC_OUTPUT:SC__PUBLISH (1)                    [100%] 1 of 1 _
[e2/311787] process > harmony_scenic:HARMONY:BEC_HARMONY:PUBLISH_BEC_OUTPUT:SC__PUBLISH_PROXY (1)              [100%] 1 of 1 _
[aa/65806d] process > harmony_scenic:HARMONY:BEC_HARMONY:NEIGHBORHOOD_GRAPH:SC__SCANPY__NEIGHBORHOOD_GRAPH (1) [100%] 1 of 1 _
[af/482e44] process > harmony_scenic:HARMONY:BEC_HARMONY:DIM_REDUCTION_TSNE_UMAP:SC__SCANPY__DIM_REDUCTION_... [100%] 1 of 1 _
[9f/67afeb] process > harmony_scenic:HARMONY:BEC_HARMONY:DIM_REDUCTION_TSNE_UMAP:SC__SCANPY__DIM_REDUCTION_... [100%] 1 of 1 _
[06/9979d0] process > harmony_scenic:HARMONY:BEC_HARMONY:DIM_REDUCTION_TSNE_UMAP:GENERATE_REPORT:SC__SCANPY... [100%] 1 of 1 _
[62/bc9c1f] process > harmony_scenic:HARMONY:BEC_HARMONY:DIM_REDUCTION_TSNE_UMAP:GENERATE_REPORT:SC__SCANPY... [100%] 1 of 1 _
[6c/7bcdbc] process > harmony_scenic:HARMONY:BEC_HARMONY:PUBLISH_BEC_DIMRED_OUTPUT:COMPRESS_HDF5 (1)           [100%] 1 of 1 _
[12/ffdd38] process > harmony_scenic:HARMONY:BEC_HARMONY:PUBLISH_BEC_DIMRED_OUTPUT:SC__PUBLISH (1)             [100%] 1 of 1 _
[bc/2f605f] process > harmony_scenic:HARMONY:BEC_HARMONY:PUBLISH_BEC_DIMRED_OUTPUT:SC__PUBLISH_PROXY (1)       [100%] 1 of 1 _
[e2/fc6577] process > harmony_scenic:HARMONY:BEC_HARMONY:CLUSTER_IDENTIFICATION:SC__SCANPY__PARAM_EXPLORE_C... [100%] 13 of 13 _
[42/3a3d5f] process > harmony_scenic:HARMONY:BEC_HARMONY:CLUSTER_IDENTIFICATION:GENERATE_REPORT:SC__SCANPY_... [100%] 13 of 13 _
[13/1afe97] process > harmony_scenic:HARMONY:BEC_HARMONY:CLUSTER_IDENTIFICATION:GENERATE_REPORT:SC__SCANPY_... [100%] 13 of 13 _
[a9/b35602] process > harmony_scenic:HARMONY:BEC_HARMONY:CLUSTER_IDENTIFICATION:SC__SCANPY__PARAM_EXPLORE_M... [100%] 13 of 13 _
[68/f310d1] process > harmony_scenic:HARMONY:BEC_HARMONY:PUBLISH_FINAL_HARMONY_OUTPUT:SC__PUBLISH_PROXY (13)   [100%] 13 of 13 _
[62/c568b9] process > harmony_scenic:HARMONY:BEC_HARMONY:GENERATE_DUAL_INPUT_REPORT:SC__SCANPY__GENERATE_DU... [100%] 13 of 13 _
[0d/7403e0] process > harmony_scenic:HARMONY:BEC_HARMONY:GENERATE_DUAL_INPUT_REPORT:SC__SCANPY__REPORT_TO_H... [100%] 13 of 13 _
[eb/7968e7] process > harmony_scenic:HARMONY:FINALIZE:SC__H5AD_TO_FILTERED_LOOM                                [100%] 1 of 1 _
[c8/56b61a] process > harmony_scenic:HARMONY:FINALIZE:FILE_CONVERTER_TO_SCOPE:SC__H5AD_TO_LOOM (1)             [100%] 1 of 1 _
[93/bb500e] process > harmony_scenic:HARMONY:FINALIZE:FILE_CONVERTER_TO_SCANPY:SC__H5AD_MERGE (1)              [100%] 1 of 1 _
[93/45acd9] process > harmony_scenic:HARMONY:SC__DIRECTS__SELECT_DEFAULT_CLUSTERING (1)                        [100%] 1 of 1 _
[46/d54367] process > harmony_scenic:HARMONY:UTILS__GENERATE_WORKFLOW_CONFIG_REPORT                            [100%] 1 of 1 _
[20/68824a] process > harmony_scenic:HARMONY:SC__SCANPY__MERGE_REPORTS (13)                                    [100%] 13 of 13 _
[18/7c1b65] process > harmony_scenic:HARMONY:SC__SCANPY__REPORT_TO_HTML (13)                                   [100%] 13 of 13 _
[91/82c2d3] process > harmony_scenic:PUBLISH_HARMONY:COMPRESS_HDF5 (1)                                         [100%] 1 of 1 _
[04/d30a8b] process > harmony_scenic:PUBLISH_HARMONY:SC__PUBLISH (1)                                           [100%] 1 of 1 _
[46/83aa13] process > harmony_scenic:PUBLISH_HARMONY:SC__PUBLISH_PROXY (1)                                     [100%] 1 of 1 _
[75/f72092] process > harmony_scenic:SCENIC_APPEND:scenic:ARBORETO_WITH_MULTIPROCESSING (1)                    [100%] 1 of 1 _
[12/a22468] process > harmony_scenic:SCENIC_APPEND:scenic:CISTARGET__MOTIF (1)                                 [100%] 1 of 1 _
[15/4d01d3] process > harmony_scenic:SCENIC_APPEND:scenic:CISTARGET__TRACK (1)                                 [100%] 1 of 1 _
[30/bfa746] process > harmony_scenic:SCENIC_APPEND:scenic:AUCELL__MOTIF (1)                                    [100%] 1 of 1 _
[ab/dd1ef3] process > harmony_scenic:SCENIC_APPEND:scenic:AUCELL__TRACK (1)                                    [100%] 1 of 1 _
[85/fec115] process > harmony_scenic:SCENIC_APPEND:scenic:MERGE_MOTIF_TRACK_LOOMS (1)                          [100%] 1 of 1 _
[1d/7cdac5] process > harmony_scenic:SCENIC_APPEND:scenic:VISUALIZE (1)                                        [100%] 1 of 1 _
[c3/40bf5c] process > harmony_scenic:SCENIC_APPEND:scenic:PUBLISH_LOOM (1)                                     [100%] 1 of 1 _
[ad/b8d267] process > harmony_scenic:SCENIC_APPEND:APPEND_SCENIC_LOOM (1)                                      [100%] 1 of 1 _
[ff/07f319] process > harmony_scenic:SCENIC_APPEND:GENERATE_REPORT (1)                                         [100%] 1 of 1 _
[6f/2a3c00] process > harmony_scenic:SCENIC_APPEND:REPORT_TO_HTML (1)                                          [100%] 1 of 1 _
[45/6f7827] process > harmony_scenic:PUBLISH_HARMONY_SCENIC:COMPRESS_HDF5 (1)                                  [100%] 1 of 1 _
[44/0e50df] process > harmony_scenic:PUBLISH_HARMONY_SCENIC:SC__PUBLISH (1)                                    [100%] 1 of 1 _
[5c/e394e2] process > harmony_scenic:PUBLISH_HARMONY_SCENIC:SC__PUBLISH_PROXY (1)                              [100%] 1 of 1 _
WARN: To render the execution DAG in the required format it is required to install Graphviz -- See http://www.graphviz.org for more info.
Duration    : 5h 58m 16s
CPU hours   : 97.1
Succeeded   : 261
```
