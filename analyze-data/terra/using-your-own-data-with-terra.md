---
description: >-
  This page describes how researchers may bring their own data files and
  metadata into Terra.
---

# Using Your Own Data with Terra



Some researchers may choose to bring their own data to Terra in addition to, or instead of, using BioData Catalyst data from Gen3. This may be done for:

* extending or enhancing the data currently available from Gen3. For example:
  * Bringing additional \(e.g., longitudinal\) phenotypic data to enhance the harmonized metadata available from Gen3
  * Joint variant calling with additional researcher provided genomic data
* using researcher provided data exclusively,

At a high-level, there are two types of data that researchers typically bring to Terra. Data files \(e.g., genomic data, including CRAM and VCF data\), and metadata \(e.g., tables of clinical/phenotypic or other data, typically regarding the subjects in their study\). These are described separately below.

### Data Files

There are two ways a researcher's data files may be made available in Terra:

* By uploading data to the researcher's workspace bucket. [**Uploading to a workspace Google bucket**](https://support.terra.bio/hc/en-us/articles/360024056512-Uploading-to-a-workspace-Google-bucket)
* By enabling Terra to access the researcher's data in a researcher managed Google bucket. [**Understanding and setting up a proxy group**](https://support.terra.bio/hc/en-us/articles/360031023592-Understanding-and-setting-up-a-proxy-group)\*\*\*\*

### Metadata

The ways in which a researcher may import metadata to the Terra Data tables are described in these articles.

* [**Managing data with tables**](https://support.terra.bio/hc/en-us/articles/360025758392) ****This article provides an overview of working with data tables in Terra, including instructions for importing data from a local system.
* \*\*\*\*[**How to import metadata to a workspace data table**](https://support.terra.bio/hc/en-us/articles/360036954991-How-to-import-metadata-to-a-workspace-data-table) ****This article briefly describes copying and importing data tables in Terra. It then describes how to use a file containing a list of files as a WDL Array\[File\] workflow configuration parameter.

