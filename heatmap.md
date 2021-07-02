### Create a heatmap from otu table
````R
utils:::menuInstallPkgs()
library(BiocManager)
BiocManager::install("phyloseq")
library(phyloseq)

tab <- read.table("otu.txt", sep ="\t", header=TRUE, row.names= 1)
OTU <- otu_table(tab, taxa_are_rows =TRUE)
plot_heatmap(OTU, method = "NMDS", distance = "bray")
