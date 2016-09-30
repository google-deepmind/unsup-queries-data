# Unsupervised Data Generated for GeoQuery and SAIL Datasets

This repository contains the generated unsupervised data for GeoQuery and SAIL
semantic parsing tasks.

For a detailed description of this see below and in the paper
[Semantic Parsing with Semi-Supervised Sequential Autoencoders](https://arxiv.org/abs/1609.09315),
Kočiský et al., EMNLP 2016.  Please cite the paper if you use this corpus in
your work.


### Bibtex

```
@inproceedings{emnlp16_kocisky,
author = {Tom\'a\v s Ko\v cisk\'y and G\'abor Melis and Edward Grefenstette and Chris Dyer and Wang Ling and Phil Blunsom and Karl Moritz Hermann},
title = {Semantic Parsing with Semi-Supervised Sequential Autoencoders},
url = {https://arxiv.org/abs/1609.09315},
booktitle = "Proceedings of the 2016 Conference on Empirical Methods in Natural Language Processing (EMNLP)",
year = "2016",
}
```


### GeoQuery Data

For GeoQuery, we fit a 3-gram Kneser-Ney model to the queries in the training
set and sample about 7 million queries from it. We ensure that the sampled
queries are different from the training queries, but do not enforce validity.


### SAIL Data

For this task we hand designed a maze by trying to approximately replicate the
key statistics of the existing mazes (corridor lengths, number and types of
intersections, object distribution).

#### Path navigation action sequences

To approximate the distribution of instruction sequences that correspond to
utterances in the SAIL dataset, we selected randomly a starting point, an ending
point, and a starting and ending orientation in the hand-designed maze. We then
found the shortest action sequence between the two points. The sequence was then
segmented into roughly utterance-sized instructions using heuristic rules.
