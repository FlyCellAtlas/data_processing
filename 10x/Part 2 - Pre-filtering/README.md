# Part 2 - Pre-filtering

## Relaxed

Doublet removal was applied along with basic (hard thresholds) filtering on quality control metrics (number of genes, percent of mitochondrial genes, ...).

## Stringent

Raw expression matrix was corrected for ambiant RNA contamination using DecontX (resulting empty cells were filtered out). Doublet removal was then applied along with an adaptive filtering on quality control metrics.
