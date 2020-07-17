---
description: >-
  A collection of useful code and tools for BioData Catalyst researchers on
  Terra
---

# Code Library for BioData Catalyst

#### Authors: Beth Sheets \(UC Santa Cruz, Genomics Institute\), Brian Hannafious \(UC Santa Cruz, Genomics Institute\)

The [BioData Catalyst Collection workspace](https://terra.biodatacatalyst.nhlbi.nih.gov/#workspaces/biodata-catalyst/BioData%20Catalyst%20Collection) on Terra is a continually evolving and expanding source of example code that demonstrates tools relevant to conducting research in the ecosystem. The examples are primarily written as Python and R Jupyter notebooks.

Below, we highlight relevant tools introduced in the BioData Catalyst Collection. 

## Terra Data Table Tooling

Before using this this tool, we suggest you review the documentation [Getting Started with Gen3 data in Terra](https://support.terra.bio/hc/en-us/articles/360038087312). 

The Jupyter notebook [terra\_data\_table\_util](https://app.terra.bio/#workspaces/biodata-catalyst/BioData%20Catalyst%20Collection/notebooks/launch/terra_data_table_util.ipynb) provides functions that consolidate Gen3 graph-structured data into a single Terra data table. The content of the consolidated table is configurable.

The default behavior is to produce a table keyed by subject id, with one row per subject, for all subjects in a Terra Workspace. This table may include genomic data, harmonized clinical metadata, or both, along with associated administrative information.

Additionally, convenience functions are provided for working with Terra data tables, including uploading, downloading, modification, and deletion.  

This notebook may be a good starting place for many analyses. For example, it is showcased in our [Genome Wide Association Study tutorial](https://terra.biodatacatalyst.nhlbi.nih.gov/#workspaces/biodata-catalyst/BioData%20Catalyst%20GWAS%201000%20Genomes%20Tutorial). 

## Data Repository Service \(DRS\) with Jupyter Notebooks Tooling

Genomic data in BioData Catalyst is accessed through the Data Repository Service \(DRS\). Before using this tooling we suggest you review this [documentation](https://support.terra.bio/hc/en-us/articles/360039330211).

The Python package [terra-notebook-utils](https://github.com/DataBiosphere/terra-notebook-utils) provides tools for accessing genomic data via DRS in Jupyter notebooks or from the Terminal command-line interfaces. It is available in the latest Jupyter notebook default environment on Terra.  

terra-notebook-utils exposes a Python API, as well as wrappers to execute some functionality on the command-line interface. The Python API is best explored with Python's great `help` function. For instance, issuing the following commands into a Python interpreter or Jupyter notebook will produce help and usage for the `DRS` module.

```text
import terra_notebook_utils as tnu
help(tnu.drs)
```

This package can also be deployed in R notebooks using the [Reticulate package](https://rstudio.github.io/reticulate/).

terra-notebook-utils will continue to grow as more popular bioinformatics functions are wrapped into the package so that they are compatible with DRS. For example, the VCF tooling highlighted below can resolve DRS links. 

## VCF Tooling

TOPMed multi-sample VCF files indexed by BioData Catalyst have been jointly-called for each "Freeze", or release of genomic data. These files are accessible in the "Reference File" node of the [Gen3 graph](https://gen3.biodatacatalyst.nhlbi.nih.gov/DD). 

TOPMed researchers not part of the TOPMed Consortium receive jointly-called VCFs subsetted by project and consent code. If users have access to multiple projects and consent codes, they may wish to merge these VCFs to form a synthetic cohort. The [Merge & Subsample VCFs notebook ](https://terra.biodatacatalyst.nhlbi.nih.gov/#workspaces/biodata-catalyst/BioData%20Catalyst%20Collection/notebooks/launch/VCF%20Merge%20and%20Subsample%20Tutorial.ipynb) demonstrates tooling to merge and subsample jointly called VCFs.

Additionally, you may want to first use the [Head VCF notebook](https://terra.biodatacatalyst.nhlbi.nih.gov/#workspaces/biodata-catalyst/BioData%20Catalyst%20Collection/notebooks/launch/head-vcf-gz.ipynb) to learn more about the VCF files you want to combine. 

##  Integrative Genomics Viewer Tool

The [Integrative Genomics Viewer](http://software.broadinstitute.org/software/igv/) is an interactive visualization tool for large genomic files and is available in Terra. [This notebook](https://terra.biodatacatalyst.nhlbi.nih.gov/#workspaces/biodata-catalyst/BioData%20Catalyst%20Collection/notebooks/launch/Prepare%20Gen3%20data%20for%20input%20into%20the%20Integrative%20Genomics%20Viewer%20%28IGV%29%20in%20Terra%20.ipynb) leads you through some data wrangling steps to generate a data table that works with the [IGV tool in Terra](https://support.terra.bio/hc/en-us/articles/360029654831-Viewing-IGV-tracks-of-BAM-files-in-your-workspace-data) using data imported from Gen3.







