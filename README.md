<div style="display: flex; flex-direction: row; justify-content: space-between; align-items: center;">
<img src="https://summerofcode.withgoogle.com/assets/media/logo.svg" width="45%">
<div style="font-size:32px;">+</div>
<img src="https://radar-base.org/wp-content/uploads/2018/03/Logo_RADAR-Base-RGB.png" width="45%">
</div>

<h1 align="center">Google Summer of Code 2022 with RADAR-Base: RADAR-Pipeline</h1>

<div align="center">
This is a summarization of the work I did for the RADAR-Pipeline project under the RADAR-Base organization as part of Google Summer of Code 2022
</div>

## 1. Table of Contents

- [1. Table of Contents](#1-table-of-contents)
- [2. Project Details](#2-project-details)
- [3. Abstract](#3-abstract)
- [4. RADAR-Pipeline](#4-radar-pipeline)
- [5. Project Goals](#5-project-goals)
- [6. Merged Pull Requests](#6-merged-pull-requests)
- [7. Achievements](#7-achievements)
- [8. Open Issues](#8-open-issues)
- [9. Future Work](#9-future-work)
- [10. Acknowledgements](#10-acknowledgements)

## 2. Project Details

-   Title: Enhancing the RADAR-Feature Pipeline
-   Organization: [RADAR-Base](https://github.com/RADAR-base)
-   Repositories: [RADAR-Pipeline](https://github.com/RADAR-base/radarpipeline), [Mock Features](https://github.com/RADAR-base-Analytics/mockfeatures)
-   Mentors:
    -   Amos Folarin
    -   Heet Sankesara
    -   Shaoxiong Sun
-   Contributor:
    -   Name: Pushkar Patel
    -   GitHub: [thepushkarp](https://github.com/thepushkarp)

## 3. Abstract

This project enhances the RADAR-Pipeline by adding support for ingesting the data, computing features from this data and then finally exporting these computed features to a file. All of these steps can be configured by a user or a researcher through YAML syntaxes specified in a single `config` file.

The ingestion of data is done by using Apache Spark through pyspark. This ingested data is internally represented as a DataFrame, which makes performing operations on the columns to extract features easier. The extracted features from this DataFrame are then exported to a file.

## 4. RADAR-Pipeline

RADAR Pipeline is an open-source python package to help researchers and users working with RADAR data to ingest, analyze, visualize, and export their data, all from a single place. The package is designed to be flexible and extensible. The pipeline aims to:

-   Allow researchers to create and publish their own custom pipelines to analyze and visualize their data in a reproducible and extensible way.
-   Allow users to consume and run published pipelines and run their own analysis on their data.

## 5. Project Goals

## 6. Merged Pull Requests

## 7. Achievements

## 8. Open Issues

## 9. Future Work

## 10. Acknowledgements
