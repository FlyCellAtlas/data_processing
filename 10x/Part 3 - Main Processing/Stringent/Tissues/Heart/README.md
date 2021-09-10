# Data

Total number of cells: 10686, genes: 12674.

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
executor >  local (239), pbs (1)                                                                                                                                                                                                                                                    
[70/20634a] process > harmony_scenic:HARMONY:SC__FILE_CONVERTER (1)                                                                                       [100%] 2 of 2 _                                                                                                           
[cd/a11fd4] process > harmony_scenic:HARMONY:FILTER_AND_ANNOTATE_AND_CLEAN:SC__ANNOTATE_BY_SAMPLE_METADATA (2)                                            [100%] 2 of 2 _                                                                                                           
[ae/8ddd92] process > harmony_scenic:HARMONY:QC_FILTER:SC__SCANPY__COMPUTE_QC_STATS (1)                                                                   [100%] 2 of 2 _                                                                                                           
[cf/65f9e5] process > harmony_scenic:HARMONY:QC_FILTER:SC__SCANPY__CELL_FILTER (1)                                                                        [100%] 2 of 2 _                                                                                                           
[cf/db3e0a] process > harmony_scenic:HARMONY:QC_FILTER:SC__SCANPY__GENE_FILTER (2)                                                                        [100%] 2 of 2 _                                                                                                           
[23/da280c] process > harmony_scenic:HARMONY:QC_FILTER:GENERATE_DUAL_INPUT_REPORT:SC__SCANPY__GENERATE_DUAL_INPUT_REPORT (1)                              [100%] 2 of 2 _                                                                                                           
[b5/7458b4] process > harmony_scenic:HARMONY:QC_FILTER:GENERATE_DUAL_INPUT_REPORT:SC__SCANPY__REPORT_TO_HTML (2)                                          [100%] 2 of 2 _                                                                                                           
[81/bd6a9c] process > harmony_scenic:HARMONY:SC__FILE_CONCATENATOR                                                                                        [100%] 1 of 1 _                                                                                                           
[04/654f5f] process > harmony_scenic:HARMONY:NORMALIZE_TRANSFORM:SC__SCANPY__NORMALIZATION                                                                [100%] 1 of 1 _                                                                                                           
[b3/cf4ea1] process > harmony_scenic:HARMONY:NORMALIZE_TRANSFORM:PUBLISH_H5AD_NORMALIZED:COMPRESS_HDF5                                                    [100%] 1 of 1 _                                                                                                           
[4a/86521d] process > harmony_scenic:HARMONY:NORMALIZE_TRANSFORM:PUBLISH_H5AD_NORMALIZED:SC__PUBLISH                                                      [100%] 1 of 1 _                                                                                                           
[c7/8d5fca] process > harmony_scenic:HARMONY:NORMALIZE_TRANSFORM:PUBLISH_H5AD_NORMALIZED:SC__PUBLISH_PROXY                                                [100%] 1 of 1 _                                                                                                           
[af/8eef90] process > harmony_scenic:HARMONY:NORMALIZE_TRANSFORM:SC__SCANPY__DATA_TRANSFORMATION                                                          [100%] 1 of 1 _                                                                                                           
[c6/08a618] process > harmony_scenic:HARMONY:HVG_SELECTION:SC__SCANPY__FIND_HIGHLY_VARIABLE_GENES                                                         [100%] 1 of 1 _                                                                                                           
[0a/9c6fd4] process > harmony_scenic:HARMONY:HVG_SELECTION:SC__SCANPY__SUBSET_HIGHLY_VARIABLE_GENES                                                       [100%] 1 of 1 _                                                                                                           
[64/2eb00c] process > harmony_scenic:HARMONY:HVG_SELECTION:SC__SCANPY__REGRESS_OUT                                                                        [100%] 1 of 1 _                                                                                                           
[04/7f2efa] process > harmony_scenic:HARMONY:HVG_SELECTION:SC__SCANPY__FEATURE_SCALING                                                                    [100%] 1 of 1 _  
[9d/5d3c04] process > harmony_scenic:HARMONY:HVG_SELECTION:PUBLISH_H5AD_HVG_SCALED:COMPRESS_HDF5                                                          [100%] 1 of 1 _
[75/326dc4] process > harmony_scenic:HARMONY:HVG_SELECTION:PUBLISH_H5AD_HVG_SCALED:SC__PUBLISH                                                            [100%] 1 of 1 _
[fe/1b9a62] process > harmony_scenic:HARMONY:HVG_SELECTION:PUBLISH_H5AD_HVG_SCALED:SC__PUBLISH_PROXY                                                      [100%] 1 of 1 _  
[31/147212] process > harmony_scenic:HARMONY:HVG_SELECTION:GENERATE_REPORT:SC__SCANPY__GENERATE_REPORT                                                    [100%] 1 of 1 _  
[bc/75f64c] process > harmony_scenic:HARMONY:HVG_SELECTION:GENERATE_REPORT:SC__SCANPY__REPORT_TO_HTML                                                     [100%] 1 of 1 _  
[fe/eecd15] process > harmony_scenic:HARMONY:DIM_REDUCTION_PCA:PCACV__FIND_OPTIMAL_NPCS                                                                   [100%] 1 of 1 _  
[54/7cfa85] process > harmony_scenic:HARMONY:DIM_REDUCTION_PCA:SC__SCANPY__DIM_REDUCTION__PCA (1)                                                         [100%] 1 of 1 _  
[bf/512993] process > harmony_scenic:HARMONY:NEIGHBORHOOD_GRAPH:SC__SCANPY__NEIGHBORHOOD_GRAPH (1)                                                        [100%] 1 of 1 _  
[cf/67753f] process > harmony_scenic:HARMONY:DIM_REDUCTION_TSNE_UMAP:SC__SCANPY__DIM_REDUCTION__TSNE (1)                                                  [100%] 1 of 1 _  
[1d/aed565] process > harmony_scenic:HARMONY:DIM_REDUCTION_TSNE_UMAP:SC__SCANPY__DIM_REDUCTION__UMAP (1)                                                  [100%] 1 of 1 _
[ce/6cd4ba] process > harmony_scenic:HARMONY:DIM_REDUCTION_TSNE_UMAP:GENERATE_REPORT:SC__SCANPY__GENERATE_REPORT (1)                                      [100%] 1 of 1 _
[00/6ccb92] process > harmony_scenic:HARMONY:DIM_REDUCTION_TSNE_UMAP:GENERATE_REPORT:SC__SCANPY__REPORT_TO_HTML (1)                                       [100%] 1 of 1 _  
[b1/f8f5de] process > harmony_scenic:HARMONY:CLUSTER_IDENTIFICATION:SC__SCANPY__PARAM_EXPLORE_CLUSTERING (13)                                             [100%] 13 of 13 _
[dd/8197f6] process > harmony_scenic:HARMONY:CLUSTER_IDENTIFICATION:GENERATE_REPORT:SC__SCANPY__PARAM_EXPLORE_CLUSTERING_GENERATE_REPORT (13)             [100%] 13 of 13 _
[11/cd5d77] process > harmony_scenic:HARMONY:CLUSTER_IDENTIFICATION:GENERATE_REPORT:SC__SCANPY__REPORT_TO_HTML (13)                                       [100%] 13 of 13 _
[bb/75431a] process > harmony_scenic:HARMONY:CLUSTER_IDENTIFICATION:SC__SCANPY__PARAM_EXPLORE_MARKER_GENES (13)                                           [100%] 13 of 13 _
[60/acb155] process > harmony_scenic:HARMONY:BEC_HARMONY:SC__HARMONY__HARMONY_MATRIX (1)                                                                  [100%] 1 of 1 _  
[70/0e4082] process > harmony_scenic:HARMONY:BEC_HARMONY:SC__H5AD_UPDATE_X_PCA (1)                                                                        [100%] 1 of 1 _  
[77/391996] process > harmony_scenic:HARMONY:BEC_HARMONY:PUBLISH_BEC_OUTPUT:COMPRESS_HDF5 (1)                                                             [100%] 1 of 1 _
[f2/3ecbd4] process > harmony_scenic:HARMONY:BEC_HARMONY:PUBLISH_BEC_OUTPUT:SC__PUBLISH (1)                                                               [100%] 1 of 1 _
[6d/f80437] process > harmony_scenic:HARMONY:BEC_HARMONY:PUBLISH_BEC_OUTPUT:SC__PUBLISH_PROXY (1)                                                         [100%] 1 of 1 _  
[0f/4e697f] process > harmony_scenic:HARMONY:BEC_HARMONY:NEIGHBORHOOD_GRAPH:SC__SCANPY__NEIGHBORHOOD_GRAPH (1)                                            [100%] 1 of 1 _  
[9f/00cf18] process > harmony_scenic:HARMONY:BEC_HARMONY:DIM_REDUCTION_TSNE_UMAP:SC__SCANPY__DIM_REDUCTION__TSNE (1)                                      [100%] 1 of 1 _  
[1b/c2112e] process > harmony_scenic:HARMONY:BEC_HARMONY:DIM_REDUCTION_TSNE_UMAP:SC__SCANPY__DIM_REDUCTION__UMAP (1)                                      [100%] 1 of 1 _  
[4e/179fc7] process > harmony_scenic:HARMONY:BEC_HARMONY:DIM_REDUCTION_TSNE_UMAP:GENERATE_REPORT:SC__SCANPY__GENERATE_REPORT (1)                          [100%] 1 of 1 _  
[12/906242] process > harmony_scenic:HARMONY:BEC_HARMONY:DIM_REDUCTION_TSNE_UMAP:GENERATE_REPORT:SC__SCANPY__REPORT_TO_HTML (1)                           [100%] 1 of 1 _  
[96/66259c] process > harmony_scenic:HARMONY:BEC_HARMONY:PUBLISH_BEC_DIMRED_OUTPUT:COMPRESS_HDF5 (1)                                                      [100%] 1 of 1 _  
[fa/c1fd43] process > harmony_scenic:HARMONY:BEC_HARMONY:PUBLISH_BEC_DIMRED_OUTPUT:SC__PUBLISH (1)                                                        [100%] 1 of 1 _
[c4/19b866] process > harmony_scenic:HARMONY:BEC_HARMONY:PUBLISH_BEC_DIMRED_OUTPUT:SC__PUBLISH_PROXY (1)                                                  [100%] 1 of 1 _
[08/39865a] process > harmony_scenic:HARMONY:BEC_HARMONY:CLUSTER_IDENTIFICATION:SC__SCANPY__PARAM_EXPLORE_CLUSTERING (12)                                 [100%] 13 of 13 _
[77/6c7ad3] process > harmony_scenic:HARMONY:BEC_HARMONY:CLUSTER_IDENTIFICATION:GENERATE_REPORT:SC__SCANPY__PARAM_EXPLORE_CLUSTERING_GENERATE_REPORT (13) [100%] 13 of 13 _
[45/f6e010] process > harmony_scenic:HARMONY:BEC_HARMONY:CLUSTER_IDENTIFICATION:GENERATE_REPORT:SC__SCANPY__REPORT_TO_HTML (13)                           [100%] 13 of 13 _
[3e/d54b16] process > harmony_scenic:HARMONY:BEC_HARMONY:CLUSTER_IDENTIFICATION:SC__SCANPY__PARAM_EXPLORE_MARKER_GENES (13)                               [100%] 13 of 13 _
[44/ac8420] process > harmony_scenic:HARMONY:BEC_HARMONY:PUBLISH_FINAL_HARMONY_OUTPUT:SC__PUBLISH_PROXY (13)                                              [100%] 13 of 13 _
[e5/54e24b] process > harmony_scenic:HARMONY:BEC_HARMONY:GENERATE_DUAL_INPUT_REPORT:SC__SCANPY__GENERATE_DUAL_INPUT_REPORT (13)                           [100%] 13 of 13 _
[fa/629580] process > harmony_scenic:HARMONY:BEC_HARMONY:GENERATE_DUAL_INPUT_REPORT:SC__SCANPY__REPORT_TO_HTML (13)                                       [100%] 13 of 13 _
[c6/d8d835] process > harmony_scenic:HARMONY:FINALIZE:SC__H5AD_TO_FILTERED_LOOM                                                                           [100%] 1 of 1 _
[aa/341890] process > harmony_scenic:HARMONY:FINALIZE:FILE_CONVERTER_TO_SCOPE:SC__H5AD_TO_LOOM (1)                                                        [100%] 1 of 1 _
[3c/66a01e] process > harmony_scenic:HARMONY:FINALIZE:FILE_CONVERTER_TO_SCANPY:SC__H5AD_MERGE (1)                                                         [100%] 1 of 1 _
[1f/5e01dc] process > harmony_scenic:HARMONY:SC__DIRECTS__SELECT_DEFAULT_CLUSTERING (1)                                                                   [100%] 1 of 1 _
[d3/5863af] process > harmony_scenic:HARMONY:UTILS__GENERATE_WORKFLOW_CONFIG_REPORT                                                                       [100%] 1 of 1 _
[36/908c7a] process > harmony_scenic:HARMONY:SC__SCANPY__MERGE_REPORTS (13)                                                                               [100%] 13 of 13 _
[0c/18dc63] process > harmony_scenic:HARMONY:SC__SCANPY__REPORT_TO_HTML (13)                                                                              [100%] 13 of 13 _
[bc/dffd75] process > harmony_scenic:PUBLISH_HARMONY:COMPRESS_HDF5 (1)                                                                                    [100%] 1 of 1 _
[81/07b150] process > harmony_scenic:PUBLISH_HARMONY:SC__PUBLISH (1)                                                                                      [100%] 1 of 1 _
[78/a1aa0e] process > harmony_scenic:PUBLISH_HARMONY:SC__PUBLISH_PROXY (1)                                                                                [100%] 1 of 1 _
[66/cffe26] process > harmony_scenic:SCENIC_APPEND:scenic:ARBORETO_WITH_MULTIPROCESSING (1)                                                               [100%] 1 of 1 _
[39/e19e25] process > harmony_scenic:SCENIC_APPEND:scenic:CISTARGET__MOTIF (1)                                                                            [100%] 1 of 1 _
[9c/a63fb0] process > harmony_scenic:SCENIC_APPEND:scenic:CISTARGET__TRACK (1)                                                                            [100%] 1 of 1 _
[2f/2e5784] process > harmony_scenic:SCENIC_APPEND:scenic:AUCELL__MOTIF (1)                                                                               [100%] 1 of 1 _
[ea/73e894] process > harmony_scenic:SCENIC_APPEND:scenic:AUCELL__TRACK (1)                                                                               [100%] 1 of 1 _
[05/038a2c] process > harmony_scenic:SCENIC_APPEND:scenic:MERGE_MOTIF_TRACK_LOOMS (1)                                                                     [100%] 1 of 1 _
[5e/979e99] process > harmony_scenic:SCENIC_APPEND:scenic:VISUALIZE (1)                                                                                   [100%] 1 of 1 _
[cc/4bbad1] process > harmony_scenic:SCENIC_APPEND:scenic:PUBLISH_LOOM (1)                                                                                [100%] 1 of 1 _
[5d/409798] process > harmony_scenic:SCENIC_APPEND:APPEND_SCENIC_LOOM (1)                                                                                 [100%] 1 of 1 _
[ad/4ff545] process > harmony_scenic:SCENIC_APPEND:GENERATE_REPORT (1)                                                                                    [100%] 1 of 1 _
[4a/71935a] process > harmony_scenic:SCENIC_APPEND:REPORT_TO_HTML (1)                                                                                     [100%] 1 of 1 _
[6b/d8bada] process > harmony_scenic:PUBLISH_HARMONY_SCENIC:COMPRESS_HDF5 (1)                                                                             [100%] 1 of 1 _
[3a/2b195d] process > harmony_scenic:PUBLISH_HARMONY_SCENIC:SC__PUBLISH (1)                                                                               [100%] 1 of 1 _
[fb/f0a8db] process > harmony_scenic:PUBLISH_HARMONY_SCENIC:SC__PUBLISH_PROXY (1)                                                                         [100%] 1 of 1 _
WARN: To render the execution DAG in the required format it is required to install Graphviz -- See http://www.graphviz.org for more info.
Duration    : 2h 43m 4s
CPU hours   : 37.5
Succeeded   : 240
```
