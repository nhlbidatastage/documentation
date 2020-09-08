---
description: >-
  Overview of Parent and TOPMed studies hosted on the BioData Catalyst Gen3
  platform
---

# Parent and TOPMed Studies

## Distinguishing Between Parent and TOPMed Studies

The Parent and TOPMed study types have been categorized on Gen3 by their Program designation. An example of this designation by Program is presented below.

![A list of Parent \(underlined in blue\) and TOPMed studies \(underlined in red\)](../../.gitbook/assets/parent_topmed_studies2.png)

The Program types can be further identified by the `_` \(underscore\) at the end of all Parent studies. TOPMed studies will not include an underscore `_` at the end of the study name.

## Parent and TOPMed Study Contents

The most notable difference between both Program categories is the type of hosted data.

###  **Programs:**

* **Parent**
  * _Genomic data_: None, but see note below about what happens when there is a Parent study and a TOPMed study.
  * _Phenotypic data_: Like with TOPMed studies, any phenotypic data found within the Graph Model, will only be DCC harmonized variables. For the raw phenotypic data from dbGaP, again, it can be found in the `reference_file` node in the tar files that share this common naming scheme: `RootStudyConsentSet_phs######.<study_shorthand>.v#.p#.c#.<consent_codes>.tar.gz`
  * _Image Files - DICOM_: At this time, only two projects with DICOM imagining files are available: `parent-COPDGene_HMB_` and `parent-COPDGENE_DS-CS_`. These files can be found in the `imaging_file` node and are files that have the extension `.dcm`
* **TOPMed**
  * _Genomic data_: Available data can include CRAM, VCFs and Cohort-level VCF files
  * _Phenotypic data_: TOPMed studies without an associated Parent study will include phenotypic data in the data graph by way of DCC harmonized variables. Additionally, raw phenotypic data from dbGaP can be found in the `reference_file` as tar files that share this common naming scheme: `RootStudyConsentSet_phs######.<study_shorthand>.v#.p#.c#.<consent_codes>.tar.gz`

# Relationship Between Parent and TOPMed Studies

There are three distinct relationships possible between Parent and TOPMed studies.

* **Parent only** -  The Parent study does not have a TOPMed counterpart study. This usually means that there are no genomic data, such as WXS \(whole exome sequencing\) or WGS \(whole genome sequencing\), located within the study; only phenotypic data.
* **TOPMed only** - This TOPMed study does not have a Parent counterpart study. These studies will contain both genomic data, WXS or WGS, and phenotypic data.
* **Parent study with a counterpart TOPMed study** - The Parent study will contain the phenotypic data, while the TOPMEd study will contain the genomic data. Under dbGaP, these studies would be kept separate from one another and the user would need to create the linkages. **In the Gen3 platform, these studies have been linked together under the Parent study, based on the participant IDs found in dbGaP.** This allows our system to produce valuable information and cohort creation as it combines both phenotypic and genomic data.

So, if you are looking at a Parent study in Gen3 for which there is also a counterpart TOPMed study, you will see genomic data in both studies, even though traditionally Parent studies lack genomic data.



