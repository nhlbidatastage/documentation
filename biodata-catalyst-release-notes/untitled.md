# 2020-10-23 BioData Catalyst Ecosystem Release Notes

## **Introduction**

The 2020-10-23 release marks the third release for the NHLBI BioData Catalyst ecosystem. This release includes several new features along with documentation and tutorials \(e.g., bringing your own data and tools\) to help new users get started on the system. This release also includes enhanced support for querying annotations for TOPMed Freeze 8 variants in the Annotation Explorer, and querying combined phenotypic and genomic data in PIC-SURE. Please find more detail on the new features and user support materials in the sections below.

The 2020-10-23 data release includes the addition of both Parent and TOPMed studies. A total of 8 new Parent studies and their respective unharmonized clinical files were added. Multi-sample VCFs, CRAMs and unharmonized clinical files were added for 2 TOPMed studies new to BioData Catalyst. Additionally, 6 studies were updated to the latest version. These updates included new CRAMs, unharmonized clinical files and multi-sample VCFs for Freeze 8. For each study and consent group, VCF files are available on a per chromosome basis and in an un-tarred format. The data is now available for access across the entire ecosystem. Please refer to the Data Release section below for more information as well as the [Data page](https://biodatacatalyst.nhlbi.nih.gov/resources/data) on the BioData Catalyst website.

## **Significant new features**

* **Form cohorts on Gen3 Exploration page and export to Seven Bridges workspace:** Users can now export PFB \(Portable Format for Bioinformatics\) files from Gen3 \(e.g., synthetic cohort files from multiple groups\) to Seven Bridges. 
* **CWL workflows for EPACTS and Plink association tests:** Users can now find CWL workflows in the Seven Bridges Public Apps Gallery for the association test methods EPACTS and Plink. More information can be found in [this blog post](https://www.sevenbridges.com/single-and-multiple-variant-association-testing-on-seven-bridges/). 
* **Query annotations for TOPMed Freeze 8 variants in the Annotation Explorer:** Users on Seven Bridges can now use the Annotation Explorer to interactively aggregate and filter ~1 billion variants from TOPMed Freeze 8 using 450 annotations. Variant grouping files can be created from the results and exported to a workspace for use in rare variant association testing. Users with dbGaP approval for one or more TOPMed studies are able to access and work with the full Freeze 8 variant annotation database. 
* **Query open access variant annotations in Annotation Explorer:** Users on Seven Bridges without dbGaP approval for any TOPMed studies can now make use of the Annotation Explorer and interactively query TOPMed variants from Freeze 5 that have been released in dbSNP, a public-domain archive for human variants. Users can aggregate and filter ~550 million variants using ~260 annotations available in this dataset and generate variant grouping files for rare variant association testing. 
* **Query combined phenotypic and genomic data in PIC-SURE:** A release of genomic data in PIC-SURE now allows users to perform combined phenotypic and genomic queries to see phenotypic/genomic correlations. Users can export queries/cohorts to Seven Bridges or Terra Workspaces using the PIC-SURE API.

## **New user support materials and documentation**

* [**Bring Your Own Tools to BioData Catalyst**](https://app.gitbook.com/@bdcatalyst/s/biodata-catalyst-documentation/community-tools-and-integration/bring-your-own-tool-s-to-biodata-catalyst): This guide introduces users to the two Docker-based workflow languages used to run batch analyses in the ecosystem: the Workflow Description Language \(WDL\) in Terra and the Common Workflow Language \(CWL\) in Seven Bridges. The guide links to resources that lead users from the early steps of learning to wrap their current pipelines for use in the cloud to how to publish their work in our open access catalog Dockstore to share with the community. This guide was originally conceived in discussion with fellows during the BDCatalyst September Face-to-Face. Fellows developed content and provided feedback and are listed as contributors within the publication. 
* **Benchmarking guide for GENESIS association test workflows:** This guide provides users with comprehensive benchmarking information for the CWL versions of the GENESIS association workflows. This guide shows the computation costs and execution times for a variety of association tests using 2.5K samples, 10K samples, 36K samples, and 50K samples run on both AWS and Google Cloud. The benchmarking guide can be found on the page “[GWAS with GENESIS](https://bdcatalyst.gitbook.io/biodata-catalyst-documentation/analyze-data/seven-bridges/gwas-page-placeholder)” of the Seven Bridges documentation. 
* [**Bring Your Own Data to Terra Tutorial**](https://app.terra.bio/#workspaces/biodata-catalyst/BioData%20Catalyst%20Collection/notebooks/launch/Bring%20Your%20Own%20Data%20Tutorial.ipynb): We published a Jupyter notebook that provides functions for users to programmatically upload data to their Terra Google bucket and organize associated data into data tables for input into workflows. This may be a helpful resource for users that plan to upload many files. This notebook is part of a growing code library available in the [BioData Catalyst Collection workspace](https://app.terra.bio/#workspaces/biodata-catalyst/BioData%20Catalyst%20Collection). 
* **Utilities Workflows on Dockstore**: The BioData Catalyst Organization on Dockstore now has a [Utilities collection](https://dockstore.org/organizations/bdcatalyst/collections/Utilities) with workflows for completing common tasks such as data import, genotype file processing, and quality control of whole genome or exome sequencing data. Fellow Kenny Westermann developed a workflow that fetches data from dbGaP for use in BDCatalyst.

## **Data Release**

The table below highlights the new data release on BioData Catalyst which includes both Parent and TOPMed studies. A total of 8 new Parent studies and their respective unharmonized clinical files were added to the ecosystem. Multi-sample VCFs, CRAMs and unharmonized clinical files were added for 2 TOPMed studies new to BioData Catalyst. Additionally, 6 TOPMed studies previously hosted on BioData Catalyst were updated to the latest study versions. These updates included new CRAMs, unharmonized clinical files and multi-sample VCFs for Freeze 8 \(previously hosted Freeze 5b only\). For each study and consent group, VCF files are available on a per chromosome basis and in an un-tarred format. The data is now available for access across the entire ecosystem.

| **Study Name** | **phs I.D. \#** | **Acronym** | **New to BioData Catalyst** | **New study version** |
| :--- | :--- | :--- | :--- | :--- |
| NHLBI GO-ESP: Lung Cohorts Exome Sequencing Project \(Asthma\) | phs000422 | Asthma | Yes |  |
| CATHeterization GENetics \(CATHGEN\) | phs000703 | CATHGEN | Yes |  |
| NHLBI TOPMed: Genetic Epidemiology of COPD \(COPDGene\) | phs000951 | COPDGene |  | Yes |
| The Diabetes Heart Study \(DHS\) | phs001012 | DHS | Yes |  |
| Evaluation of COPD Longitudinally to Identify Predictive Surrogate Endpoints \(ECLIPSE\) | phs001252 | ECLIPSE | Yes |  |
| NHLBI TOPMed: Evaluation of COPD Longitudinally to Identify Predictive Surrogate Endpoints \(ECLIPSE\) | phs001472 | ECLIPSE | Yes |  |
| NHLBI TOPMed: Boston Early-Onset COPD Study in the TOPMed Program | phs000946 | EOCOPD |  | Yes |
| NHLBI TOPMed - NHGRI CCDG: Genes-Environments and Admixture in Latino Asthmatics \(GALA II\) | phs000920 | GALAII |  | Yes |
| NHLBI TOPMed: Genetic Epidemiology Network of Arteriopathy \(GENOA\) | phs001345 | GENOA |  | Yes |
| NHLBI TOPMed: Genetic Epidemiology Network of Salt Sensitivity \(GenSalt\) | phs001217 | GenSalt |  | Yes |
| Hispanic Community Health Study /Study of Latinos \(HCHS/SOL\) | phs000810 | HCHS-SOL | Yes |  |
| Pediatric Cardiac Genomics Consortium \(PCGC\) Study | phs001194 | PCGC | Yes |  |
| NHLBI TOPMed: PCGC's Congenital Heart Disease Biobank | phs001735 | PCGC\_CHD | Yes |  |
| PGRN-RIKEN: Rate Control Therapy in Patients with Atrial Fibrillation | phs000439 | PGRN-RIKEN\_AF | Yes |  |
| NHLBI TOPMed: Study of African Americans, Asthma, Genes and Environment \(SAGE\) | phs000921 | SAGE |  | Yes |
| SNP Health Association Resource \(SHARe\) Asthma Resource Project \(SHARP\) | phs000166 | SHARP | Yes |  |

### **For detailed platform release notes please consult the following resources:**

* Gen3 release notes
* [Terra release notes](https://support.terra.bio/hc/en-us/categories/360000693572)
* [Seven Bridges release notes](https://sb-biodatacatalyst.readme.io/blog)
* PIC-SURE release notes
* [Dockstore release notes](https://docs.dockstore.org/en/develop/changelog.html)

