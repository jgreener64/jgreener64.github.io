+++
title = "Where next for structural bioinformatics?"
date = Date(2025, 10, 15)
+++

# Where next for structural bioinformatics?

*Joe Greener - 15th October 2025*

I still remember the day I found out about AlphaFold 2 \citep{Jumper2021}. Sat at home in November 2020, shortly before the virtual CASP14 conference, I was idly playing a video game in the evening and hoping that COVID would end. An email pinged in from the CASP organisers providing a table of the results. In typical CASP fashion, it wasn't a simple ranking of each group's performance; it was a large table of results that required processing. I grew frustrated as I wrote a bash script to sort it. No matter how many times I tried, it seemed like one group had smashed it across the board. Then I realised: my script was fine, the problem had effectively been solved. My first thought was excitement, where is Slack, I need to talk about this. My second thought? Where does this leave structural bioinformatics.

## Cut to five years later

Despite a few predictions of its decline, structural biology is in rude health. Getting the structure is only part of the process, and AlphaFold only works some of the time. You get the structure in order to interpret it and learn things, often with experiments, so AlphaFold has given structural biology a boost and become an important tool in the toolkit.

True single sequence structure prediction remains elusive. The cautious old guard who initially responded by highlighting the difference between protein structure prediction (the what) and protein folding (the how), correctly saying that the second remains an open problem, have surprised nobody by not going on to work on protein folding[^folding].

CASP has struggled for funding, been given a reprieve by Google, and continues to assess the many AlphaFold variants. Many companies have been drawn in, assembling and then sometimes laying off biological research groups. Structural bioinformatics has evolved somewhat. Is this a good thing? Well, let's consider the main aims of the discipline[^aims].

## What are we trying to do?

1. Understand biomolecules by considering structures at scale, rather than individually. This is how the field began, when the PDB started getting big enough that only the likes of Alexey Murzin could keep it all in their head, and the diversity revealed patterns in evolution and function. Structural classifications like CATH and SCOP were a natural consequence of this.

2. Make predictive models, with the idea that biologists would use these on their system of interest. This includes prediction of structure, function, interactions, binding sites, and other tasks like structural alignment. Also, produce databases of predictions using these models. On a deeper level, this is partly an attempt to understand the world, since you do not understand what you cannot predict. As we will come on to, though, being able to predict something doesn't necessarily mean that you do understand it.

3. Design new biomolecules. It's debatable whether this falls under the banner, but given that modern protein design and structure prediction use similar models it seems fair to include it. More broadly, design of drugs and organisms.

⠀

## How are we doing with respect to those aims?

Structural bioinformatics in 2025 seems to be mainly three things:

1. AlphaFoldology: reproducing, retraining, explaining, ablating, using for screening, tuning MSA inputs, estimating errors, extending to ensembles, integrating experimental data. A hot topic in Nature and across social media was whether and how AlphaFold can output different conformations of fold-switching proteins \citep{WaymentSteele2024, Schafer2025}. This might help study individual systems, but I struggle to get enthusiastic about the fundamental question. Does it teach us something about the world if a black box model predicts one thing or another? AlphaFoldology is directly concerned with aims 2 and 3 above, and does little to increase our scientific understanding on its own. Nonetheless, I find myself excited about the upcoming release of OpenFold and the associated ablations that will let me, too, peek inside the crystal ball. Recent announcements of the SGC Target2035 and OpenBind efforts to increase the amount of protein-ligand data are welcome, and point to a better understanding of drug binding as well as the obvious outcome of more data for training predictive models.

2. Large language models (LLMs) for protein, and increasingly DNA, sequences. These have found wide use as foundation models that "compress biology" and work well as inputs for other supervised models (aim 2) and to generate sequences (aim 3). Whether they can produce genuinely new things or are just efficient samplers is an ongoing research area \citep{King2025}, and sadly one where you have to deal with the bluster of multiple startups. ESM3 can supposedly simulate "500 million years of evolution" \citep{Hayes2025}, which is an interesting way of saying that they designed a fluorescent protein with 58% sequence identity to a known fluorescent protein[^esm]. Again, though, LLMs infiltrating every corner of bioinformatics does not seem to lead to understanding directly, and may hinder it by reducing the interpretability of model inputs for downstream models. Until we can formulate our questions in a closed, maths Olympiad style that is catnip to modern reasoning models, it's not clear that we can extract the biological reasoning that we are after.

