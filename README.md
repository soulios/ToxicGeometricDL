# ToxicGeometricDL
A repo of the most seminal applications of geometric deep learning in toxicity prediction tasks.

The most comprehensive professionally curated resource on Geometric Deep learning applied in toox pred tasks including
the best tutorials, videos, books, papers, articles, courses, websites, conferences and open-source libraries.
Since, predictive toxicology is a niche field, many papers are from neighboring fields such as drug discovery or plain DL which are just applied in toxicology datasets.

The papers will be listed by time order, noting the advancements along the way.

Disclaimer: All the images are sourced from the resources I linked.

# Table of Contents 
- [Tutorials](#Tutorials)
- [Papers](#Papers)
- [Articles/Blogs](#Articles)
- [Repositories](#Repositories)
- [Videos](#Videos)
- [Tools](#Tools)
- [What is a graph?](#What-is-a-graph?)
- [Graph Neural Networks](#Graph-Neural-Networks)
- [Graph Convolutions](#Graph-Convolutions)



## Papers
| Paper | Author | Year | Github | Comments | Datasets|
| ---------- | ----- | --- | --- | -------------| -----|
| __General interest__ | | | | |
|[Gated Graph Sequence Neural Networks](https://arxiv.org/abs/1511.05493?context=stat)|Li et al.|2015| [Github](https://github.com/yujiali/ggnn)|LSTM on graphs|Graph algorithm tasks|
| [Semi-Supervised Classification with Graph Convolutional Networks](https://arxiv.org/abs/1609.02907) | Kipf and Welling | 2016 | [Github](https://github.com/tkipf/gcn) | The most influential GCN🔥🔥🔥| Citation datasets|
|[Graph Attention Networks](https://arxiv.org/abs/1710.10903)| Velickovic et al. | 2017| [Github](https://github.com/PetarV-/GAT)| Introduced attention to GNNs. Not implemented inductively though.🔥🔥🔥| Citation and PPI|
|[Inductive Representation Learning on Large Graphs](https://cs.stanford.edu/people/jure/pubs/graphsage-nips17.pdf)| Hamilton et al.| 2017|[Github](https://github.com/williamleif/GraphSAGE)|The inductive variant of Kipf's GCN along with different aggregator functions|Citation and PPI|
|[Geom-GCN: Geometric Graph Convolutional Networks](https://arxiv.org/abs/2002.05287) | Pei et al. | 2020|[Github](https://github.com/graphdml-uiuc-jlu/geom-gcn)|Transductive model including geometric info|Citation networks|
| __Pooling?__ | | | | | |
|[Hierarchical Graph Representation Learning with Differentiable Pooling](https://arxiv.org/abs/1806.08804)| Ying | 2018|[Github](https://github.com/RexYing/diffpool)|Pooling hierarchical better than global mean and sum and sortpooling| ENZYMES,PROTEINS,REDDIT.COLAB|
| __Molecular property/activity/toxicity prediction__| | | | | |
| [Convolutional Networks on Graphs for Learning Molecular Fingerprints](https://arxiv.org/abs/1509.09292) | Duvenaud et al. | 2015 | [Github](https://github.com/HIPS/neural-fingerprint) | Aligned the notion of graph embedding to molecular fingerprints | Solubility, Drug efficacy|
| [Molecular Graph Convolutions: Moving Beyond Fingerprints](https://arxiv.org/abs/1603.00856?context=stat) | Kearnes et al. | 2016 | [DeepChem](https://github.com/deepchem) | Introduced edge features. Used weave convolutions and noticed that complex atom/bond featurizations do not enhance the model |PCBA,MUV,Tox21|
| [Convolutional Embedding of Attributed Molecular Graphs for Physical Property Prediction](https://pubs.acs.org/doi/10.1021/acs.jcim.6b00601) | Coley et al.| 2017 | [Github](https://github.com/connorcoley/conv_qsar_fast) | Atom features in graphs like ECFP, bond features are not updating. Not an improvement over Tox21 Challenge winner | Solubility, Tox21|  
| [Neural Message Passing for Quantum Chemistry](https://proceedings.mlr.press/v70/gilmer17a.html)| Gilmer et al. | 2017 |[Github](https://github.com/priba/nmp_qc)| Introduced the concept of Message passing networks. Also, tried to encode spatial info about the graph by distance bins, super nodes and virtual edges and resembled model ensembling by the concept of multiple towers🔥🔥🔥|QM9|
|[Learning Graph-Level Representation for Drug Discovery](https://arxiv.org/abs/1709.03741) | Li et al. | 2017|[Github](https://github.com/ZJULearning/graph_level_drug_discovery)|Introduced dummy super node connected to all the other nodes to learn global features | Tox21(0,76 scaffold)ToxCast,HIV,PCBA,MUV|
|[PotentialNet for Molecular Property Prediction](https://pubs.acs.org/doi/full/10.1021/acscentsci.8b00507) | Feinberg et al. | 2018| [DGL-lifesci](https://github.com/awslabs/dgl-lifesci) | Used another type of split called agglomerative by the pairwise similarity of every ligand-protein pair,Unknown split on tox21|PDBBind,QM8,Tox21(0.856)|
|[Adaptive Graph Convolutional Neural Networks](https://ojs.aaai.org/index.php/AAAI/article/view/11691) | Li et al. | 2018|[Github](https://github.com/codemarsyu/Adaptive-Graph-Convolutional-Network)|A successful spectral graph model|Tox21,CLinTox,ToxCast|
|[Graph classification using structural attention](https://dl.acm.org/doi/pdf/10.1145/3219819.3219980) | Lee et al. | 2018|[Github](https://github.com/benedekrozemberczki/GAM)|Improved attention|HIV,NCI|
|[Chemi-Net: A Molecular Graph Convolutional Network for Accurate Drug Property Prediction](https://www.mdpi.com/1422-0067/20/14/3389/htm) | Liu et al. | 2019|None|Predicting ADME properties with a multitask GCN.Surpassed a known tool by far,Cubist|ADME|
|[Analyzing Learned Molecular Representations for Property Prediction](https://pubs.acs.org/doi/full/10.1021/acs.jcim.9b00237) | Yang et al. | 2019|[Chemprop](https://github.com/chemprop/chemprop)|The directed edges reduce the noise.They added also global features by RDKit.SOTA results on Tox21 but excellent github resource|Most molecular datasets🔥🔥🔥🔥🔥🔥🔥🔥🔥|
|[Strategies for Pre-training Graph Neural Networks](https://arxiv.org/abs/1905.12265) | Hu et al. | 2019| [DGL-lifesci](https://github.com/awslabs/dgl-lifesci)|Combination of node-wise(context pred and attr masking) and graph-wise supervised pretraining does not cause negative transfer🔥🔥🔥|ChEMBL,ZINC,Tox21,ToxCast etc|
|[Pushing the Boundaries of Molecular Representation for Drug Discovery with the Graph Attention Mechanism](https://pubs.acs.org/doi/10.1021/acs.jmedchem.9b00959) | Xiong et al. | 2020| [DeepChem](https://github.com/deepchem)  |AttentiveFP was a significant improvement to previous models.They added chirality to atom features and stereo to bond features.Also,they used GRU as a readout.Check for aromaticity pretraining task.|Most molecular datasets|
|[Multi-View Graph Neural Networks for Molecular Property Prediction](https://arxiv.org/abs/2005.13607) | Ma et al. | 2020|None|Graph seen in two ways, edge-central and node-central and a cross-dependent passing enhances more the model, Check for interpretability(Tox21 scaf 0.836🔥🔥🔥|Most molecular datasets|
|[Communicative Representation Learning on Attributed Molecular Graphs](https://www.ijcai.org/proceedings/2020/0392.pdf) | Song et al. | 2021|[Github](https://github.com/SY575/CMPNN)|D-MPNN but with a communicative function to boost the edge messages🔥🔥🔥|Same as Gilmer DMPNN|
|__Graph Contrastive learning__| | | | |
|[Knowledge graph-enhanced molecular contrastive learning with functional prompt](https://www.nature.com/articles/s42256-023-00654-0#Sec14) | Y. Fang et al. | 2023 | KNOWLEDGE GRAPH enhanced pretrained, SOTA but expensive KG🔥🔥🔥|Most molecular datasets(Tox21=0.837)|
|[MoCL: Data-driven Molecular Fingerprint via Knowledge-aware Contrastive Learning from Molecular Graph](https://arxiv.org/abs/2106.04509) | Sun et al. | 2021|Local level contrastive learning by bioisostere substitution, and global-level maximizing the similarity of ECFPs ang graph embeddings. NEGATIVE TRANSFER on TOX datasets|Bace,BBBP,Tox21,ToxCast|
|[Molecular contrastive learning of representations via graph neural networks](https://www.nature.com/articles/s42256-022-00447-x) | Wang et al. | 2022| Best contrastive so far, augmenting by subgraph removal|Most molecular datasets(Tox21=0.8)|
| __Pretraining-Transfer Learning__ | | | | | |
|[Geometry-enhanced molecular representation learning for property prediction](https://www.nature.com/articles/s42256-021-00438-4)|Fang et al.|2022|[Github](https://github.com/PaddlePaddle/PaddleHelix/tree/dev/apps/pretrained_compound/ChemRL/GEM)|Pre-train on geometry info improves the downstream task performance🔥🔥🔥|Most molecular datasets|
|[PRE-TRAINING MOLECULAR GRAPH REPRESENTATION WITH 3D GEOMETRY](https://arxiv.org/pdf/2110.07728.pdf)|Liu et al.|2022|Contrast 2D with 3D or generate 3D from 2D, NOT IMPROVED|Most molecular datasets|
| __Multi-modal__ | | | | | |
|[Dual-view Molecule Pre-training](https://arxiv.org/pdf/2106.10234.pdf)|Zhu et al.| 2021|SMILES transformer and GNN node masking as pretraining, Dual view consistenscy loss|PubChem 10M|LESS THAN 0.8 ON TOX21 &#9658;   `        |
|[Molecule Property Prediction Based on Spatial Graph Embedding](https://pubs.acs.org/doi/10.1021/acs.jcim.9b00410) | Wang et al. | 2018|[Github](https://github.com/1128bian/C-SGEN)|1D-convolutions on each atom's features using skip connections + fingerprints|ESOL,lipophilicity,PDBBind|
| __Data-centric AI__ | | | | | |
|[ASGN: An Active Semi-supervised Graph Neural Network for Molecular Property Prediction](https://dl.acm.org/doi/pdf/10.1145/3394486.3403117)| Hao et al. | 2020|[Github](https://github.com/HaoZhongkai/AS_Molecule)|Active Learning surpassed Infograph and Mean Teaches and SelfSL but still expensive|QM9,OPV|
|[Chemical toxicity prediction based on semi-supervised learning and graph convolutional neural network](https://jcheminf.biomedcentral.com/articles/10.1186/s13321-021-00570-8)| Chen et al. | 2021 | [Github](https://github.com/chen709847237/SSL-GCN)| Mean-Teacher mediocre results|Tox21,QM9,ZINC|
|[Low Data Drug Discovery with One-Shot Learning](https://pubs.acs.org/doi/10.1021/acscentsci.6b00367) | Altae-Tran et al. | 2017|[DeepChem](https://github.com/deepchem)|One-shot learning in graph classification tasks paired with LSTM updates|Tox21(0.827),SIDER,MUV|
| __Graph Generation/ De novo molecule design__ | | | | | |
|[Junction Tree Variational Autoencoder for Molecular Graph Generation](https://proceedings.mlr.press/v80/jin18a.html) | Jin et al. | 2018|[Github](https://github.com/wengong-jin/icml18-jtnn)|JTVAE generating molecules by first creating scaffolds|ZINC|
|[MolGAN: An implicit generative model for small molecular graphs](https://arxiv.org/abs/1805.11973) | De Cao and Kipf | 2018|[Github](https://github.com/nicola-decao/MolGAN)|GANs and RL combined gave valid, novel but not unique molecules|QM9|
|[Graph Convolutional Policy Network for Goal-Directed Molecular Graph Generation](https://proceedings.neurips.cc/paper/2018/file/d60678e8f2ba9c540798ebbde31177e8-Paper.pdf) | You et al. | 2018|[Github](https://github.com/bowenliu16/rl_graph_generation)|GCPN uses adversarial training and RL,better than JT-VAE but not compared to molgan|ZINC|
|[MoFlow: An Invertible Flow Model for Generating Molecular Graphs](https://dl.acm.org/doi/abs/10.1145/3394486.3403104)| Zang et al. | 2020|[Github](https://github.com/calvin-zcx/moflow)|Best compared to any other graph generation|QM9,ZINC|
|[GraphAF: a Flow-based Autoregressive Model for Molecular Graph Generation](https://arxiv.org/abs/2001.09382) | Shi et al. | 2019|[Github](https://github.com/DeepGraphLearning/GraphAF)One of the first flow based approaches|ZINC|
| __Variational Graph Autoencoders__| | | | |
|[Variational Graph Auto-Encoders](https://arxiv.org/abs/1611.07308) | Kipf amd Welling | 2016|[Github](https://github.com/tkipf/gae)|The first GVAE on link prediction tasks|Citation|
|[Constrained Graph Variational Autoencoders for Molecule Design](https://arxiv.org/abs/1805.09076) | Liu et al. | 2018|[Github](https://github.com/microsoft/constrained-graph-variational-autoencoder)|Novel unique and valid molecules🔥🔥🔥||CEPDB,QM9,ZINC|
|[Constrained Generation of Semantically Valid Graphs via Regularizing Variational Autoencoders](https://proceedings.neurips.cc/paper/2018/file/1458e7509aa5f47ecfb92536e7dd1dc7-Paper.pdf) | Ma et al. | 2018|None|Mediocre results in graph generation|QM9,ZINC|
|__Graph Unet__| | | | |
|[Graph U-Nets](https://arxiv.org/pdf/1905.05178.pdf)| Gao and Li |2018|none|com|
|__Graph Transformers__| | | | |
|[Self-Supervised Graph Transformer on Large-ScaleMolecular Data](https://papers.nips.cc/paper/2020/hash/94aef38441efa3380a3bed3faf1f9d5d-Abstract.html)|Rong et al.|2020|[Github](https://github.com/tencent-ailab/grover)|Dynamic MPNN:Number of hops is random|ChEMBL,ZINC|
|[Graph Transformer Networks](https://arxiv.org/abs/1911.06455) | Jun et al. | 2020|An improvement compared to GAT to learn better node-level representations|IMDB and Citations|
|__Graph Explainability__| | | | |
|[GNNExplainer: Generating Explanations for Graph Neural Networks](https://arxiv.org/abs/1903.03894) | Ying et al. | 2019|A model-agnostic, single-instance,post-hoc explanation by extracting subgraphs|MUTAG,REDDIT|
|[Reinforced Causal Explainer for Graph Neural Networks](https://arxiv.org/abs/2204.11028?context=cs.AI) | Wang et al. | 2022 |It frames the explanation task as a sequential decision process.|MUTAG,REDDIT,Genome|
|__Reviews__ | | | | |
|[Graph convolutional networks: a comprehensive review](https://computationalsocialnetworks.springeropen.com/articles/10.1186/s40649-019-0069-y?ref=https://githubhelp.com) | Zhang et al. | 2019|none|com|
|[How Powerful are Graph Neural Networks?](https://arxiv.org/abs/1810.00826) | Xu et al. | 2019|none|com|
|[Does GNN Pretraining Help Molecular Representation?](https://arxiv.org/abs/2207.06010) |Sun et al. |2022 |MUST READ🔥🔥🔥| ABLATION STUDIES| |
|[Graph convolutional networks for computational drug development and discovery](https://academic.oup.com/bib/article/21/3/919/5498046?login=true) | Sun et al. | 2020|none|com|
|[Graph neural networks: A review of methods and applications](https://www.sciencedirect.com/science/article/pii/S2666651021000012) | Zhou et al. | 2020|none|com|
|[A compact review of molecular property prediction with graph neural networks](https://www.sciencedirect.com/science/article/pii/S1740674920300305) | Wieder et al. | 2020 |none|🔥🔥🔥|
|[Could graph neural networks learn better molecular representation for drug discovery? A comparison study of descriptor-based and graph-based models](https://jcheminf.biomedcentral.com/articles/10.1186/s13321-020-00479-8) | Jiang et al. | 2021 |none|🔥🔥|


## Tutorials

- [Intro to Graph Neural Networks](https://www.youtube.com/watch?v=8owQBFAHw7E)
- [UvA DL Notebooks](https://uvadlc-notebooks.readthedocs.io/en/latest/tutorial_notebooks/tutorial7/GNN_overview.html)

## Articles
- [Understanding GNNs](https://distill.pub/2021/understanding-gnns/) :fire: :fire: :fire:
- [Introduction to Graph Neural Networks](https://theaisummer.com/graph-convolutional-networks/)
- [Graph Convolutional Networks](https://tkipf.github.io/graph-convolutional-networks/)
## Repositories
- [Chemprop: A library with MPNN and D-MPNN applications on molecular datasets](https://github.com/chemprop/chemprop)🔥

## Videos
-[ An Introduction to Graph Neural Networks: Models and Applications](https://www.youtube.com/watch?v=zCEYiCxrL_0) by Miltos ALlamanis(Microsoft Research)🔥🔥🔥
- [Intro to graph neural networks (ML Tech Talks)](https://www.youtube.com/watch?v=8owQBFAHw7E) by Petar Velickovic(DeepMind)🔥🔥🔥
- [Understanding Graph Neural Networks](https://www.youtube.com/watch?v=fOctJB4kVlM) by DeepFindr
- [The AI EPiphany](https://www.youtube.com/c/TheAIEpiphany/playlists) by Gordic Aleksa


## Tools
- [DGL-lifesci](https://lifesci.dgl.ai/):  DGL-LifeSci is a python package for applying graph neural networks to various tasks in chemistry and biology.🔥🔥🔥
- [Pytorch-Geometric](https://pytorch-geometric.readthedocs.io/en/latest/) PYG is a library to easily train Graph Neural Networks (GNNs) for a wide range of applications related to structured data.
- [Dive Into Graphs](https://diveintographs.readthedocs.io/en/latest/) DIG provides a unified testbed for higher level, research-oriented graph deep learning tasks, such as graph generation, self-supervised learning, explainability, and 3D graphs.
- [RDKit](https://www.rdkit.org/): A cheminformatics library for generating/calculating molecular descriptors and fingerprints and handling molecules
- [MoleculeNet](https://moleculenet.org/): A library for benchmarking ML models across different molecular tasks
- [DeepChem](https://github.com/deepchem/deepchem): A toolkit which includes a lot of different models and datasets with relevant tutotials for gentle introduction into molecular ML. 







## What is toxicology?

Toxicology is the study of the adverse effects of chemicals or physical agents on living organisms.

It can be clustered by the degree of their damage to cell (cytotoxicity), organ (hepatotoxicity) or systemic toxicants (mutagenicity,genotoxicity).
Any given chemical has to undergo a rigorous, expensive and time-consuming toxicity-assessment.
The field of computational toxicology tries to alleviate this burden by building QSAR (quantitative structure-activity relationship) models that 
associate a structure to a specific toxic effect.
For many years , that was a task of experienced chemists that know which fragments of a molecule are potentially toxic and build models based on these so called structural alerts. Basically, if a substructure was identified as part of a molecule, that molecule had a higher probability of being toxic.
The last two decades there has been a lot of development as we developed ways to represent a molecule in a machine-readable way.
Among the most popular are the SMILES strings, the molecular descriptors and the molecular fingeprints.
For the computer though, toxicity is just a dataset where a chemical has a label of 1 or 0 encoding being toxic or not.
The last fifteen years they have been developed several datasets with these mappings based on lab experiments.
MoleculeNet is a library that gathered all these as a benchmark for the ML models.
Based on these representations and coupled with ML and DL models, we achieved great results. In the last few years, graph neural networks seem to dominate the research interest of the field. As graphs are a new input for our models, it was intuitive that molecules can be described as graphs and that lit the spark for the development of this field and the reason for this repo.


## What is a graph?
A graph G is a set of nodes and vertices between them G(V,E). Molecules can be intuitively seen as graphs where the nodes are the atoms and the edges are the bonds between them.


![alt text](https://github.com/soulios/MolecularGeometricDL/blob/main/image/graphs.png?raw=true)


How we  use the graphs as input though?

The graph can be represented essentially by three matrices:
- The adjacency matrix, which shows how the nodes(atoms) are connected
- The node features matrix, which encodes information about every node(atom)
- The edge features matrix, whoch encodes information about the edge(bond)


![alt text](https://github.com/soulios/MolecularGeometricDL/blob/main/image/graphmatrices.png?raw=true)

## Graph Neural Networks

GNNs are a type of networks that operate on these graphs. 

There are two ways to develop GNNs, spectrally and spatially.

Both tried to generalize the mathematical concept of convolution to graphs.
The spectral methods stuck to the strict mathematical notions resorted to the frequency domain(Laplacian eigenvectors).
Being computationally expensive and not applicable to inductive scenarios, they finally died out.
Spatial ones form the ones, now known as graph convolutions and are the ones that we are going to analyse more.
If you still want to get a basic understanding of spectral methods you can advise the links below.

Oops, I mentioned inductive without even explaining. The image speaks for itself.

__Inductive learning:__
This type of learning is like the usual supervised learning. The model has not seen the nodes/graphs that will
later classify. This applies to graph-classification tasks which are our main interst for molecular proprerty
prediction.

__Transductive learning:__
In transductive learning, the model has seen the nodes without their labels and/or some features but gets an
understanding of how they are connected within the graph. That is useful mainly for node-classification tasks.

![alt text](https://github.com/soulios/MolecularGeometricDL/blob/main/image/inductive.png?raw=true)



## Graph Convolutions

__Normal Convolutions__

A typical feed forward network does a forward pass with the following equation:

- __Y = &#963;(W*X + &#946;)__,

where σ is a non-linear function(ReLU,tanh), W is the weight associated with each feature, X the features and β is the bias.

In convolutional neural networks, the input usually is an image(i.e a tensor height* width*channels). 

- An RGB image has three channels whereas a greyscale only one. 

- In CNNs, the W is called a filter or kernel and is usually a matrix(2x2, 3x3 etc.) which is the same passed acrossed the image to extract features(patterns) from every part of the image.

- That is called weight sharing. That is done because a pattern is interesting wherever it is in the image(translational invariance)


![alt text](https://github.com/soulios/MolecularGeometricDL/blob/main/image/cnns.gif)

The question became how we can generalize the convolutions to graphs?

There are some significant differences between images and graphs.
- Images are positioned in a Euclidean space, and thus have a notion of locality.Pixels that are close to each other will be much more strongly related than distant ones. Graphs on the other hand do not as information about the distance between nodes is not encoded.
- Pixels follow an order while graph nodes do not.
So, the locality is achieved in graphs based on neighborhoods.
Also, we adopt the weight sharing from the normal convolutions.

__Invariance__

The order invariance is achieved by applying functions that are order invariant
Permutation matrix, P is a matrix that only changes the order of another matrix.
So for every P, the following equation should be obeyed.
- f(PX)=f(X)

__Equivariance__

But if we wanted information on node-level the invariant function would not suffice. Instead, we need a permutation equivariant function that do not change the node order and follow the following equation.
- f(PX)=Pf(X)

We can think of these functions f that transform the x<sub>i</sub> features of a node to a latent vector h<sub>i</sub>.


__h<sub>i</sub> = f(x<sub>i</sub>)__

Stacking these will result in 
__H = f(X)__

How we can use these latent vectors?

![alt text](https://github.com/soulios/MolecularGeometricDL/blob/main/image/graphtasks.png?raw=true)

But hold on...

How we incorporate the adjacency matrix A into this equation?

A simple update rule: 

__H<sub>k+1</sub> = &#963;(A*W*H<sub>k</sub>)__, 
where A is the adjacency matrix, k is the number of itearations and we dropped β for simplicity reasons.

Hopefully the similarities with the classical equation are obvious.

Node-wise the equation is written:

__h<sub>i</sub> = Σ (W*h<sub>j</sub>)__,

where j is every neighbor of the node i.

Let's see it in practice:


![alt text](https://github.com/soulios/MolecularGeometricDL/blob/main/image/adjacency.png?raw=true)

Considering this adjacency matrix, when we update the state of the node v<sub>1</sub>, we will take into account its neighbor states.
That although would be wrong as we'll be entirely dropping the previous state of node v<sub>1</sub>. 
So, we need to make a correction to the adjacency matrix A by adding the identity matrix and creating the matrix Ã.
That would add 1s across the diagonal making each node a neighbor of itself, i.e we add self-loops.

![alt text](https://github.com/soulios/MolecularGeometricDL/blob/main/image/adjacencycorrected.jpg?raw=true)

Each latent vector of a node is a sum of the vectors of its neighbors. So, if the degree of a node( degree shows to how many neighbors a node has) is really high the scale of the latent vector would be entirely different and we'll face vanishing or exploding gradients.
- So, we should normalize based on the degree of the node.
Firstly we calculate degree matrix, D by summing up row-wise the adjacency matrix, Ã.


![alt text](https://github.com/soulios/MolecularGeometricDL/blob/main/image/degree.jpg?raw=true)

Then, we inverse it and thus the equation takes the form.


![alt text](https://github.com/soulios/MolecularGeometricDL/blob/main/image/inversedegree.jpg?raw=true)

__H<sub>k+1</sub> = &#963;(ÃD<sup>-1</sup>W<sub>k</sub>H<sub>k</sub>)__

__WE DID IT!__
We now have the first equation upon we can build our different variants of graph convolutions.

This equation essentially describes a simple averaging of the neighbors' vectors.
This update of the state of the vectors happens for i number of steps.
On each step or a neighborhood hop you aggregate the vectors fo the neighbors.
Once we have all the latent vectors for each node after k number of steps, we can use these for node classification or in our case
we can aggregate them and reach a unique embedding for every graph.
# GCN Variants
- GCN

The most known variation of graph convolutions was set by [Kipf & Welling](https://arxiv.org/abs/1609.02907)
in 2017. 
They introduced a renormalization trick which is more than just a mere average of the neighbors.
They normalize by  1&#247;&#8730;(d<sub>i</sub> * d<sub>j</sub>)


__H<sub>k+1</sub> = &#963;(D<sup>-1/2</sup>ÃD<sup>-1/2</sup>W<sub>k</sub>H<sub>k</sub>)__

From now on, we'll refer to it as the __GCN__.

- GAT(Graph Attention Networks)

Petar Velickovic had another [idea](https://arxiv.org/abs/1710.10903). Instead, of giving an equal weight to every neighbor that will be added explicitly, 
a concept called attention. So, the node-wise equation now became:

__h<sub>i</sub> = σ(Σ(a<sub>ij</sub>h<sub>j</sub>))__
![alt text](https://github.com/soulios/MolecularGeometricDL/blob/main/image/GAT.png?raw=true)

The a<sub>ij</sub> comes from applying a softmax to e<sub>ij</sub> = a(h<sub>i</sub>,h<sub>j</sub>)
which are non-normalized coefficients across pairs of nodes

Influenced by the results of [Vaswani et al.](https://arxiv.org/abs/1706.03762)
they included multi head attention mechanisms which is essentially a K 
number of replicates which are then concatenated or aggregated. The following figure from the paper makes it abundantly 
clear.
![alt text](https://github.com/soulios/MolecularGeometricDL/blob/main/image/GAT-MULTI.png?raw=true)


# Message Passing Neural Nets

The term message-passing arised in 2017 and  is really intuitive way to see graph neural nets.
The two main points evolve around the two functions that happen in a GNN
- The Update function, q
- The Aggregate function, U

From this [youtube video](https://www.youtube.com/watch?v=zCEYiCxrL_0) we can sum them up by the figure.

![alt text](https://github.com/soulios/MolecularGeometricDL/blob/main/image/MPNN.png?raw=true)

Essentially we concatenate the vector of the node-in-focus of the previous step with the edges K and its neighbors.
The resulting vector passed through an update function f and then aggregated by the function U. 
Finally they are passed through a non-linear function to get new updated representation.

The previously described GCN and GAT, following a similar [formalism](https://towardsdatascience.com/a-unified-view-of-graph-neural-networks-12b40e8fdac5)
can be described in the following figures.
![alt text](https://github.com/soulios/MolecularGeometricDL/blob/main/image/GCNGATMP.png?raw=true)


This [article](https://distill.pub/2021/understanding-gnns/) includes an interactive session to play aroung with graphs and the most essential GNN variants.

