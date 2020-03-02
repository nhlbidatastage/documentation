---
description: >-
  How to login to the NHLBI BioData Catalyst Gen3 platform and view available
  genomic and phenotypic data.
---

# Discovering Data Using Gen3

## Login to the BioData Catalyst Gen3 Platform <a id="login-to-nhlbi-biodata-catalyst-gen3"></a>

In order to navigate and access data available on the Gen3 platform, please start by visiting the [login page](https://gen3.biodatacatalyst.nhlbi.nih.gov/login). You will need an eRA Commons account as well as access permissions through the [Database of Genotypes and Phenotypes \(dbGaP\)](https://www.ncbi.nlm.nih.gov/gap/). If you are a researcher, login using your [eRA Commons account](https://public.era.nih.gov/commons/public/login.do). BioData Catalyst consortia developers can login using their Google accounts. Please make sure to use the correct login method that contains access to your available projects.

![Login page for the BioData Catalyst Gen3 portal.](../../.gitbook/assets/image%20%2846%29.png)

Once logged in, your username will appear in the upper right-hand corner of the page. You will also see a display with aggregate statistics for the total number of subjects, studies, aliquots and files available within the BioData Catalyst platform.

> **NOTE**: These numbers may differ from those displayed in the dbGaP records as they include TOPMed studies as well as the associated parent studies.

![Post-login view of the BioData Catalyst Gen3 front page.](../../.gitbook/assets/screenshot_2020-01-17-https-gen3-datastage-io.png)

## Types of Hosted Data <a id="types-of-hosted-data"></a>

### Phenotypic <a id="phenotypic"></a>

#### DCC Harmonized clinical data:  <a id="dcc-harmonized-clinical-data"></a>

A number of clinical variables have been harmonized by the [Data Coordinating Center \(DCC\)](https://www.nhlbiwgs.org/group/dcc) in order to facilitate cross-study analysis. Faceted search over the DCC Harmonized Variables is available via the [Exploration](exploration.md#the-data-tab) page, under the "Data" tab.

#### Unharmonized clinical data:  <a id="unharmonized-clinical-data"></a>

Unharmonized clinical files are also available on the Gen3 platform and contain all of the raw phenotypic information for the hosted studies. Unlike the DCC Harmonized Variables, these files are located and searchable under the "[Files](https://app.gitbook.com/@bdcatalyst/s/biodata-catalyst-documentation/~/diff/drafts/-M-L1HmuSHOOxJmXm-Qv/explore_data/gen3-discovering-data#the-files-tab)" tab in the [Exploration](exploration.md#the-files-tab) page.

### Genomic <a id="genomic"></a>

The Gen3 platform hosts genomic data provided by the [Trans-Omics for Precision Medicine](https://www.nhlbiwgs.org/) \(TOPMed\) program. At present, this includes CRAM and VCF files together with their respective index files. Each TOPMed project will contain at least one multi-sample VCF that comprises all subjects within the consent group. These files are available under the "Files" tab in the [Exploration](exploration.md#the-files-tab) page.

## Gen3 Pages <a id="gen3-pages"></a>

The BioData Catalyst Gen3 platform contains five pages described below:

* \*\*\*\*[**Dictionary**](dictionary.md)**:** An interactive data dictionary display that details the contents and relationships between clinical and biospecimen data.
* \*\*\*\*[**Exploration**](exploration.md)**:** The facet filter custom cohort creation tool
* \*\*\*\*[**Query**](query.md)**:** The GraphQL query tool to retrieve specific data within the graph model
* \*\*\*\*[**Workspace**](workspace.md)**:** The launch page for Gen3 workspaces that includes Jupyter Notebooks and RStudio
* \*\*\*\*[**Profile**](profile.md)**:** The information page for each user, displaying access and the location for credential file downloads

![The BioData Catalyst Gen3 Pages.](https://blobscdn.gitbook.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-LwOmaDlbanAQ-7fhd89%2F-M-PyVfe6nb9uTFTslqZ%2F-M-Pz_BYTNBPIU57B-GK%2Fimage.png?alt=media&token=383d80d2-45e4-4753-a062-47074cd14693)

