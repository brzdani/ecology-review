---
title: "Generating Single Phylogenetic Trees"
author: Daniel Borzoo 
date: 2025-06-06
---

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

## CONSTRUCTING A CLADOGRAM
---

There are two ways to group taxa together based on shared apomorphies. 
- Hennig Argumentation
- Wagner Method

### Constructing a Cladogram: Hennig Argumentation

The information in character 1 unites taxa A, B, and C because they share the apomorphic state. The tree that shows this relationship is:

![image](https://github.com/user-attachments/assets/8bd9e589-0fb2-41d2-b97e-831feb6b712e)
![image](https://github.com/user-attachments/assets/58b03234-aa38-4e01-a984-cb2ec8b9a4e0)


There are two main classes of techniques for reconstructing phylogenetic trees. Clustering methods gradually build up the tree, starting from a small number of sequences and adding one sequence at each step. The output from these methods is a single tree that attempts to recover the evolutionary relationships between the sequences. In the second group of methods, many different tree topologies are generated and each is tested against the data in a search for those that are optimal or close to optimal according to particular criteria. We will discuss clustering methods first, followed by the other techniques. 



