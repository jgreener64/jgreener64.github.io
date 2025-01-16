+++
title = "My favourite papers 2001-2023"
date = Date(2025, 1, 16)
+++

# My favourite papers 2001-2023

*Joe Greener - 16th January 2025*

On [X](https://x.com/jgreener64/status/1879124605794975934) and [Bluesky](https://bsky.app/profile/jgreener64.bsky.social/post/3lfp4mw44u22g) I made a list of my favourite paper from each year. It is collected here for convenience.

## 2001

["Experimental and computational approaches to estimate solubility and permeability in drug discovery and development settings"](https://www.sciencedirect.com/science/article/abs/pii/S0169409X96004231) by Lipinski et al.

This classic paper introduces "Lipinski's rule of 5" for finding drugs with good absorption and permeability properties.

The rules are not always correct, since many drugs break them and there are alternative ways for drugs to get into cells.

But crucially this work is a quantifiable framework for thinking about the concepts of molecular size, lipophilicity, and the tradeoffs of increasing affinity during lead optimisation.

Still as relevant today as it was then.

## 2002

["The protein kinase complement of the human genome"](https://www.science.org/doi/10.1126/science.1075762) by Manning et al.

Protein kinases are a key class of proteins that regulate other proteins via phosphorylation.

This paper found 518 putative protein kinase genes, many for the first time.

This seems to still be the accepted number, give or take (there are also ~20 lipid kinases).

They classify the kinases and compare them across organisms, all while keeping it readable.

Honourable mention goes to Taylor's mad [paper](https://www.nature.com/articles/416657a) on a "periodic table" for protein structures.

I am glad unconventional ideas can (could?) make it into Nature.

## 2003

["Multiplexed-Replica Exchange Molecular Dynamics Method for Protein Folding Simulation"](https://www.sciencedirect.com/science/article/pii/S0006349503748978) by Rhee and Pande.

This paper didn't come up with the idea of REMD, which had been recently applied to biomolecules.

It developed the concept by having multiple replicas at each temperature, making the algorithm more suitable for distributed computing.

They folded a 23 amino acid protein in implicit solvent with Folding@home, the first time REMD had been used to fold a protein.

The development of a simulation algorithm to fit a specific computing model is particularly interesting here.

Honourable mention goes to Kuhlman et al.'s [paper](https://www.science.org/doi/10.1126/science.1089427) on the first de novo designed protein.

"What I cannot create, I do not understand" - Feynman.

## 2004

["Random-coil behavior and the dimensions of chemically unfolded proteins"](https://www.pnas.org/doi/10.1073/pnas.0403643101) by Kohn et al.

They expand on existing data and show that most chemically denatured proteins scale with polymer length by means of a power law.

This links denatured proteins to polymer theory and indicates that few proteins retain residual structure under strong denaturants.

It also demonstrates the power of corrections: a year after publication the prefactor of the scaling relationship was corrected from 1.330 to 1.927 Å. Quite an important change!

Honourable mention goes to Åqvist et al.'s [paper](https://www.sciencedirect.com/science/article/abs/pii/S0009261403021687) on a neat way to control pressure in MD simulations without calculating the virial.

OpenMM doesn't have virial calculation, and this is why.

## 2005

["TM-align: a protein structure alignment algorithm based on the TM-score"](https://academic.oup.com/nar/article/33/7/2302/2401364) by Zhang and Skolnick.

Methods to compare and align protein structures are essential. TM-align extends the TM-score to provide a metric that is normalised across protein size, runs from 0 to 1, and is sequence independent.

I've always found the cutoff of ~0.5 for the same fold to be useful, with peaks around 0.4 and 0.6 in distributions of TM-align scores indicating pairs with different and the same fold.

## 2006

["How many drug targets are there?"](https://www.nature.com/articles/nrd2199) by Overington et al.

They propose a consensus number of drug targets for all classes of drugs, reconciling previous estimates that differ by an order of magnitude.

This was the result of careful database review and dataset curation.

The main takeaways are that there were a small number (324) of drug targets and that more than half of drugs target GPCRs, nuclear receptors and ion channels.

## 2007

["Generalized neural-network representation of high-dimensional potential-energy surfaces"](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.98.146401) by Behler and Parrinello.

Machine learning interatomic potentials (MLIPs) are now the hot topic in computational chemistry. This paper was the first proper attempt at training a neural network on DFT data to obtain a fast, accurate MLIP.

Today the models are more elaborate and descriptive, but many of the basic concepts - a sum over atom energies, radial/angular symmetry functions, and smooth cutoffs based on distance - are present in this work.

Honourable mention goes to Bussi et al.'s [paper](https://pubs.aip.org/aip/jcp/article-abstract/126/1/014101/186581/Canonical-sampling-through-velocity-rescaling) (also from Parrinello) on rescaling velocities stochastically to sample the canonical distribution.

## 2008

["Crystal Structure of a Ten-Amino Acid Protein"](https://pubs.acs.org/doi/10.1021/ja8030533) by Honda et al.

This paper finds the crystal structure of CLN025, a more stable variant of the ten amino acid protein chignolin (which had an NMR structure) designed by the same first author.

They also see multiple folding/unfolding events in 1 μs of MD simulation.

The distinction between a peptide and a protein has always been unclear. Here there is a readable discussion which suggests defining a protein based on the shape of the energy surface.

## 2009

["Fpocket: An open source platform for ligand pocket detection"](https://bmcbioinformatics.biomedcentral.com/articles/10.1186/1471-2105-10-168) by Le Guilloux et al.

Finding potential ligand binding pockets on a protein is mostly a case of finding cavities on the surface.

Fpocket does this using Voronoi tessellation and alpha spheres that fill the empty space in cavities.

The software is open and easy to use, meaning it can be built on to develop other methods.

For example, my first paper re-ranked Fpocket pockets to find allosteric sites.

Honourable mention goes to Martínez et al.'s [paper](https://onlinelibrary.wiley.com/doi/10.1002/jcc.21224) on Packmol, popular software for generating MD starting configurations.

## 2010

["Efficient Nonbonded Interactions for Molecular Dynamics on a Graphics Processing Unit"](https://onlinelibrary.wiley.com/doi/abs/10.1002/jcc.21413) by Eastman and Pande.

Non-bonded interactions are the slowest part of a MD simulation, but are amenable to GPU acceleration.

This paper presents the algorithm used in OpenMM, which considers interacting blocks of atoms and can skip inter-block interactions if the blocks are far enough apart.

This is made efficient by periodically redefining the blocks to consist of atoms that are close in space.

The result is a fast algorithm that does not require a neighbour list.

## 2011

["How Fast-Folding Proteins Fold"](https://www.science.org/doi/10.1126/science.1208351) by Lindorff-Larsen et al.

They use the Anton supercomputer built for MD to run long MD simulations of small proteins.

The proteins repeatedly fold to their native structures and unfold, providing the best evidence yet that molecular mechanics force fields work for biomolecules.

Whilst classic papers often show their age, this one still feels fresh and the data remains popular to use.

The sampling, reaching milliseconds for some proteins, is still not achievable for most academic groups today.

Honourable mention goes to Morcos et al.'s [paper](https://www.pnas.org/doi/10.1073/pnas.1111471108) on direct-coupling analysis to predict contacting residues in protein structures.

## 2012

["HHblits: lightning-fast iterative protein sequence searching by HMM-HMM alignment"](https://www.nature.com/articles/nmeth.1818) by Remmert et al.

A fast sequence searching algorithm is developed which represents both query and database sequences as profile hidden Markov models.

This extends HHsearch to enable iterative searches that are more sensitive than PSI-BLAST.

Deep multiple sequence alignments are the bedrock of the protein structure prediction revolution, so fast methods to search large sequence databases will continue to be a crucial part of bioinformatics.

Honourable mention goes to Beauchamp et al.'s [paper](https://pubs.acs.org/doi/10.1021/ct2007814) on benchmarking force fields against NMR data.

## 2013

["PeptideBuilder: A simple Python library to generate model peptides"](https://peerj.com/articles/80) by Tien et al.

Software is developed to generate peptides from given backbone angles.

Whilst the software is nice, I like the paper for Table 1 which shows the RMSD when building peptides using different levels of information.

In short, if you only use backbone torsion angles (plus ideal bond lengths and angles) then you get high RMSD structures.

This shows how quickly errors propagate when building sequentially and has implications for neural network architectures.

Honourable mention goes to Pascanu et al.'s [paper](https://proceedings.mlr.press/v28/pascanu13) on the challenges when training recurrent neural networks and ways to address them.

## 2014

["Building Force Fields: An Automatic, Systematic, and Reproducible Approach"](https://pubs.acs.org/doi/10.1021/jz500737m) by Wang et al.

They use the ForceBalance method to train water models that fit a variety of experimental properties and QM data.

This involves taking the derivative of a thermodynamic average property with respect to the parameters.

In the machine learning age we should be able to quickly and reproducibly train whole force fields to match all sorts of properties.

Going beyond QM data may become increasingly important for machine learning potentials as they are applied to larger systems.

Honourable mention goes to Wang et al.'s [paper](https://www.nature.com/articles/nchem.2099) (also involving Pande) on high temperature QM simulations in a "nanoreactor" to explore the formation of life.

## 2015

["Accurate and Reliable Prediction of Relative Ligand Binding Potency in Prospective Drug Discovery by Way of a Modern Free-Energy Calculation Protocol and Force Field"](https://pubs.acs.org/doi/10.1021/ja512751q) by Wang et al.

This paper, primarily from Schrödinger, presents a free energy perturbation protocol that allows accurate prediction of protein-ligand binding affinities. This is useful in the lead optimisation stage of drug discovery.

Crucially they display a decent correlation across eight diverse systems, which have become useful data for the community.

There is still room to improve performance with better force fields, sampling and system setup.

Honourable mention goes to Bah et al.'s [paper](https://www.nature.com/articles/nature13999) on an intrinsically disordered protein that folds on phosphorylation, preventing its binding to another protein.

## 2016

["Design and synthesis of a minimal bacterial genome"](https://www.science.org/doi/10.1126/science.aad6253) by Hutchison et al.

They use whole-genome design and synthesis to develop a minimal bacterial genome consisting of 473 genes.

This is smaller than any independent cell found in nature.

Understandably, since biology is complex, this was very difficult. It turns out that there are quasi-essential genes that are required for robust growth, and 149 of the genes had unknown function.

## 2017

["Protein structure determination using metagenome sequence data"](https://www.science.org/doi/10.1126/science.aah4043) by Ovchinnikov et al.

This paper used Rosetta and residue-residue contact prediction from evolutionary information to generate protein structures for over 600 families that lacked them.

Structure prediction has improved vastly in the years since, with old school Rosetta no longer used for this purpose.

But the idea of using metagenomic sequence data to obtain deep MSAs is still important.

Honourable mention goes to Steinegger and Söding's [paper](https://www.nature.com/articles/nbt.3988) on MMseqs2, software for outrageously fast sequence searching.

## 2018

["Developing a molecular dynamics force field for both folded and disordered protein states"](https://www.pnas.org/doi/10.1073/pnas.1800690115) by Robustelli et al.

They benchmark existing force fields on folded and disordered proteins and show that none are able to describe both.

By modifying a few parameters they create the a99SB-disp force field which has good agreement to experiments across the board.

This paper was very influential on me as it showed both the deficiencies in force fields and the difficulties of manually tuning parameters to make improvements.

Ideally we would systematically improve all parameters at once to match the data.

Honourable mention goes to Sorokina and Mushegian's [paper](https://biologydirect.biomedcentral.com/articles/10.1186/s13062-018-0217-6) on whether proteins can fold by themselves. You probably haven't heard of this one, but it will make you question everything you thought you knew.

## 2019

["Learning Protein Structure with a Differentiable Simulator"](https://openreview.net/forum?id=Byg3y3C9Km) by Ingraham et al.

They develop a protein structure prediction algorithm that uses an energy function, a Langevin dynamics simulator and an imputation network.

To my knowledge it is the first paper to do differentiable molecular simulation.

The challenges in taking gradients through such models are also considered.

Honestly the approach is somewhat over-engineered and doesn't work that well, but the method is ambitious and some of the ideas would be refined in AlphaFold2.

Honourable mention goes to Drautz's [paper](https://journals.aps.org/prb/abstract/10.1103/PhysRevB.99.014104) on atomic cluster expansion, an elegant and popular approach for machine learning interatomic potentials.

## 2020

["Supervised Contrastive Learning"](https://proceedings.neurips.cc//paper/2020/hash/d89a66c7c80a29b1bdbab0f2a1a94af8-Abstract.html) by Khosla et al.

This paper presents a loss function for the supervised setting, where you want inputs in the same category to be close together in embedding space and those in different categories to be far apart.

It is conceptually simple but makes efficient use of the data and leads to well-separated embedding spaces.

Honourable mention goes to Wang et al.'s [paper](https://arxiv.org/abs/2003.00868) on differentiable molecular simulation, another early one for the field.

## 2021

["Learning neural network potentials from experimental data via Differentiable Trajectory Reweighting"](https://www.nature.com/articles/s41467-021-27241-4) by Thaler and Zavadlav.

This paper extends the ensemble reweighting approach for fitting force fields (including MLIPs) to experimental data in two ways: by using automatic differentiation through the whole scheme, and by reusing simulation data with perturbation theory.

This is applied to three examples, most impressively a DimeNet++ model for diamond.

Fitting many parameters at once is key to using all sorts of experimental data to improve MLIPs.

Honourable mention goes to Kidger's [PhD thesis](https://arxiv.org/abs/2202.02435) on neural differential equations, which is not technically a paper but surveys the field well and provides lots of insights.

## 2022

["End-to-end differentiable construction of molecular mechanics force fields"](https://pubs.rsc.org/en/content/articlelanding/2022/sc/d2sc02739a) by Wang et al.

They go beyond discrete atom types for molecular dynamics by treating molecules as graphs and using a graph neural network to predict atom embeddings.

The embeddings are then pooled in a clever way to get bonded parameters and partial charges.

This is probably the most influential paper on my future research direction. It points the way to fast, reproducible training on large QM datasets, and eventually to exploring new functional forms and the limits of pairwise force fields.

Honourable mention goes to Robustelli et al.'s [paper](https://pubs.acs.org/doi/10.1021/jacs.1c07591) on simulations of a small molecule binding to part of the intrinsically disordered protein α-synuclein.

## 2023

["Updated benchmarking of variant effect predictors using deep mutational scanning"](https://www.embopress.org/doi/full/10.15252/msb.202211474) by Livesey and Marsh.

This paper benchmarks 55 variant effect predictors on deep mutational scanning data and finds that unsupervised methods like ESM-1v, EVE and DeepSequence do well.

I have a lot of time for benchmarking studies that don't try to sell a new method as well, it increases the credibility of the results.

The thought of installing 55 pieces of bioinformatics software fills me with dread.

Honourable mention goes to Fu et al.'s [paper](https://openreview.net/forum?id=A8pqQipwkt) on benchmarking machine learning force fields, which suggests looking at stability as well as force accuracy.
