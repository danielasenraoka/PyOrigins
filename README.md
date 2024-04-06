# PyOrigins

This code computes the activity of a Protein-Protein Interaction Network (PPIN) associated with a specified gene set. The code is developed in Python 3.11.4 and implemented within a Jupyter notebook for interactive exploration.

A PPIN associated with a specific set of genes can be constructed by extracting the interactions from the full Human PPIN that involve proteins encoded by the genes within the defined gene set $x$. A score that reflects the activity of a PPIN can be defined for each cell $i$ as follows:

\begin{equation} \label{eq:cell_activity}
ACT_i^x = \frac{1}{m \cdot e} \sum_{j,k=1}^{m} A_{jk} Y_{ij} Y_{ik}.
\end{equation}

Where $A_{jk}$ is the upper triangular adjacency matrix, that characterizes the connectivity between genes $j$ and $k$ in the network.
$Y$ is the transposed normalized expression matrix of dimensions $n \times m$, and $e$ is the number of edges in the PPIN. To enhance clarity, each row of $Y$ is the expression profile of the $i$-th cell. Hence, $Y$ is the transposed counterpart of the conventional expression matrix, where rows correspond to genes and columns to cells. A normalization factor of $m \cdot e$ is introduced to account for graph size differences. This factor enables comparisons between samples and various PPINs.
