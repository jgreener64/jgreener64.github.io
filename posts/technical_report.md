+++
title = "MirageBio Technical Report"
date = Date(2026, 4, 1)
+++

# MirageBio Technical Report

*Joe Greener - 1st April 2026*

Today we are excited to release our new protein structure model with state-of-the-art performance. We are making it available as a technical report, because apparently even pre-prints are supposed to have a methods section. Besides, how can we silently edit the post unless we host it ourselves?

Here at MirageBio we are deeply committed to pivoting to the latest trends. Last year that was protein design, but apparently now it is binding affinity. Next year it will be disordered proteins, but we are avoiding that because NMR data is hard to understand. On our carefully chosen benchmarks - it's hard to overstate how carefully we selected these benchmarks - we show a 1% improvement over a competitor we didn't run properly.

\figalt{A small molecule binding to a protein}{images/technical_report_protein.png}
*Competely accurate image of a small molecule binding to a protein. If we solve this problem, we solve drug discovery.*

How did we do this? We will say it was due to an innovative model architecture, and nobody can complain because there is no chance of anyone seeing the code. Too much risk of people finding our licence violations for that. It was really because we joined forces with other industry partners to freely share data amongst non-academics. Oh, and we added a new activation function we heard someone talking about at NeurIPS.

Our model generalises well across biology. For example, we took one protein kinase out of the dataset, left the other 500 in, and found excellent performance on the held-out protein. In fact, you don't even need to provide the target: we can rank a series of ligands without knowing what you want them to bind to. Our model generalises to unseen proteins. You'll have trouble proving us wrong there, because any protein you can provide has been seen.

In order to install our model you will need to download 2 TB of uncompressed sequence data from an unreliable server. You can either set up a conda environment that became impossible to resolve last year, or use a brand new Python packaging software that will be forgotten by next year.

You can also run our model via our proprietary GUI that one of our team vibe-coded whilst they were avoiding doing proper validation. We haven't found a case where it doesn't work, because we haven't used it ourselves yet. Under the hood we hammer a free web server to get our multiple sequence alignments, and we get angry when they rate-limit our requests and our paying customers complain to us.

We don't know what you're going to do with it. We don't even know what we are going to do with it. But we plan to keep following the hype, at least until corporate realises that we aren't making any money. In the mean time, come and find us at one of our 20 posters at ICLR.
