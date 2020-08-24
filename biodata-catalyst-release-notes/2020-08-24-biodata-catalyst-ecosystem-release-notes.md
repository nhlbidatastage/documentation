# 2020-08-24 BioData Catalyst Ecosystem Release Notes

### Introduction

The 2020-08-24 release marks the second release for the NHLBI BioData Catalyst ecosystem. This release includes several new features along with documentation and tutorials \(e.g. genome-wide association studies\) to help new users get started on the system. This release also includes enhanced support for machine learning in the workspace environments and support for GA4GH industry standard in Dockstore for workflows. Please find more detail on the new features and user support materials in the sections below.

The 2020-08-24 data release includes the addition of TOPMed Freeze 8 data for a subset of studies on BioData Catalyst. Freeze8 multi-sample VCFs are available for 29 studies, of which 10 studies are new to the ecosystem. For each study and consent group, VCF files are available on a per chromosome basis and in an un-tarred format, in contrast to the Freeze5 multi-sample VCFs which are hosted as tar bundles. For the 10 studies new to BioData Catalyst, CRAM files and unharmonized clinical files are also available for access. The data release further includes updates of many studies to the latest versions that are available on dbGaP. The next data release will include Freeze8 multi-sample VCFs for additional TOPMed studies in addition to unharmonized clinical data and CRAM files for studies that are not yet hosted on the system. Please refer to the Data Release section below for more information as well as the[ Data page](https://biodatacatalyst.nhlbi.nih.gov/resources/data) on the BioData Catalyst website.

### Significant new features

* **GENESIS tutorial and public project:** Seven Bridges has made a public project available that introduces users to the GENESIS R package and related R packages \(SeqArray, SeqVarTools, and SNPRelate\) used in mixed model association testing in sequence data. The examples in the project help users understand the code that is used in the GENESIS public apps \([available on GitHub](https://uw-gac.github.io/SISG_2020/)\), prepare data for input to those apps, and interact with the results. The “GENESIS Tutorial” public project can be found in the list of Seven Bridges public projects on the top navigation bar of the platform.  
* **Launch machine learning packages in Jupyterlab Notebooks:** Users on Seven Bridges can now use a docker image with[ pre-installed libraries](https://sb-biodatacatalyst.readme.io/v1.0/docs/about-libraries-in-a-data-cruncher-analysis) that support machine learning analyses when working in Jupyterlab Notebooks. This docker image can be found in the Data Cruncher feature: Select “Create new analysis” and then, under the Environment setup menu, select “SB Machine Learning - TensorFlow 2.0, Python 3.7.” 
* **Support for larger GPU instances:** A larger[ AWS GPU instance type](https://aws.amazon.com/ec2/instance-types/p3/) is now available for researchers working in Jupyterlab Notebooks and RStudio on Seven Bridges. The p3dn.24xlarge instance has 1800GB SSD, 96vCPUs, 768GB RAM, and 8 GPUs. These higher memory cards enable machine learning training on large 3D images and high-performance computing applications. 
* **Data Cruncher Interactive Analyses:** Seven Bridges now features a “[Data Cruncher Interactive Analyses](https://sb-biodatacatalyst.readme.io/docs/data-cruncher-interactive-analyses)” public project, found in the list of public projects on the top navigation bar of the platform, with example analyses to help users interpret results from secondary analysis. The project has eight separate analyses - three in RStudio and five in Jupyterlab Notebooks - including one on VCF visualization and one on structural variant analysis. Read the [blog post](https://www.sevenbridges.com/blog-data-cruncher-interactive-analysis/). 
* **Launch Dockstore workflows in Seven Bridges:** Users can now find CWL workflows in Dockstore and launch them in the Seven Bridges workspace environment. 
* **Export large PFBs from Gen3 to Terra:** Users can now export large PFB \(Portable Format for Bioinformatics\) files from Gen3 \(e.g. synthetic cohort files from multiple groups\) to Terra. New backend systems now automatically parse files more efficiently. 
* **Automatic syncing with GitHub apps:** Dockstore now[ automatically updates your workflows](https://docs.dockstore.org/en/develop/getting-started/github-apps/github-apps.html) with any changes you make to your linked GitHub repository. 
* **Link ORCID iDs to published workflows:** Users can now link their[ ORCID iDs](https://orcid.org/) to their Dockstore accounts, and make iDs visible via their organizations, and in workflows and tools they have starred. Users searching Dockstore’s catalog will be able to associate workflows you contribute with scientific publications. 
* **GA4GH TRS Support:** Dockstore now implements the [GA4GH Tool Registry Service](https://github.com/ga4gh/tool-registry-service-schemas) \(TRS\) v2 standard. The goal of the TRS API is to provide a standardized way to describe the availability of tools and workflows. 
* **Transfer datasets to Jupyter Notebooks with Query Id:** Users that query the PIC-SURE UI and apply filters to create datasets can submit their query ID to the PIC-SURE client library via an R or Python[ Jupyter Notebook](https://github.com/hms-dbmi/Access-to-Data-using-PIC-SURE-API/tree/master/NHLBI_BioData_Catalyst) and do not need to re-build the query manually. 
* **Data Tree Optimizations:** The PIC-SURE data tree has been optimized to show users only the studies they have been authorized to see and rendered more efficiently to allow users to select studies faster. 
* **Export data dictionary of clinical variables:**[ ****R and Python Jupyter Notebooks](https://github.com/hms-dbmi/Access-to-Data-using-PIC-SURE-API/tree/master/NHLBI_BioData_Catalyst) are now available that provide directions on exporting the full data dictionary of all clinical variables to a CSV via PIC-SURE.

### New user support materials and documentation

* **Overview of the ecosystem:** This collaboratively developed [overview document](https://bdcatalyst.gitbook.io/biodata-catalyst-documentation/) guides new users through the process of understanding what the BioData Catalyst is to getting started using the ecosystem. 
* **Tips for reliable and efficient analysis set-up:**[ ****This guide](https://sb-biodatacatalyst.readme.io/page/comprehensive-tips-for-reliable-and-efficient-analysis-set-up) provides recommendations on how to set up your initial set of analyses, tips for running tools/workflows, and specifications for computational resources on Seven Bridges. 
* **Genetic Association Testing Using GENESIS Workflows:**[ ****This tutorial](https://bdcatalyst.gitbook.io/biodata-catalyst-tutorials/tutorials/seven-bridges-tutorials) guides users through the steps of running a single variant or multiple variant association test on Seven Bridges using the GENESIS R package pipelines. 
* **Troubleshooting Tasks:**[ ****This guide](https://bdcatalyst.gitbook.io/biodata-catalyst-documentation/analyze-data/seven-bridges/troubleshooting-tasks) presents some of the most common errors in task execution on Seven Bridges and shows you how to debug and resolve them. 
* **GWAS tutorial and example cloud costs:** Terra’s [GWAS tutorial](https://bdcatalyst.gitbook.io/biodata-catalyst-documentation/analyze-data/terra/performing-genome-wide-association-study-gwas-analysis-in-terra) walks users through the steps of preparing data for input via Hail workflows and running association tests as workflows with the GENESIS R package and provides example cloud costs derived from the tutorial. 
* **Code Library:** This release includes a Terra[ featured workspace](https://bdcatalyst.gitbook.io/biodata-catalyst-documentation/analyze-data/terra/interactive-analysis-with-jupyter-notebooks/code-library-for-biodata-catalyst) containing R and Python Jupyter Notebooks that cover how to use the Integrated Genomics Viewer with data from Gen3, workflows for merging VCF files, and expanded features for interacting with data using the Data Repository Service \(DRS\) such as bulk downloads.  
* **Dockstore Fundamentals:** A[ video recording, slides, and exercises](https://github.com/dockstore/bcc2020-training) are available from the recent workshop Dockstore Fundamentals: Introduction to Docker and Descriptors for Reproducible Analysis. 
* **API and User Interface Technical Documentation:**[ ****PIC-SURE technical documentation](https://bdcatalyst.gitbook.io/biodata-catalyst-documentation/explore_data/pic-sure-for-biodata-catalyst-user-guide/pic-sure-api-documentation)  provides users with information about the PIC-SURE API and user interface and examples of how to load data into the PIC-SURE High Performance Data Store. 
* **Scalability and cost-effectiveness analysis of whole genome-wide association studies in the Cloud:**[ This recent article](https://academic.oup.com/jamia/advance-article/doi/10.1093/jamia/ocaa068/5876972) from PIC-SURE provides a straightforward and innovative methodology to optimize cloud configuration in order to conduct genome-wide association studies and helps users understand the trade-off between speed and cost.

### Data Release

The table below highlights which TOPMed studies were included in the 2020-08-24 data release. Freeze 8 multi-sample VCFs were added for the 29 studies listed in the table below. This includes 19 studies which were previously hosted on BioData Catalyst with Freeze 5b data available and 10 studies which are new to BioData Catalyst. For each study and consent group, VCF files are available on a per chromosome basis and in an un-tarred format. For the 10 studies which are new to BioData Catalyst, CRAM files and unharmonized clinical files are also available for access. Additionally, 10 of these studies were updated to the latest version. The data is now available for access across the entire ecosystem. 

| **Study Name** | **phs I.D. \#** | **Acronym** | **New to BioData Catalyst** | **New study version** |
| :--- | :--- | :--- | :--- | :--- |
| NHLBI TOPMed: Genetics of Cardiometabolic Health in the Amish | phs000956 | Amish | - | Yes |
| NHLBI TOPMed: Atherosclerosis Risk in Communities | phs001211 | ARIC | - | - |
| NHLBI TOPMed: NHGRI CCDG: The BioMe Biobank at Mount Sinai | phs001644 | BioMe | Yes | - |
| NHLBI TOPMed: Childhood Asthma Management Program | phs001726 | CAMP | Yes | - |
| NHLBI TOPMed: Coronary Artery Risk Development in Young Adults | phs001612 | CARDIA | Yes | - |
| NHLBI TOPMed: Cleveland Clinic Atrial Fibrillation | phs001189 | CCAF | - | Yes |
| NHLBI TOPMed: The Cleveland Family Study | phs000954 | CFS | - | Yes |
| NHLBI TOPMed: Cardiovascular Health Study | phs001368 | CHS | - | - |
| NHLBI TOPMed: Framingham Heart Study | phs000974 | FHS | - | - |
| NHLBI TOPMed: Genetic Study of Atherosclerosis Risk | phs001218 | GeneSTAR | - | Yes |
| NHLBI TOPMed: Epigenetic Determinants of Lipid Response to Dietary Fat and Fenofibrate | phs001359 | GOLDN | - | Yes |
| NHLBI TOPMed: The Hispanic Community Health Study/Study of Latinos | phs001395 | HCHS/SOL | Yes | - |
| NHLBI TOPMed: The Heart and Vascular Health Study | phs000993 | HVH | - | - |
| NHLBI TOPMed: Genetics of Left Ventricular Hypertrophy | phs001293 | HyperGEN | - | Yes |
| NHLBI TOPMed: The Jackson Heart Study | phs000964 | JHS | - | - |
| NHLBI TOPMed: NHGRI CCDG: The Johns Hopkins University School of Medicine Atrial Fibrillation Genetics Study | phs001598 | JHU\_AF | Yes | - |
| NHLBI TOPMed: The Multi-Ethnic Study of Atherosclerosis | phs001416 | MESA | - | - |
| NHLBI TOPMed: Plasma microRNAs are associated with atrial fibrillation and change after catheter ablation | phs001434 | miRhythm | Yes | - |
| NHLBI TOPMed: Partners HealthCare Biobank | phs001024 | PARTNERS | - | Yes |
| NHLBI TOPMed: Pulmonary Hypertension and the Hypoxic Response in Sickle Cell Disease | phs001682 | PUSH\_SCD | Yes | - |
| NHLBI TOPMed: Recipient Epidemiology and Donor Evaluation Study-III Brazil Sickle Cell Disease Cohort | phs001468 | REDS-III\_Brazil\_SCD | Yes | - |
| NHLBI TOPMed: San Antonio Family Heart Study | phs001215 | SAFHS | - | Yes |
| NHLBI TOPMed: Severe Asthma Research Program | phs001446 | SARP | Yes | - |
| NHLBI TOPMed: Genome-wide Association Study of Adiposity in Samoans | phs000972 | SAS | - | - |
| NHLBI TOPMed: The Vanderbilt Atrial Fibrillation Ablation Registry | phs000997 | VAFAR | - | Yes |
| NHLBI TOPMed: Venous Thromboembolism project | phs001402 | VTE | - | - |
| NHLBI TOPMed: The Vanderbilt Atrial Fibrillation Registry | phs001032 | VU\_AF | - | Yes |
| NHLBI TOPMed: Walk-PHaSST Sickle Cell Disease | phs001514 | Walk\_PHaSST\_SCD | Yes | - |
| NHLBI TOPMed: Women's Health Initiative | phs001237 | WHI | - | - |

#### For detailed platform release notes please consult the following resources:

* Gen3 release notes
* [Terra release notes](https://support.terra.bio/hc/en-us/categories/360000693572)
* [Seven Bridges release notes](https://sb-biodatacatalyst.readme.io/blog)
* PIC-SURE release notes
* [Dockstore release notes](https://docs.dockstore.org/en/develop/changelog.html)

