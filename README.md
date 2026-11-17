# Modularity on the Karate Club Graph

DSC212 – Graph Theory research assignment, Priyam Badal (IMS25293)

This notebook applies Newman's spectral modularity method (Newman, 2006) to Zachary's Karate Club graph, using NumPy and NetworkX. A community is split using the signs of the leading eigenvector of its modularity matrix block, and it is left alone once that eigenvalue is 0 or less. After every split I redrew the graph on a fixed layout and recomputed degree, betweenness, closeness and clustering for each node inside its own community, since computing them on the full graph would never change.

The first split gave Q = 0.372 and matched the real division of the club for 33 of 34 members (only node 8 was misplaced), and it scores higher than the real split itself (Q = 0.358). Three more splits brought Q up to 0.409, ending with communities of 13, 10, 5, 5 and 1 members. Most of the gain came from the first cut. Nodes 0 (Mr. Hi) and 33 (the Officer) stayed the most central nodes at every stage. Betweenness shifted the most as the communities shrank, while the clustering coefficient was the least useful for picking out leaders, because it favoured low-degree nodes in tight peripheral groups. An optional section compares the handout's block-restricted matrix with Newman's generalised matrix, which gives 4 communities and Q = 0.393.

## Reference

Newman, M. E. J. (2006). Modularity and community structure in networks. *PNAS*, 103(23), 8577–8582.
