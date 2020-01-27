---
description: >-
  How to login to the NHLBI BioData Catalyst Gen3 website and view available
  genomic and phenotypic data.
---

# Discovering Data Using Gen3

## Login to NHLBI BioData Catalyst Gen3

In order to navigate and access data available on the Gen3 platform, please start by visiting the login page. You will need an eRA Commons account as well as access permissions through the [Database of Genotypes and Phenotypes \(dbGaP\)](https://www.ncbi.nlm.nih.gov/gap/). If you are a researcher, please login using your [eRA Commons account](https://public.era.nih.gov/commons/public/login.do). BioData Catalyst consortia developers can login using their Google accounts.  Please make sure to use the correct login method that contains access to your available projects.

![Login page for the Gen3 portal.](../.gitbook/assets/image%20%2813%29.png)

Once logged in, your username will appear in the upper right-hand corner of the page. You will also see a display with aggregate statistics for the total number of subjects, studies, aliquots and files  available within the BioData Catalyst platform. 

> **NOTE**: These numbers may differ from those displayed in the dbGaP records as the structure of these projects has been broken up between TOPMed and Parent studies plus the consent groups within studies.

![Post login view of the Gen3 front page.](../.gitbook/assets/screenshot_2020-01-17-https-gen3-datastage-io.png)

## Types of Hosted Data

### Phenotypic: 

#### DCC Harmonized clinical data: 

A number of clinical variables have been harmonized by the [Data Coordinating Center \(DCC\)](https://www.nhlbiwgs.org/group/dcc) in order to facilitate cross-study analysis. Faceted search over the DCC Harmonized Variables is available via the [Exploration](https://gen3.datastage.io/explorer) page, under the "Data" tab.

#### Unharmonized clinical data: 

Unharmonized clinical files contain all of the raw phenotypic information available for the hosted studies. Unlike the DCC Harmonized Variables, these files are available under the "Files" tab in the [Exploration](https://gen3.datastage.io/explorer) page. 

### Genomic:

## Using Exploration

The Exploration tab located in the upper right-hand section of the toolbar allows users to search through data and create cohorts. The Exploration portal contains a dynamic summary statistics display, as well as search facets leveraging the DCC Harmonized Variables.

### Data Accessibility

![Data access panel in the Exploration page. ](../.gitbook/assets/image%20%2812%29.png)

Users can navigate through data in the Exploration page by selecting any of the three Data Access categories: 

* `Data with Access`: A user can view all of the summary data and associated study information including but not limited to Project ID, file types, and clinical variables, amongst others.
* `Data without Access`: Users can still search through the available studies but only view summary statistics. Summary information will also be hidden if the select cohort contains fewer than 50 subjects \(example below\). Users can request access to data by visiting the [dbGaP homepage](https://dbgap.ncbi.nlm.nih.gov/). 

![Example: The variable of Race is hidden once the number of subjects falls below 50.](../.gitbook/assets/image%20%2816%29.png)

* `All Data`: Users can view all of the data available in the BioData Catalyst Gen3 platform, including studies with and without access. As a result, studies not available to a user will be locked as demonstrated below.

![](https://blobscdn.gitbook.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-LwOmaDlbanAQ-7fhd89%2F-Lyjh7yZAx0phhN3j_yk%2F-LyjiMBhmdrRF1BFFoZe%2Fimage.png?alt=media&token=c09ee728-403c-407a-9991-0ba9078fe614)

By default, all users visiting the Exploration page will be assigned to `Data with Access`.

### Data Tab

![Place holder, please remove before Go Live.](../.gitbook/assets/image%20%289%29.png)

Under the "Data" tab, users can leverage the [DCC harmonized variables](https://chs-nhlbi.org/sites/chs-nhlbi.org/files/page/Stilp_topmed_pheno_harmonization_ccc_portland_2017-03-11.pdf) to create custom cohorts. When facets are selected and/or updated to cover a desired range of values, the display will reflect the information relevant to the new applied filter. If no facets have been selected, all of the data accessible to the user will be displayed. At this time, a user can filter based on three categories of clinical information:

* `Medical History`: Standard questionnaire used to collect medical records from patients.
* `Diagnosis`: Data from the investigation, analysis and recognition of the presence and nature of disease, condition, or injury from expressed signs and symptoms; also, the scientific determination of any kind; the concise results of such an investigation
* `Subject`: The collection of all data related to a specific subject in the context of a specific experiment 

> **NOTE**: The facet filters are exclusive to the DCC harmonized variables submitted within the BioData Catalyst Gen3 Data Dictionary. This means for TOPMed studies that do not contain these harmonized clinical data, they will be filtered out of the cohort when selecting one of these facets.

### Exporting and Downloading Data

When a cohort has been selected, the user will have the option of exporting or downloading the data.

#### Export

The options for export are as follows:

![Three options offered for data export.](../.gitbook/assets/image%20%282%29.png)

* `Export All to Terra` :  This button will initiate a [PFB](https://github.com/uc-cdis/pypfb) export of all clinical data and file GUIDs for the selected cohort to the Terra system.
* `Export to PFB` : This button will initiate a [PFB](https://github.com/uc-cdis/pypfb) export of all clinical data and file GUIDs for the selected cohort to your local machine.
* `Export to Workspaces` : This button will initiate a manifest export to the user's workspace and make the cases associated data files available in the workspace under the `/data` directory.

#### Download

The `Download`drop-down menu will display two options:

![The download drop-down menu.](../.gitbook/assets/image%20%281%29.png)

* `Download All Clinical` : Download files with selected clinical data in a `JSON` formatted file.
* `Download Manifest` : Download a list of Global Unique Identifiers \(GUIDs\) for use with the [gen3-client](https://gen3.org/resources/user/gen3-client/).

### Files Tab

![The Files Tab page.](../.gitbook/assets/image%20%284%29.png)

The Files tab displays study files from the facets chosen on the left-side panel \(Project ID, Data Type, and Data Format\). Each time a facet selection is made, the data summary and displays will update to reflect the applied filters.

#### Unharmonized clinical data

The Files tab also contains files that are either case-independent or project-level. This is important for files that are part of the `Unharmonized Clinical Data` category under the Data Type field. Unharmonized clinical files are made available in two distinct data formats: 

* `TAR` : Contain a directory of TSV files that are direct downloads of unharmonized clinical data from dbGaP
* `AVRO`: These files are the same as the unharmonized clinical data from dbGaP, but in a Portable Format for Bioinformatics \(PFB\)

> **NOTE**: The harmonized clinical data comes from the [Data Coordinating Center \(DCC\)](https://www.nhlbiwgs.org/group/dcc) and is a hand selected subset of the data from dbGaP that has been reprocessed for compatibility across all studies. The unharmonized clinical data contains all data from the dbGaP study, but it is not cross compatible between all projects.

On the Files tab, once a group of files have been filtered for, a user can choose to either download a manifest of the files to use with the [gen3-client](https://gen3.org/resources/user/gen3-client/), export the files to a gen3 workspace, or view the file page by clicking the link in the file table under the GUID column.

### File Page

![An example File page.](../.gitbook/assets/image%20%286%29.png)

A File page will display the details about a file, such as the data format, size, object\_id, the last time it was updated and the md5sum. The page also contains a download button to download the single file via the browser. For files that are 5Gb or more, we suggest using the [gen3-client](https://gen3.org/resources/user/gen3-client/) to download the file.

