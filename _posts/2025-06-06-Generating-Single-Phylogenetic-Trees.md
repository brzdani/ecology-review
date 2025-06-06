---
title: "Generating Single Phylogenetic Trees"
author: Daniel Borzoo 
date: 2025-06-06
---

<script src="https://polyfill.io/v3/polyfill.min.js?features=es6"></script>
<script id="MathJax-script" async
  src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js">
</script>
<script>MathJax = {tex: {inlineMath: [["$", "$"]]}}</script>



An unrooted phylogenetic tree does not assume knowledge of a common ancestor, but only positions the taxa to show their relative relationships. In a rooted tree, all the sequences under study have a common ancestor or root node from which a unique evolutionary path leads to all other nodes. 

![image](https://github.com/user-attachments/assets/9e835388-0077-40cb-8ec0-7e690dca84ab)

Many techniques such as molecular clock, Bayesian molecular clock, outgroup rooting, or midpoint rooting methods tend to estimate the root of a tree using data and assumptions. 

## Molecular clock hypothesis
---

Molecular clock is an assumption by which molecular sequences evolve at constant rates so that the amount of accumulated mutations is proportional to evolutionary time. Based on this hypothesis, branch lengths on a tree can be used to estimate divergence time. Let the rate of neutral mutations (i.e. mutations with no effect on fitness) in a new individual be μ. The probability that this new mutation will become fixed in the population is then 1/N, since each copy of the gene is as good as any other. Every generation, each individual can have new mutations, so there are μN new neutral mutations in the population as a whole. That means that each generation, μ new neutral mutations will become fixed. If most changes seen during molecular evolution are neutral, then fixations in a population will accumulate at a clock-rate that is equal to the rate of neutral mutations in an individual.

![image_2025-06-06_13-13-01](https://github.com/user-attachments/assets/f8f171b6-732f-4124-a506-a4de2e198ce7)


The search for a correct tree topology can sometimes be extremely difficult and computationally demanding. The reason is that the number of potential tree topologies can be enormously large even with a moderate number of taxa. 

The number of rooted trees ($N_R$) for n taxa is determined by the following formula:

$$
  N_R = \frac{(2n-3)!}{2^{n-2} (n-2)!}
$$

For unrooted trees, the number of unrooted tree topologies ($N_U$) is:

$$
  N_U = \frac{(2n-5)!}{2^{n-3} (n-3)!}
$$

Sometimes a tree-building method may result in several equally optimal trees. A consensus tree can be built by showing the commonly resolved bifurcating portions and collapsing the ones that disagree among the trees, which results in a polytomy.

Combining the nodes can be done by:
- strict consensus
- majority rule
- semi-strict consensus tree

In a strict consensus tree, all conflicting nodes are collapsed into polytomies. In a semi-strict consensus tree, indicates all relationships supported by one or both trees and not contradicted by either. Sometimes it is called combinable-component consensus. In a consensus tree based on a majority rule, among the conflicting nodes, those that  agree by more than 50% of the nodes are retained whereas the remaining nodes are collapsed into multifurcation.

Quantitative character was seen as a form of continuous distribution, observed by measuring, had many controller genes, influenced by environmental factors very easily and selected through data analysis.

Qualitative character was seen as a form of rigid distribution, observed visually, had one or two controller genes, influenced by environmental factors very scarcely and selected visually. 

There are two main classes of techniques for reconstructing phylogenetic trees. Clustering methods gradually build up the tree, starting from a small number of sequences and adding one sequence at each step. The output from these methods is a single tree that attempts to recover the evolutionary relationships between the sequences. In the second group of methods, many different tree topologies are generated and each is tested against the data in a search for those that are optimal or close to optimal according to particular criteria. We will discuss clustering methods first, followed by the other techniques. 

## CONSTRUCTING A CLADOGRAM
---

There are two ways to group taxa together based on shared apomorphies. 
- Hennig Argumentation
- Wagner Method

### Constructing a Cladogram: Hennig Argumentation

The information in character 1 unites taxa A, B, and C because they share the apomorphic state. The tree that shows this relationship is:
<p align = 'left'> 
  <img src="https://github.com/user-attachments/assets/8bd9e589-0fb2-41d2-b97e-831feb6b712e" width= "310"/>
  <img src="https://github.com/user-attachments/assets/58b03234-aa38-4e01-a984-cb2ec8b9a4e0" width= "500"/>
</p> 

Character 2 - the derived state is found only in taxon B. It is an autapomorphy of that taxon and provides no information about the relationships among the taxa:

<p align = 'left'> 
  <img src = "https://github.com/user-attachments/assets/0f0413d9-9e2d-4444-a904-541d5170a4d3" width = "310"/>
</p>

Character 3 - the derived state is an autapomorphy. 

![image](https://github.com/user-attachments/assets/4b592a96-8748-4a21-b912-573b9699adf6)

Character 4 - the derived state is a synapomorphy that unites taxa B and C

![image](https://github.com/user-attachments/assets/6315d6b8-fef4-4c1e-89f9-fbe31c6f85f4)


Character 5 - the derived state is an autapomorphy for taxon A

![image](https://github.com/user-attachments/assets/1c512bfd-0729-4ffb-a5f6-e1e53cc701ba)

Do not generate a hypothesis any more complex than is demanded by the data. This is because the simplest explanation requires the fewest assumptions and the fewest leaps of logic. In dealing with problems that may have an infinite number of possible solutions, choosing the simplest model may help to “shave off” those variables that are not really necessary to explain the phenomenon. By doing this, model development may become easier, and there may be less chance of introducing inconsistencies, ambiguities, and redundancies, hence, the name Occam’s razor.

The length, or number of steps, is the total number of character state changes necessary to support the relationship of the taxa in a tree. The better a tree fits the data, the fewer homoplasies will be required and the fewer number of character state changes will be required. Therefore, a tree with a lower length fits the data better than a tree with a higher length. The tree with the lowest length compels us to assume fewer homoplasies and so is more parsimonious- it will be the hypothesis of taxa relationship that is selected. 

The relative amount of homoplasy can be measured using the consistency index (often abbreviated CI). It is calculated as the number of steps expected given the number of character states in the data, divided by the actual number of steps multiplied by 100. The formula for the CI is:

![image](https://github.com/user-attachments/assets/dcc05a7b-32ef-4e09-8e6a-12df288eca80)

Another measure of the relative amount of homoplasy required by a tree is the retention index (RI). The retention index measures the amount of synapomorphy expected from a data set that is retained as synapomorphy on a cladogram.

![image](https://github.com/user-attachments/assets/ec628a8c-5b67-47cd-b079-30a3dea1e984)


## Distance Based Methods
---

Distance methods proceed in two steps:
-  Estimation of evolutionary distances
-  Infer tree topology on the basis of estimated evolutionary distances

### UPGMA & WPGMA

The first distance method we will look at—UPGMA—is simple to apply, but has the disadvantage that it assumes a constant molecular clock. The name UPGMA is an acronym of unweighted pair-group method using arithmetic averages, a description of the technique used. Assumption of a constant rate of evolution has important consequences for a dataset of sequences that are all associated with the same evolutionary time point, namely the present day, as it dictates that the same number of substitutions will have occurred in each sequence since the time of the last common ancestor. Thus, the distance from any node to any leaf that is its descendant will be the same for all descendants. The trees produced by this method are rooted and ultrametric, and all the leaves are at the same distance from the root.

The sequences are grouped into clusters as the tree is constructed, each cluster being defined as the set of all descendants of the new node just added. Initially, all sequences are regarded as defining their own cluster. At each stage, the two clusters with the shortest evolutionary distance are combined into a new cluster. The tree is complete when all the sequences belong to the same cluster, whose node is the root of the tree.

The distance between two clusters is defined as follows. Consider the construction of a tree for N sequences and suppose that at some stage you have clusters X containing $N_X$ sequences and Y containing $N_Y$ sequences. Initially, each cluster will contain just one sequence. The evolutionary distance (dXY) between the two clusters X and Y is defined as the arithmetic average of the distances between their constituent sequences, that is 

$$
  dXY = \frac {1}{N_XN_Y} \sum {dij}
$$

where i labels all sequences in cluster X, j labels all sequences in cluster Y, and dij is the distance between sequences i and j. When two clusters X and Y are combined to make a new cluster Z there is an efficient way of calculating the distances of other clusters such as W to the new cluster. The new distances can all be defined using existing cluster-to-cluster distances without the need to use the constituent sequence-to-sequence distances, using the equation

$$
  dZW = \frac {N_XdXW + N_YdYW}{N_Y + N_X}
$$

This method is very straightforward to apply, and can be used to construct trees for large sets of sequences.

![image](https://github.com/user-attachments/assets/e4255603-5053-4846-97cb-526db983707c)

 It often occurs in ecology that groups of objects, representing different regions of a territory, are of unequal sizes. Eliminating objects to equalize the clusters would mean discarding valuable information. However, the presence of a large group of objects, which are more similar a priori because of their common origin, may distort the UPGMA results when a fusion occurs with a smaller group of objects. Sokal & Michener (1958) proposed a solution to this problem, called weighted arithmetic average clustering (“WPGMA” in Sneath & Sokal, 1973: “Weighted Pair-Group Method using Arithmetic averages”). This solution consists in giving equal weights, when computing fusion similarities, to the two branches of the dendrogram that are about to fuse. This is equivalent, when computing a fusion similarity, to giving different weights to the original similarities, i.e. down-weighting the largest group. Hence the name of the method. 

###  The neighbor-joining method

The neighbor-joining (NJ) method proposed by Naruya Saitou and Masatoshi Nei in 1987 does not assume all sequences have the same constant rate of evolution over time, and  is more generally applicable than UPGMA. The basis of the method lies in the concept of minimum evolution, namely that the true tree will be that for which the total branch length, S, is shortest. The resulting tree is not rooted and is additive, a property that is assumed in deriving the formulae for its construction.

Neighbors in a phylogenetic tree are defined as a pair of nodes that are separated by just one other node. As with the methods described above, pairs of tree nodes are identified at each step of the method and used to gradually build up a tree. The way in which pairs of clusters are identified as neighbors in each step is different from that used UPGMA, resulting in the potential to generate a different topology.

To derive the neighbor-joining equations, consider Nsequences, labeled 1 to N. The two trees of Figure below illustrate one step of the neighbor-joining technique. The tree in Figure A is a star tree, in which all sequences are related directly to a single ancestral sequence at node X. Figure B shows a closely related tree in which neighbor sequences 1 and 2 have been separated from node X by another node, Y.  Note that because these trees are not rooted, the direction of evolution along the branch connecting X and Y is not clear. The distance between two sequences is written dij for sequences i and j. The length of a branch of a tree between leaf (or node) e and node f is called bef, and the total branch length S of a star tree such as that in Figure A is given by

$$
  S = \sum {b_{iX}} = \frac{1}{N - 1} \sum {dij}
$$

 ![image](https://github.com/user-attachments/assets/839e4cb1-5ff8-41ab-ab70-ee95309dbf7d)

The total branch length of the tree in Figure B, where sequences 1 and 2 have been removed from the central node X by internal node Y, is given by

$$
  S_{12} = b_{1Y} + b_{2Y} + b_{XY} + \sum_{i=3} {b_{iX}} 
$$

which needs to be converted into a form that uses the sequence distances d. 

 
