# Fargrapher
Cartography of the farcaster network

## Overview, MVP
1. Started by taking edge/node data from [nounderline/farcaster-social-graph](https://github.com/nounderline/farcaster-social-graph/). 500 users, 36,348 edges.


# Graph Theory + ML
## Laplacian
- Graph equivalent for the laplace operator, $\nabla^2$. 
$$
L = D - A
$$
where 
- $D$ is the degree of the vertex. $D_{in}$, $D_{out}$ and therefore $L_{in}$, $L_{out}$ are different.
- $A$ adjacency matrix, symmetric for undirected graphs.

## Spectral Embedding + Clustering
- Eigenvector/values of laplacian matrix can be used for spectral clustering. To create a K-dimensional embedding:
    - Compute Laplacian matrix of graph, potentially [normalise](https://en.wikipedia.org/wiki/Laplacian_matrix#Laplacian_matrix_normalization_2). 
    - Compute K smallest eigenvalues, use associated K eigenvectors to create a $(n, k)$ embedding matrix.
    - Clustering via traditional clustering techniques for dense $(n, k)$ matrices, e.g. k nearest neighbours.