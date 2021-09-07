# Part 1 - Index Hopping Filtering and Cell Ranger

## 1.1. Index Hopping Filter

This step is using the `index-hopping-filter` to remove reads that were likely hopped during sequencing.

The `index_hopping_filter/metadata` folder contains the resulting files of running:

```
./index-hopping-filter mkcsv <INPUT>
```
