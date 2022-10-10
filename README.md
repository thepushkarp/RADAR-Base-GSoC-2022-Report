<div style="display: flex; flex-direction: row; justify-content: space-between; align-items: center;">
<img src="https://summerofcode.withgoogle.com/assets/media/logo.svg" width="45%">
<div style="font-size:32px;">+</div>
<img src="https://radar-base.org/wp-content/uploads/2018/03/Logo_RADAR-Base-RGB.png" width="45%">
</div>

<h1 align="center">Google Summer of Code 2022 with RADAR-Base: RADAR-Pipeline</h1>

This is a summarization of the work I did for the RADAR-Pipeline project under the RADAR-Base organization as part of Google Summer of Code 2022

## 1. Table of Contents

- [1. Table of Contents](#1-table-of-contents)
- [2. Project Details](#2-project-details)
- [3. Abstract](#3-abstract)
- [4. RADAR-Pipeline](#4-radar-pipeline)
- [5. Project Goals](#5-project-goals)
- [6. Merged Pull Requests](#6-merged-pull-requests)
  - [Before official coding period](#before-official-coding-period)
    - [1. Change yaml to pyYaml and add pysftp in requirements](#1-change-yaml-to-pyyaml-and-add-pysftp-in-requirements)
    - [2. Some minor corrections and typo fixes](#2-some-minor-corrections-and-typo-fixes)
  - [During official coding period](#during-official-coding-period)
    - [1. Add mock data input through pySpark](#1-add-mock-data-input-through-pyspark)
    - [2. Ingestion improvements](#2-ingestion-improvements)
    - [3. Improve features codebase](#3-improve-features-codebase)
    - [4. Add Feature and Data Export Modules](#4-add-feature-and-data-export-modules)
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

The following are the goals that were set for the project at the beginning of the program. ✅ represents that the goal has been achieved. 🚧 represents that the goal is in progress and 📝 represents that the goal is to be done in the future.

-   ✅ Support a larger variety of data into the pipeline, using well-defined schemas
-   🚧 Add reading capability from multiple data sources
-   ✅ Enhance feature analysis of the data
-   📝 Add visualization support to the pipeline
-   ✅ Use software best practices and add comprehensive documentation to make the pipeline more developer-friendly
-   ✅ Add capability to generate and save a statistical report/log of the data processes

Apart from these goals that were set at the beginning of the project, we also added the following features to the project along the way:

-   Support for reading data and features located locally or as a GitHub repository
-   Add mock data and mock features for testing and demonstration purposes
-   Add ability for reading data with or without a predefined schema
-   Add ability to compress data while exporting

## 6. Merged Pull Requests

### Before official coding period

Before the official coding period, when I was setting up the codebase and installing the dependencies, I had to make a few changes to the codebase. These changes were made in the following pull requests:

#### 1. [Change yaml to pyYaml and add pysftp in requirements](https://github.com/RADAR-base/radarpipeline/pull/13)

This was a minor pull request fixing some of the dependency errors that I was facing while setting up the codebase. It also added the `pysftp` dependency which was required for reading data from an SFTP server and changed the `yaml` dependency to `pyYaml` as the former was deprecated.

#### 2. [Some minor corrections and typo fixes](https://github.com/RADAR-base/radarpipeline/pull/14)

This pull request fixed some of the typos and refactored the codebase along with improved error handling for some exceptional cases.

### During official coding period

The following pull requests were made during the coding period:

#### 1. [Add mock data input through pySpark](https://github.com/RADAR-base/radarpipeline/pull/17)

This pull request added the ability to read mock data which could be added as a submodule to the repository. The data, which is in the form of gzipped CSV was ingested using Spark through pyspark. This pull request also added the ability to read a schema file and use it to read the data much more efficiently. Apart from this, the error handling and logging was also improved and the code was refactored to make it more readable and the instructions for running the pipeline was documented. Code formatting and linting was also done to make the codebase consistent.

#### 2. [Ingestion improvements](https://github.com/RADAR-base/radarpipeline/pull/26)

This pull request changed the way data was being read from reading it file by file by passing each filename to the Spark File Reader to reading it in a single pass by passing the directory name to the Spark File Reader. This improved the speed of data ingestion tremendously. Apart from this, the mock data was also checked before running the mock pipeline and if it was not available, then it was downloaded to avoid errors while reading. The codebase was also refactored to remove some datatype inconsistencies and improve the readability of the code.

#### 3. [Improve features codebase](https://github.com/RADAR-base-Analytics/mockfeatures/pull/2)

This pull request was made in the mock features repository. It removed the dependence of the mock features on the pipeline repository by removing it as a submodule and instead, adding it as a dependency in the `requirements.txt` file. This pull request also also fixed some previous calculations to improve the feature processing operations.

#### 4. [Add Feature and Data Export Modules](https://github.com/RADAR-base/radarpipeline/pull/30)

This pull request added the support for processing the features and exporting the computed features from the pipeline to a file. The codebase in this pull request went through a major refactor because of some folder and file reorganization. The codebase and the documentation was also updated to reflect the changes done in the codebase till now.

## 7. Achievements

The major achievements of this project are:

-   The pipeline now supports reading a larger size of data, thanks to Spark's lazy reading capabilities. This along with the ability to read the data irrespective of the data schema being available or not makes the pipeline much more flexible with the kind of data it can handle
-   Making the feature processing work was a major achievement as it was a vital part of the pipeline. The feature processing supports using both Pandas' and Spark's DataFrames, which gives the researcher freedom and flexibility of writing the processing implementation in whichever way they are comfortable with.
-   The pipeline now supports exporting the computed features to a file. This makes the pipeline much more useful as the computed features can be used for further analysis and visualization.
-   Finally, documenting the codebase and the pipeline was also a major achievement as it makes the codebase much more developer-friendly and easier to understand. Also, it makes it easier for new contributors to contribute to the project.

## 8. Open Issues

Through the discussions with the mentors during the course of the project, we identified many new areas of improvement for the pipeline. There are also a few bugs that need to be addressed in the pipeline.

The following are the major issues that were identified an are open that need further work:

-   [Error in Schema reading](https://github.com/RADAR-base/radarpipeline/issues/36)
-   [Add Docker support to the Pipeline](https://github.com/RADAR-base/radarpipeline/issues/34)
-   [Template for new pipeline for researcher](https://github.com/RADAR-base/radarpipeline/issues/39)
-   [Integrate branch option with GitHub repo location](https://github.com/RADAR-base/radarpipeline/issues/31)
-   [Writing test for radar-pipeline](https://github.com/RADAR-base/radarpipeline/issues/9)
-   [Using multiple source data directory during data ingestion](https://github.com/RADAR-base/radarpipeline/issues/42)
-   [Read config.yaml file from the remote repo](https://github.com/RADAR-base/radarpipeline/issues/40)

## 9. Future Work

## 10. Acknowledgements
