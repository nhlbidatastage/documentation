---
description: >-
  Overview of Parent and TOPMed studies hosted on the BioData Catalyst Gen3
  platform
---

# Parent and TOPMed Studies

## Distinguishing Between Parent and TOPMed Studies

The Parent and TOPMed study types have been separated on Gen3 by their Program designation. An example of this division by Program is presented below.

![A list of Parent \(underlined in blue\) and TOPMed studies \(underlined in red\)](../../.gitbook/assets/parent_topmed_studies2.png)

The Program types can be further identified by the `_` \(underscore\) at the end of all Parent studies.

## Parent and TOPMed Study Contents

The most notable difference between both Program categories is the type of hosted data for each

 **Programs:**

* TOPMed
  * _Genomic data_: Available data can include CRAM, VCFs and Cohort-level VCF files
  * _Phenotypic data_: TOPMed studies without an associated Parent study will include phenotypic data in the data graph by way of DCC harmonized variables. Additionally, raw phenotypic data from dbGaP can be found in the `reference_file` as tar files that share this common naming scheme: `RootStudyConsentSet_phs######.<study_shorthand>.v#.p#.c#.<consent_codes>.tar.gz`
* Parent
  * _Genomic data_: None
  * _Phenotypic data_: Like with TOPMed studies, any phenotypic data found within the Graph Model, will only be DCC harmonized variables. For the raw phenotypic data from dbGaP, again, it can be found in the `reference_file` node in the tar files that share this common naming scheme: `RootStudyConsentSet_phs######.<study_shorthand>.v#.p#.c#.<consent_codes>.tar.gz`
  * _Image Files - DICOM_: At this time, only two projects with DICOM imagining files are available: `parent-COPDGene_HMB_` and `parent-COPDGENE_DS-CS_`. These files can be found in the `imaging_file` node and are files that have the extension `.dcm`

