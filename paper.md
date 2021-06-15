---
title: 'pipra: pixel-precise annotator for semantic segmentation'
tags:
  - Python
  - Deep Learning
  - Supervised learning
  - Semantic segmentation
authors:
  - name: Andreas M. Kist # note this makes a footnote saying 'co-first author'
    orcid: 0000-0003-3643-7776
    affiliation: "1" # (Multiple affiliations must be quoted)
affiliations:
 - name: Department Artificial Intelligence in Biomedical Engineering, Friedrich-Alexander-University, Erlangen-Nürnberg
   index: 1
date: 15 June 2021
bibliography: paper.bib
---

# Summary

Semantic segmentation is a key task in Deep Learning, where each pixel of 
a given image is assigned to a class, e.g. fore- and background. The training of deep 
neural networks is typically supervised and requires therefore ground-truth data,
such as a binary mask stating fore- and background. As further larger amounts of
data are needed, efficient tools are crucial. Here, we provide `pipra`,
a smart tool for generating efficiently binary masks using different modes of 
annotation. 

# Statement of need

Predicting binary masks is a common task in modern deep learning. There are plenty
of tools that allow the annotation, such as [LabelMe] and [LabelBox].
However, many of these tools are focusing on completeness in application and
are not optimized to a given problem. 

With `pipra`, we focus on the efficient generation of binary masks with 
maximum interoperability. In detail, pipra is easy to install from an Anaconda
environment (`pip install pipra`) and can be executed by typing `pipra`. 
We further offer a pre-compiled version on [anki.xyz/pipra](https://www.anki.xyz/pipra).

`pipra` constists of a graphical user interface (GUI) written in Python and relies
on the libraries PyQt5 and pyqtgraph. For fast operations, we rely on numpy arrays [citation] and
utilize LLVM compiled functions using `numba` [citation] to further accelerate the annotation.

`pipra` allows the annotation using three major modalities (Figure \ref{fig:modalities}): 

  - Brush
  - Outline
  - Floodfill

![Labelling modalities in pipra. a) Brush, b) Outline, c) Floodfill.\label{fig:modalities}](modalities.png)

In general, `pipra` is intended for time variant data, such as videos, or z-stacks, such as
microscopy stacks at different positions in `z`. In addition, `pipra` also provides a folder mode
to label efficiently multiple images in a given folder without individual loading and saving.
The resulting segmentations masks are stored as `hdf5` container to offer maximum flexibility,
but can be easily exported from the graphical user interface to `tif` and `mp4` files.

`pipra` was already successfully applied in several biomedical image segmentation tasks to allow
the segmentation of the glottal area in high-speed videoendoscopy footage [@gomez:2020;@kist:2020]
or the segmentation of cerebellar Purkinje cells in confocal stacks [@markov:2020],
and is currently being used to label dendritic spines.

# Acknowledgements

We acknowledge contributions from Pablo Gómez on this project for testing and improving it.

# References

