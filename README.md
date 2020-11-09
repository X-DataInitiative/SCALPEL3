# SCALPEL3

SCALPEL3 framework is designed to perform scalable, reproducible and easy medical concepts extraction from large observational databases (LODs). In its current form, this library is focused on [SNDS]((https://www.snds.gouv.fr/SNDS/Accueil) Data. However, we believe it could be easily adapted to other LODs.

This work results from a research Partnership between [École Polytechnique](https://www.polytechnique.edu/en) & 
[Caisse Nationale d'Assurance Maladie](https://assurance-maladie.ameli.fr/qui-sommes-nous/fonctionnement/organisation/cnam-tete-reseau)
started in 2015 by [Emmanuel Bacry](http://www.cmap.polytechnique.fr/~bacry/) and [Stéphane Gaïffas](https://stephanegaiffas.github.io/).
Since then, many research engineers and PhD students developped and used this framework
to do research on SNDS data, the full list of contributors is available in [CONTRIBUTORS.md](CONTRIBUTORS.md).
This library is based on [PySpark](https://spark.apache.org/docs/latest/api/python/pyspark.html).

## SCALPEL-Flattening

[![CircleCI](https://circleci.com/gh/X-DataInitiative/SCALPEL-Flattening.svg?style=shield&circle-token=1c2d54e464ad11d11d5515221b75f644d1c6fb5a)](https://circleci.com/gh/X-DataInitiative/SCALPEL-Flattening)
[![codecov](https://codecov.io/gh/X-DataInitiative/SCALPEL-Flattening/branch/master/graph/badge.svg?token=GWYM6JLi0z)](https://codecov.io/gh/X-DataInitiative/SCALPEL-Flattening)
[![License](https://img.shields.io/badge/License-BSD%203--Clause-blue.svg)](https://opensource.org/licenses/BSD-3-Clause)
![Version](https://img.shields.io/github/v/release/X-DataInitiative/SCALPEL-Flattening?include_prereleases)

SCALPEL-Flattening, based on [Apache Spark](https://spark.apache.org/), denormalizes [Système National des Données de Santé (SNDS)](https://www.snds.gouv.fr/SNDS/Accueil) data to accelerate concept extraction when using [SCALPEL-Extraction](https://github.com/X-DataInitiative/SCALPEL-Extraction).
Denormalization consists of several join operations and data compression, resulting in a big table representing SNDS databases, such as DCIR or PMSI. Denormalize3d tables are outputted in [Apache Parquet](https://parquet.apache.org/) or [Apache ORC](https://orc.apache.org/) files.


## SCALPEL-Extraction

[![CircleCI](https://circleci.com/gh/X-DataInitiative/SCALPEL-Extraction.svg?style=shield&circle-token=6dd3a84c5ec9b9d3acac9e1ed156077eeadf9780)](https://circleci.com/gh/X-DataInitiative/SCALPEL-Extraction)
[![codecov](https://codecov.io/gh/X-DataInitiative/SCALPEL-Extraction/branch/master/graph/badge.svg?token=4a0h501t8P)](https://codecov.io/gh/X-DataInitiative/SCALPEL-Extraction)
[![License](https://img.shields.io/badge/License-BSD%203--Clause-blue.svg)](https://opensource.org/licenses/BSD-3-Clause)
![Version](https://img.shields.io/github/v/release/X-DataInitiative/SCALPEL-Extraction?include_prereleases)

SCALPEL-Extraction provides concept extractors meant to fetch meaningful Medical Events & Patients from [Système National des Données de Santé (SNDS)](https://www.snds.gouv.fr/SNDS/Accueil) data.
This library is based on [Apache Spark](https://spark.apache.org/). It reads denormalized data resulting from executing [SCALPEL-Flattening](https://github.com/X-DataInitiative/SCALPEL-Flattening) on raw SNDS data. It then extracts sets of `Patients` with associated `Events` stored as Parquet or ORC files along with their metadata tracking the transformation applied to the input data.


## SCALPEL-Analysis

[![CircleCI](https://circleci.com/gh/X-DataInitiative/SCALPEL-Analysis/tree/master.svg?style=shield&circle-token=77551e927f0d9f66b6c4755743d2cb7f5753395c)](https://circleci.com/gh/X-DataInitiative/SCALPEL-Analysis)
[![codecov](https://codecov.io/gh/X-DataInitiative/SCALPEL-Analysis/branch/master/graph/badge.svg?token=f78o8HzmAl)](https://codecov.io/gh/X-DataInitiative/SCALPEL-Analysis)
[![License](https://img.shields.io/badge/License-BSD%203--Clause-blue.svg)](https://opensource.org/licenses/BSD-3-Clause)
![Version](https://img.shields.io/github/v/release/X-DataInitiative/SCALPEL-Analysis?include_prereleases)

SCALPEL-Analysis is based on [PySpark](https://spark.apache.org/docs/latest/api/python/pyspark.html). It provides useful abstractions easing cohort data analysis and manipulation. While it can be used as a standalone, it expects inputs formatted as the data resulting from SCALPEL-Extraction concept extraction.

## Citation

If you use a library part of _SCALPEL3_ in a scientific publication, we would appreciate citations. You can use the following bibtex entry:

    @article{bacry2020scalpel3,
        title={SCALPEL3: a scalable open-source library for healthcare claims databases},
        author={Bacry, Emmanuel and Gaiffas, St{\'e}phane and Leroy, Fanny and Morel, Maryan and Nguyen, Dinh-Phong and Sebiat, Youcef and Sun, Dian},
        journal={International Journal of Medical Informatics},
        pages={104203},
        year={2020},
        publisher={Elsevier}
    }
