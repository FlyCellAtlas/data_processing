# Data

Total number of cells: 96926, genes: 15267.

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
executor >  local (405), pbs (1)                                                                                                                                                                                                                                                    
[2a/31b45d] process > harmony_scenic:HARMONY:SC__FILE_CONVERTER (7)                                            [100%] 13 of 13 _                                                                                                                                                    
[44/3399b1] process > harmony_scenic:HARMONY:FILTER_AND_ANNOTATE_AND_CLEAN:SC__ANNOTATE_BY_SAMPLE_METADATA ... [100%] 13 of 13 _                                                                                                                                                    
[9b/7826e2] process > harmony_scenic:HARMONY:QC_FILTER:SC__SCANPY__COMPUTE_QC_STATS (13)                       [100%] 13 of 13 _                                                                                                                                                    
[40/3d7064] process > harmony_scenic:HARMONY:QC_FILTER:SC__SCANPY__CELL_FILTER (12)                            [100%] 13 of 13 _                                                                                                                                                    
[08/608372] process > harmony_scenic:HARMONY:QC_FILTER:SC__SCANPY__GENE_FILTER (13)                            [100%] 13 of 13 _                                                                                                                                                    
[74/662331] process > harmony_scenic:HARMONY:QC_FILTER:GENERATE_DUAL_INPUT_REPORT:SC__SCANPY__GENERATE_DUAL... [100%] 13 of 13 _                                                                                                                                                    
[ee/1cfcd0] process > harmony_scenic:HARMONY:QC_FILTER:GENERATE_DUAL_INPUT_REPORT:SC__SCANPY__REPORT_TO_HTM... [100%] 13 of 13 _                                                                                                                                                    
[34/c5d6c4] process > harmony_scenic:HARMONY:SC__FILE_CONCATENATOR                                             [100%] 1 of 1 _                                                                                                                                                      
[7d/00373f] process > harmony_scenic:HARMONY:NORMALIZE_TRANSFORM:SC__SCANPY__NORMALIZATION                     [100%] 1 of 1 _                                                                                                                                                      
[9a/5e8574] process > harmony_scenic:HARMONY:NORMALIZE_TRANSFORM:PUBLISH_H5AD_NORMALIZED:COMPRESS_HDF5         [100%] 1 of 1 _                                                                                                                                                      
[f8/aff1c8] process > harmony_scenic:HARMONY:NORMALIZE_TRANSFORM:PUBLISH_H5AD_NORMALIZED:SC__PUBLISH           [100%] 1 of 1 _                                                                                                                                                      
[59/369bcd] process > harmony_scenic:HARMONY:NORMALIZE_TRANSFORM:PUBLISH_H5AD_NORMALIZED:SC__PUBLISH_PROXY     [100%] 1 of 1 _                                                                                                                                                      
[1c/c054db] process > harmony_scenic:HARMONY:NORMALIZE_TRANSFORM:SC__SCANPY__DATA_TRANSFORMATION               [100%] 1 of 1 _                                                                                                                                                      
[a0/a308a1] process > harmony_scenic:HARMONY:HVG_SELECTION:SC__SCANPY__FIND_HIGHLY_VARIABLE_GENES              [100%] 1 of 1 _                                                                                                                                                      
[c6/3ee2db] process > harmony_scenic:HARMONY:HVG_SELECTION:SC__SCANPY__SUBSET_HIGHLY_VARIABLE_GENES            [100%] 1 of 1 _
[22/4c4c38] process > harmony_scenic:HARMONY:HVG_SELECTION:SC__SCANPY__REGRESS_OUT                             [100%] 1 of 1 _
[64/df886d] process > harmony_scenic:HARMONY:HVG_SELECTION:SC__SCANPY__FEATURE_SCALING                         [100%] 1 of 1 _
[66/8c05d8] process > harmony_scenic:HARMONY:HVG_SELECTION:PUBLISH_H5AD_HVG_SCALED:COMPRESS_HDF5               [100%] 1 of 1 _
[cb/26ceab] process > harmony_scenic:HARMONY:HVG_SELECTION:PUBLISH_H5AD_HVG_SCALED:SC__PUBLISH                 [100%] 1 of 1 _
[89/07103b] process > harmony_scenic:HARMONY:HVG_SELECTION:PUBLISH_H5AD_HVG_SCALED:SC__PUBLISH_PROXY           [100%] 1 of 1 _
[95/1f854d] process > harmony_scenic:HARMONY:HVG_SELECTION:GENERATE_REPORT:SC__SCANPY__GENERATE_REPORT         [100%] 1 of 1 _
[5c/058993] process > harmony_scenic:HARMONY:HVG_SELECTION:GENERATE_REPORT:SC__SCANPY__REPORT_TO_HTML          [100%] 1 of 1 _
[6b/53a061] process > harmony_scenic:HARMONY:DIM_REDUCTION_PCA:PCACV__FIND_OPTIMAL_NPCS                        [100%] 1 of 1 _
[f5/012ea8] process > harmony_scenic:HARMONY:DIM_REDUCTION_PCA:SC__SCANPY__DIM_REDUCTION__PCA (1)              [100%] 1 of 1 _
[ae/6a883d] process > harmony_scenic:HARMONY:NEIGHBORHOOD_GRAPH:SC__SCANPY__NEIGHBORHOOD_GRAPH (1)             [100%] 1 of 1 _
[e0/4df53f] process > harmony_scenic:HARMONY:DIM_REDUCTION_TSNE_UMAP:SC__SCANPY__DIM_REDUCTION__TSNE (1)       [100%] 1 of 1 _
[d7/a950f6] process > harmony_scenic:HARMONY:DIM_REDUCTION_TSNE_UMAP:SC__SCANPY__DIM_REDUCTION__UMAP (1)       [100%] 1 of 1 _
[c3/a95cef] process > harmony_scenic:HARMONY:DIM_REDUCTION_TSNE_UMAP:GENERATE_REPORT:SC__SCANPY__GENERATE_R... [100%] 1 of 1 _
[4c/65f661] process > harmony_scenic:HARMONY:DIM_REDUCTION_TSNE_UMAP:GENERATE_REPORT:SC__SCANPY__REPORT_TO_... [100%] 1 of 1 _
[ee/354dcd] process > harmony_scenic:HARMONY:CLUSTER_IDENTIFICATION:SC__SCANPY__PARAM_EXPLORE_CLUSTERING (20)  [100%] 20 of 20 _
[f7/617971] process > harmony_scenic:HARMONY:CLUSTER_IDENTIFICATION:GENERATE_REPORT:SC__SCANPY__PARAM_EXPLO... [100%] 20 of 20 _
[c2/8af16e] process > harmony_scenic:HARMONY:CLUSTER_IDENTIFICATION:GENERATE_REPORT:SC__SCANPY__REPORT_TO_H... [100%] 20 of 20 _
[23/78a109] process > harmony_scenic:HARMONY:CLUSTER_IDENTIFICATION:SC__SCANPY__PARAM_EXPLORE_MARKER_GENES ... [100%] 20 of 20 _
[c6/132552] process > harmony_scenic:HARMONY:BEC_HARMONY:SC__HARMONY__HARMONY_MATRIX (1)                       [100%] 1 of 1 _
[27/5e9e92] process > harmony_scenic:HARMONY:BEC_HARMONY:SC__H5AD_UPDATE_X_PCA (1)                             [100%] 1 of 1 _
[f0/81bab5] process > harmony_scenic:HARMONY:BEC_HARMONY:PUBLISH_BEC_OUTPUT:COMPRESS_HDF5 (1)                  [100%] 1 of 1 _
[e1/cc71cf] process > harmony_scenic:HARMONY:BEC_HARMONY:PUBLISH_BEC_OUTPUT:SC__PUBLISH (1)                    [100%] 1 of 1 _
[31/848606] process > harmony_scenic:HARMONY:BEC_HARMONY:PUBLISH_BEC_OUTPUT:SC__PUBLISH_PROXY (1)              [100%] 1 of 1 _
[0e/5310ec] process > harmony_scenic:HARMONY:BEC_HARMONY:NEIGHBORHOOD_GRAPH:SC__SCANPY__NEIGHBORHOOD_GRAPH (1) [100%] 1 of 1 _
[17/5b7c88] process > harmony_scenic:HARMONY:BEC_HARMONY:DIM_REDUCTION_TSNE_UMAP:SC__SCANPY__DIM_REDUCTION_... [100%] 1 of 1 _
[c6/d704d3] process > harmony_scenic:HARMONY:BEC_HARMONY:DIM_REDUCTION_TSNE_UMAP:SC__SCANPY__DIM_REDUCTION_... [100%] 1 of 1 _
[6b/e30115] process > harmony_scenic:HARMONY:BEC_HARMONY:DIM_REDUCTION_TSNE_UMAP:GENERATE_REPORT:SC__SCANPY... [100%] 1 of 1 _
[73/5b5eb8] process > harmony_scenic:HARMONY:BEC_HARMONY:DIM_REDUCTION_TSNE_UMAP:GENERATE_REPORT:SC__SCANPY... [100%] 1 of 1 _
[c3/51eaa5] process > harmony_scenic:HARMONY:BEC_HARMONY:PUBLISH_BEC_DIMRED_OUTPUT:COMPRESS_HDF5 (1)           [100%] 1 of 1 _
[a6/a5232a] process > harmony_scenic:HARMONY:BEC_HARMONY:PUBLISH_BEC_DIMRED_OUTPUT:SC__PUBLISH (1)             [100%] 1 of 1 _
[2f/29dc2a] process > harmony_scenic:HARMONY:BEC_HARMONY:PUBLISH_BEC_DIMRED_OUTPUT:SC__PUBLISH_PROXY (1)       [100%] 1 of 1 _
[2e/348a1f] process > harmony_scenic:HARMONY:BEC_HARMONY:CLUSTER_IDENTIFICATION:SC__SCANPY__PARAM_EXPLORE_C... [100%] 20 of 20 _
[c6/fc3896] process > harmony_scenic:HARMONY:BEC_HARMONY:CLUSTER_IDENTIFICATION:GENERATE_REPORT:SC__SCANPY_... [100%] 20 of 20 _
[d2/b9d486] process > harmony_scenic:HARMONY:BEC_HARMONY:CLUSTER_IDENTIFICATION:GENERATE_REPORT:SC__SCANPY_... [100%] 20 of 20 _
[f4/e1dd29] process > harmony_scenic:HARMONY:BEC_HARMONY:CLUSTER_IDENTIFICATION:SC__SCANPY__PARAM_EXPLORE_M... [100%] 20 of 20 _
[2a/59c90c] process > harmony_scenic:HARMONY:BEC_HARMONY:PUBLISH_FINAL_HARMONY_OUTPUT:SC__PUBLISH_PROXY (20)   [100%] 20 of 20 _
[1b/8b4c2c] process > harmony_scenic:HARMONY:BEC_HARMONY:GENERATE_DUAL_INPUT_REPORT:SC__SCANPY__GENERATE_DU... [100%] 20 of 20 _
[83/a05cdb] process > harmony_scenic:HARMONY:BEC_HARMONY:GENERATE_DUAL_INPUT_REPORT:SC__SCANPY__REPORT_TO_H... [100%] 20 of 20 _
[51/6ede8c] process > harmony_scenic:HARMONY:FINALIZE:SC__H5AD_TO_FILTERED_LOOM                                [100%] 1 of 1 _
[bb/a0d102] process > harmony_scenic:HARMONY:FINALIZE:FILE_CONVERTER_TO_SCOPE:SC__H5AD_TO_LOOM (1)             [100%] 1 of 1 _
[5a/ed2399] process > harmony_scenic:HARMONY:FINALIZE:FILE_CONVERTER_TO_SCANPY:SC__H5AD_MERGE (1)              [100%] 1 of 1 _
[1c/6a0a99] process > harmony_scenic:HARMONY:SC__DIRECTS__SELECT_DEFAULT_CLUSTERING (1)                        [100%] 1 of 1 _
[85/f1e62c] process > harmony_scenic:HARMONY:UTILS__GENERATE_WORKFLOW_CONFIG_REPORT                            [100%] 1 of 1 _
[ce/9417a8] process > harmony_scenic:HARMONY:SC__SCANPY__MERGE_REPORTS (20)                                    [100%] 20 of 20 _
[5e/666d9d] process > harmony_scenic:HARMONY:SC__SCANPY__REPORT_TO_HTML (19)                                   [100%] 20 of 20 _
[fe/f37736] process > harmony_scenic:PUBLISH_HARMONY:COMPRESS_HDF5 (1)                                         [100%] 1 of 1 _
[5a/08102f] process > harmony_scenic:PUBLISH_HARMONY:SC__PUBLISH (1)                                           [100%] 1 of 1 _
[b9/47a9e7] process > harmony_scenic:PUBLISH_HARMONY:SC__PUBLISH_PROXY (1)                                     [100%] 1 of 1 _
[97/f46a74] process > harmony_scenic:SCENIC_APPEND:scenic:ARBORETO_WITH_MULTIPROCESSING (1)                    [100%] 1 of 1 _
[25/694aa9] process > harmony_scenic:SCENIC_APPEND:scenic:CISTARGET__MOTIF (1)                                 [100%] 1 of 1 _
[ed/f9368c] process > harmony_scenic:SCENIC_APPEND:scenic:CISTARGET__TRACK (1)                                 [100%] 1 of 1 _
[63/ab6ce0] process > harmony_scenic:SCENIC_APPEND:scenic:AUCELL__MOTIF (1)                                    [100%] 1 of 1 _
[42/5edee2] process > harmony_scenic:SCENIC_APPEND:scenic:AUCELL__TRACK (1)                                    [100%] 1 of 1 _
[40/a0a771] process > harmony_scenic:SCENIC_APPEND:scenic:MERGE_MOTIF_TRACK_LOOMS (1)                          [100%] 1 of 1 _
[36/adff8f] process > harmony_scenic:SCENIC_APPEND:scenic:VISUALIZE (1)                                        [100%] 1 of 1 _
[1c/176ed6] process > harmony_scenic:SCENIC_APPEND:scenic:PUBLISH_LOOM (1)                                     [100%] 1 of 1 _
[cd/e13250] process > harmony_scenic:SCENIC_APPEND:APPEND_SCENIC_LOOM (1)                                      [100%] 1 of 1 _
[fa/1db783] process > harmony_scenic:PUBLISH_HARMONY_SCENIC:COMPRESS_HDF5 (1)                                  [100%] 1 of 1 _
[e0/1cb741] process > harmony_scenic:PUBLISH_HARMONY_SCENIC:SC__PUBLISH (1)                                    [100%] 1 of 1 _
[af/98be9e] process > harmony_scenic:PUBLISH_HARMONY_SCENIC:SC__PUBLISH_PROXY (1)                              [100%] 1 of 1 _
WARN: To render the execution DAG in the required format it is required to install Graphviz -- See http://www.graphviz.org for more info.
Duration    : 20h 19m 8s
CPU hours   : 423.3
Succeeded   : 406
```
