[![CC BY-NC-SA 4.0][cc-by-nc-sa-shield]][cc-by-nc-sa]

<!---

    Copyright (c) 2022 Robert Bosch GmbH and its subsidiaries.

-->

# Knowledge Graph for Autonomous Driving (AD) Enhanced with Common Sense Knowledge (CSK)

This repository contains the dataset relevant for the following publication.

> Sreyasi Nag Chowdhury, Ruwan Wickramarachchi, Mohamed H. Gad-Elrab, Daria Stepanova, and Cory Henson.
> **Towards Leveraging Commonsense Knowledge for Autonomous Driving.** ISWC 2021 - Demos & Posters track. [[Text](http://ceur-ws.org/Vol-2980/paper396.pdf)]

More specifically, the dataset stores a collection of commonsense knowledge assertions relevant for the autonomous driving (AD) domain, which can be used either independently or in combination with pandaset (an open-source dataset for urban AD situations). 

Please cite the above paper if using the dataset.

## AD_CSK Knowledge Graph

The repository stores the following data:

(1) [pandaset.ttl](pandaset.ttl) - A knowledge graph [1] constructed relying on
- [Pandaset](https://scale.com/open-datasets/pandaset)
 
(2) [pandaset_ad_csk.ttl](pandaset_ad_csk.ttl) - An extension of pandaset.ttl with commonsense relations from:
- [ConceptNet](https://github.com/commonsense/conceptnet)
- [WebChild](https://www.mpi-inf.mpg.de/departments/databases-and-information-systems/research/yago-naga/commonsense/webchild/)
- [Quasi-mododo](https://github.com/Aunsiels/CSK)
- [CSKG](https://github.com/usc-isi-i2/cskg) 

(3) [link_prediction_models](link_prediction_models) - A folder with the link prediction models TransE [2] and HolE [3] pretrained using [Ampligraph 1.4](https://github.com/Accenture/AmpliGraph/) on (1) and (2).
To load the models run 
```python
from ampligraph.utils import  restore_model

model = restore_model('<model_name>.pkl')
```

(4) [explainable_clustering](explainable_clustering) - A folder with the explainable clustering results, i.e., the output of the method from [4] on the following input:
- [pandaset_no_literals.tsv](explainable_clustering/input/pandaset_no_literals.tsv): The KG (1) without literals in the tsv format
- [pandaset_ad_csk_no_literals.tsv](explainable_clustering/input/pandaset_ad_csk_no_literals.tsv): The KG (2) without literals in the tsv format
- [target_scene_entities.txt](explainable_clustering/input/target_scene_entities.txt): Scenes to be clustered


## References

[1] Ruwan Wickramarachchi, Cory Henson, and Amit Sheth. Knowledge-infused Learning for Entity Prediction in Driving Scenes. Frontiers in Big Data 4 (2021): 759110.

[2] Antoine Bordes, Nicolas Usunier, Alberto García-Durán, Jason Weston, Oksana Yakhnenko:
Translating Embeddings for Modeling Multi-relational Data. NIPS 2013: 2787-2795

[3] Maximilian Nickel, Lorenzo Rosasco, Tomaso A. Poggio:
Holographic Embeddings of Knowledge Graphs. AAAI 2016: 1955-1961

[4] Mohamed H. Gad-Elrab, Daria Stepanova, Trung-Kien Tran, Heike Adel, Gerhard Weikum:
ExCut: Explainable Embedding-Based Clustering over Knowledge Graphs. ISWC (1) 2020: 218-237

## License
This dataset is licensed under [Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License (CC-BY-SA-4.0)][cc-by-nc-sa].

[![CC BY-NC-SA 4.0][cc-by-nc-sa-image]][cc-by-nc-sa]

[cc-by-nc-sa]: http://creativecommons.org/licenses/by-nc-sa/4.0/
[cc-by-nc-sa-image]: https://licensebuttons.net/l/by-nc-sa/4.0/88x31.png
[cc-by-nc-sa-shield]: https://img.shields.io/badge/License-CC%20BY--NC--SA%204.0-lightgrey.svg