3. Protein design, mainly of binders but increasingly of enzymes and proteins with specific desirable features. This has seen an explosion of work and venture funding in the last few years, driven by the rise of generative AI in general and the repurposing of AlphaFold-like architectures in particular. This is a clear success story with widely-available computational methods, even if experimental success has a high barrier of entry and is limited to a few groups. Models like RFdiffusion get a lot of the attention, but ProteinMPNN \citep{Dauparas2022} deserves much of the credit for making inverse folding routine. There is a long tail of sketchy conference workshop papers, but [I've spoken about that before](https://jgreener64.github.io/posts/science_the_hard_way) and it just has to be tolerated. This is clearly associated with aim 3, though we can learn principles too \citep{Koga2012}.

The theme is that there is a lot of prediction and design, and not much focus on what we can learn with all this \citep{Bromberg2025}. We now have the AlphaFold database, foundation models that supposedly span all scales of biology, and seem to be able to design binders to arbitrary proteins. Shouldn't we have tried to use these to learn something? I don't mean for individual systems, biologists do that, I mean use the data deluge to do some, you know, informatics.

## A science not a service

There have of course been efforts to cluster the AlphaFold database \citep{BarrioHernandez2023, Durairaj2023}, and while these do provide insights themselves the main output seems to be the processed data for others to use. The Encyclopedia of Domains (TED) takes a careful, domain-based approach and provides more CATH annotations \citep{Lau2024}. This treasure trove of data can surely be used for more in the future. We spent so long trying to get all the protein structures, but we could have thought more about what we were going to do with them once we had them.

How about looking at evolution through the lens of structure and comparing proteomes across the tree of life? How about understanding the link between structure and function, without cheating by transferring annotations from homologs? How about explaining the origin and function of unusual protein chemistries \citep{vonPappenheim2022}? How about unsupervised protein classification and comparison to human classifications to reveal our biases? How about trying to find the unifying principles of nebulous concepts like allostery? How about wading into the liquid-liquid phase separation debate? How about working out how much of a simplification [Anfinsen's dogma](https://en.wikipedia.org/wiki/Anfinsen%27s_dogma) is \citep{Sorokina2018}?

I'm sure I've missed papers and people are doing these things. I can't help but feel, though, that structural bioinformatics should move beyond making predictions and start to ask what those predictions can teach us. We can't leave all the fun to the biologists; we should zoom out while they zoom in. We should, please, not let the field become a load of half-baked LLMs.[^leaving]

[^folding]: The ship has sailed on people using protein folding to mean protein structure prediction. Protein folding is of course fascinating but has less practical application than structure prediction, less data to train machine learning models on, and unclear metrics to target. The best paper is now 14 years old \citep{LindorffLarsen2011}.
[^aims]: I exclude molecular dynamics, which is more focused on physics than data, and sequence-based tasks like sequence searching which don't tend to use structure even if the sequences are of proteins.
[^esm]: How this conflation of process and outcome made it past authors, editors and reviewers is beyond me. Next time I empty my cup into the sink, though, I'll be satisfied that I simulated two weeks of evaporation.
[^leaving]: I'm trying to leave, but keep getting pulled in for one last job \citep{Greener2025}. Yes, it is a predictor.

*Thanks to Shaun Kandathil and Andy Lau for comments. All omissions remain my own.*

## References

* \biblabel{BarrioHernandez2023}{Barrio-Hernandez et al. 2023} Barrio-Hernandez I, Yeo J, Jänes J, Mirdita M, Gilchrist CLM, Wein T, Varadi M, Velankar S, Beltrao P and Steinegger M. Clustering predicted structures at the scale of the known protein universe, *Nature* 622, 637–645 (2023)
* \biblabel{Bromberg2025}{Bromberg and Shehu 2025} Bromberg Y and Shehu A. Better AI For Understanding Life on Earth: Predict First, Design Later, *Proceedings of the 2025 SIAM International Conference on Data Mining (SDM)* 443-446 (2025)
* \biblabel{Dauparas2022}{Dauparas et al. 2022} Dauparas J, Anishchenko I, Bennett N, Bai H, Ragotte RJ, Milles LF, Wicky BIM, Courbet A, de Haas RJ, Bethel N, Leung PJY, Huddy TF, Pellock S, Tischer D, Chan F, Koepnick B, Nguyen H, Kang A, Sankaran B, Bera AK, King NP and Baker D. Robust deep learning–based protein sequence design using ProteinMPNN, *Science* 378(6615), 49-56 (2022)
* \biblabel{Durairaj2023}{Durairaj et al. 2023} Durairaj J, Waterhouse AM, Mets T, Brodiazhenko T, Abdullah M, Studer G, Tauriello G, Akdel M, Andreeva A, Bateman A, Tenson T, Hauryliuk V, Schwede T and Pereira J. Uncovering new families and folds in the natural protein universe, *Nature* 622, 646–653 (2023)
* \biblabel{Greener2025}{Greener and Jamali 2025} Greener JG and Jamali K. Fast protein structure searching using structure graph embeddings, *Bioinformatics Advances* 5(1), vbaf042 (2025)
* \biblabel{Hayes2025}{Hayes et al. 2025} Hayes T, Rao R, Akin H, Sofroniew NJ, Oktay D, Lin Z, Verkuil R, Tran VQ, Deaton J, Wiggert M, Badkundri R, Shafkat I, Gong J, Derry A, Molina RS, Thomas N, Khan YA, Mishra C, Kim C, Bartie LJ, Nemeth M, Hsu PD, Sercu T, Candido S and Rives A. Simulating 500 million years of evolution with a language model, *Science* 387(6736), 850-858 (2025)
* \biblabel{Jumper2021}{Jumper et al. 2021} Jumper J, Evans R, Pritzel A, Green T, Figurnov M, Ronneberger O, Tunyasuvunakool K, Bates R, Žídek A, Potapenko A, Bridgland A, Meyer C, Kohl SAA, Ballard AJ, Cowie A, Romera-Paredes B, Nikolov S, Jain R, Adler J, Back T, Petersen S, Reiman D, Clancy E, Zielinski M, Steinegger M, Pacholska M, Berghammer T, Bodenstein S, Silver D, Vinyals O, Senior AW, Kavukcuoglu K, Kohli P and Hassabis D. Highly accurate protein structure prediction with AlphaFold, *Nature* 596, 583-589 (2021)
* \biblabel{King2025}{King et al. 2025} King SH, Driscoll CL, Li DB, Guo D, Merchant AT, Brixi G, Wilkinson ME and Hie BL. Generative design of novel bacteriophages with genome language models, *bioRxiv* (2025)
* \biblabel{Koga2012}{Koga et al. 2012} Koga N, Tatsumi-Koga R, Liu G, Xiao R, Acton TB, Montelione GT and Baker D. Principles for designing ideal protein structures, *Nature* 491, 222-227 (2012)
* \biblabel{Lau2024}{Lau et al. 2024} Lau AM, Bordin N, Kandathil SK, Sillitoe I, Waman VP, Wells J, Orengo CA and Jones DT. Exploring structural diversity across the protein universe with The Encyclopedia of Domains, *Science* 386(6721) (2024)
* \biblabel{LindorffLarsen2011}{Lindorff-Larsen et al. 2011} Lindorff-Larsen K, Piana S, Dror RO and Shaw DE. How Fast-Folding Proteins Fold, *Science* 334(6055), 517-520 (2011)
* \biblabel{Schafer2025}{Schafer et al. 2025} Schafer JW, Lee M, Chakravarty D, Thole JF, Chen EA and Porter LL. Sequence clustering confounds AlphaFold2, *Nature* 638, E8-E12 (2024)
* \biblabel{Sorokina2018}{Sorokina and Mushegian 2018} Sorokina I and Mushegian A. Modeling protein folding in vivo, *Biology Direct* 13, 13 (2018)
* \biblabel{vonPappenheim2022}{von Pappenheim et al. 2022} von Pappenheim FR, Wensien M, Ye J, Uranga J, Irisarri I, de Vries J, Funk L-M, Mata RA and Tittmann K. Widespread occurrence of covalent lysine-cysteine redox switches in proteins, *Nature Chemical Biology* 18, 368-375 (2022)
* \biblabel{WaymentSteele2024}{Wayment-Steele et al. 2024} Wayment-Steele HK, Ojoawo A, Otten R, Apitz JM, Pitsawong W, Hömberger M, Ovchinnikov S, Colwell L and Kern D. Predicting multiple conformations via sequence clustering and AlphaFold2, *Nature* 625, 832-839 (2024)
