# PyOrigins

This code computes the activity of a Protein-Protein Interaction Network (PPIN) associated with a specified gene set. The code is developed in Python 3.11.4 and implemented within a Jupyter notebook for interactive exploration.

A PPIN associated with a specific set of genes can be constructed by extracting the interactions from the full Human PPIN that involve proteins encoded by the genes within the defined gene set $x$. A score that reflects the activity of a PPIN can be defined for each cell $i$ as follows:

$$ ACT_i^x = \frac{1}{e \cdot \mu_i} \sum_{j,k=1}^{m} A_{jk} Y_{ij} Y_{ik}. $$

Where $A_{jk}$ is the upper triangular adjacency matrix, that characterizes the connectivity between genes $j$ and $k$ in the network.
$Y$ is the transposed normalized expression matrix of dimensions $n \times m$, $e$ is the number of edges in the PPIN, and $\mu_i$ is the average expression of all genes in cell $i$. To enhance clarity, each row of $Y$ is the expression profile of the $i$-th cell. Hence, $Y$ is the transposed counterpart of the conventional expression matrix, where rows correspond to genes and columns to cells. Again, this adjustment enhances clarity regarding notation to avoid using transposed symbols or non-standard index orders. A normalization factor of $e \cdot \mu_i$ is introduced to account for graph size differences and differences in the mean expression. This factor enables comparisons between samples and various PPINs.
