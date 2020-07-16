---
description: >-
  A collection of useful code and tools for BioData Catalyst researchers on
  Terra
---

# Code Library for BioData Catalyst

#### Author: Beth Sheets \(UC Santa Cruz, Genomics Institute\)

The [BioData Catalyst Collection](https://app.terra.bio/#workspaces/biodata-catalyst/BioData%20Catalyst%20Collection) workspace on Terra is a continually evolving and expanding source of example code that demonstrates tools relevant to conducting research in the ecosystem. The examples are primarily written as Jupyter notebooks that employ Python or R tooling. 

Some of the early code in the library pertains to how to interact with data.  Interacting with data in BioData Catalyst introduces two new concepts that may take some time to learn: how to work with the [Gen3 graph-based data model](https://support.terra.bio/hc/en-us/articles/360038087312-Understanding-and-using-Gen3-data-in-Terra) and how to access genomic data through the [GA4GH Data Repository Service \(DRS\)](https://support.terra.bio/hc/en-us/articles/360039330211-Data-Access-with-the-GA4GH-Data-Repository-Service-DRS-#h_4a56bae9-f008-4fc8-b81c-f5c595a31e77). 

Below, we highlight relevant tools that are introduced in the BioData Catalyst Collection. 

## Terra Data Table Tooling

The Jupyter notebook [terra\_data\_table\_util](https://app.terra.bio/#workspaces/biodata-catalyst/BioData%20Catalyst%20Collection/notebooks/launch/terra_data_table_util.ipynb) provides functions that consolidate multiple Gen3 graph-structured data tables in Terra to create a single consolidated table that is easier to use. The content of the combined table produced is configurable.

The default behavior is to produce a table keyed by subject id, with one row per subject, for all subjects in a Terra Workspace. This table may include the genomic data, harmonized clinical metadata, or both, along with the associated administrative information.

Additionally, convenience functions are provided for working with Terra data tables, including uploading, downloading, modification and deletion.  

This notebook may be a good starting place for many analyses. For example, it is showcased in our Genome Wide Association Analysis tutorial. 

## Data Repository Service \(DRS\) Tooling

The Python package [terra-notebook-utils](https://github.com/DataBiosphere/terra-notebook-utils) provides tools for accessing genomic data via DRS in Jupyter notebooks or the terminal in Terra. It is available in the latest Jupyter notebook default environment on Terra.  You can learn more about DRS on Terra [here](https://support.terra.bio/hc/en-us/articles/360039330211-Data-Access-with-the-GA4GH-Data-Repository-Service-DRS-#h_4a56bae9-f008-4fc8-b81c-f5c595a31e77). 

terra-notebook-utils exposes a Python API, as well as wrappers to execute some functionality on the command line interface \(CLI\). The Python API is best explored with Pythons great `help` function. For instance, issuing the follow commands into a Python interpreter or Jupyter notebook will produce help and usage for the `drs` module.

```text
import terra_notebook_utils as tnu
help(tnu.drs)
```

terra-notebook-utils will continue to grow as more popular bioinformatics functions are wrapped into the package so that they are compatible with DRS. For example, the VCF tooling highlighted below can resolve DRS links. 

## VCF Tooling

TopMED multi-sample VCF files indexed by BioData Catalyst have been jointly called for each "Freeze", or release of genomic data. These files are accessible in the "Reference File" node of the [Gen3 graph](https://gen3.biodatacatalyst.nhlbi.nih.gov/DD). 

TOPMed researchers not part of the TOPMed Consortium receive jointly called VCFs subsetted by project and consent code. If users have access to multiple projects and consent codes, they may wish to merge these VCFs to form a synthetic cohort. The [Merge & Subsample VCFs notebook ](https://terra.biodatacatalyst.nhlbi.nih.gov/#workspaces/biodata-catalyst/BioData%20Catalyst%20Collection/notebooks/launch/VCF%20Merge%20and%20Subsample%20Tutorial.ipynb)demonstrates tooling to merge and subsample jointly called VCFs.

Additionally, you may want to first use the [Head VCF notebook](https://terra.biodatacatalyst.nhlbi.nih.gov/#workspaces/biodata-catalyst/BioData%20Catalyst%20Collection/notebooks/launch/head-vcf-gz.ipynb) to learn more about the VCF files you want to combine. 

##  Integrative Genomics Viewer Tool

The [Integrative Genomics Viewer](http://software.broadinstitute.org/software/igv/) is an interactive visualization tool for large genomic files and is available in Terra. [This notebook](https://terra.biodatacatalyst.nhlbi.nih.gov/#workspaces/biodata-catalyst/BioData%20Catalyst%20Collection/notebooks/launch/Prepare%20Gen3%20data%20for%20input%20into%20the%20Integrative%20Genomics%20Viewer%20%28IGV%29%20in%20Terra%20.ipynb) leads you through some data wrangling steps to generate a data table that works with the [IGV tool in Terra](https://support.terra.bio/hc/en-us/articles/360029654831-Viewing-IGV-tracks-of-BAM-files-in-your-workspace-data) using data imported from Gen3.







