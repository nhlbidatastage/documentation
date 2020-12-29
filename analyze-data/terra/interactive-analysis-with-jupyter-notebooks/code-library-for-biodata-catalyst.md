---
description: >-
  A collection of useful code and tools for BioData Catalyst researchers on
  Terra
---

# Code Library for BioData Catalyst

### Authors: Beth Sheets \(UC Santa Cruz, Genomics Institute\), Brian Hannafious \(UC Santa Cruz, Genomics Institute\)

Find example code and tools for conducting research in the BioData Catalyst ecosystem in the [BioData Catalyst Collection workspace](https://terra.biodatacatalyst.nhlbi.nih.gov/#workspaces/biodata-catalyst/BioData%20Catalyst%20Collection). The examples, mostly Python and R notebooks,  are continually evolving and expanding. Scroll down for highlights.

## Manipulating data tables in Terra

Before using, we suggest you review the documentation [Getting Started with Gen3 data in Terra](https://support.terra.bio/hc/en-us/articles/360038087312).

The Jupyter notebook [terra\_data\_table\_util](https://app.terra.bio/#workspaces/biodata-catalyst/BioData%20Catalyst%20Collection/notebooks/launch/terra_data_table_util.ipynb) provides functions that consolidate Gen3 graph-structured data into a single Terra data table, which you can configure following the sample code in the notebook. 

The default output is a consolidated table keyed by subject id, with one row per subject for all subjects in a Terra Workspace. You can configure the table to include genomic data, harmonized clinical metadata, or both, along with associated administrative information.

The notebook also includes convenience functions for uploading, downloading, modifying, and deleting data tables.

This notebook may be a good starting place for many analyses. For example, it is showcased in our [Genome Wide Association Study tutorial](https://terra.biodatacatalyst.nhlbi.nih.gov/#workspaces/biodata-catalyst/BioData%20Catalyst%20GWAS%201000%20Genomes%20Tutorial).

## Genomic data and the Data Repository Service \(DRS\)

To access genomic data in BioData Catalyst, you will use the Data Repository Service \(DRS\). Learn more about DRS in Terra in this [documentation](https://support.terra.bio/hc/en-us/articles/360039330211).

The  Python package [terra-notebook-utils](https://github.com/DataBiosphere/terra-notebook-utils) lets you access genomic data \(via DRS\) in a Jupyter notebook or from the terminal command-line interface. Note that the package is available in the latest Jupyter notebook default environment on Terra.

**Package details:**  [terra-notebook-utils](https://github.com/DataBiosphere/terra-notebook-utils) exposes a Python API, as well as wrappers to execute some functionality on the command-line interface. To understand the Python API, try Python's great `help` function. For instance, issuing the following commands into a Python interpreter or Jupyter notebook will produce help and usage for the `DRS` module.

```text
import terra_notebook_utils as tnu
help(tnu.drs)
```

To use these functions in R notebooks, see the [Reticulate package](https://rstudio.github.io/reticulate/).

**Future functionality:**  [terra-notebook-utils](https://github.com/DataBiosphere/terra-notebook-utils) will continue to grow as we wrap additional popular bioinformatics functions into the package so that they are compatible with DRS. For example, the VCF tooling highlighted below can resolve DRS links.

## VCF Tooling

Each "Freeze", or release, of TOPMed genomic data includes jointly-called, multi-sample VCF files indexed by BioData Catalyst. These files are accessible in the "Reference File" node of the [Gen3 graph](https://gen3.biodatacatalyst.nhlbi.nih.gov/DD).

TOPMed researchers not part of the TOPMed Consortium receive jointly-called VCFs subsetted by project and consent code. If you have access to multiple projects and consent codes, you may wish to merge these VCFs to form a synthetic cohort. The [Merge & Subsample VCFs notebook ](https://terra.biodatacatalyst.nhlbi.nih.gov/#workspaces/biodata-catalyst/BioData%20Catalyst%20Collection/notebooks/launch/VCF%20Merge%20and%20Subsample%20Tutorial.ipynb) demonstrates how to merge and subsample jointly called VCFs.

To learn more about the VCF files you want to combine, reference the [Head VCF notebook](https://terra.biodatacatalyst.nhlbi.nih.gov/#workspaces/biodata-catalyst/BioData%20Catalyst%20Collection/notebooks/launch/head-vcf-gz.ipynb).

## Integrative Genomics Viewer Tool

The [Integrative Genomics Viewer](https://software.broadinstitute.org/software/igv/) is an interactive visualization tool for large genomic files and is available in Terra. [This notebook](https://terra.biodatacatalyst.nhlbi.nih.gov/#workspaces/biodata-catalyst/BioData%20Catalyst%20Collection/notebooks/launch/Prepare%20Gen3%20data%20for%20input%20into%20the%20Integrative%20Genomics%20Viewer%20%28IGV%29%20in%20Terra%20.ipynb) leads you through some data wrangling steps to generate a data table that works with the [IGV tool in Terra](https://support.terra.bio/hc/en-us/articles/360029654831-Viewing-IGV-tracks-of-BAM-files-in-your-workspace-data) using data imported from Gen3.

