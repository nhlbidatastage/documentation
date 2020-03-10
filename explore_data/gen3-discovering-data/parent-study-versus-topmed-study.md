---
description: >-
  This page will explain the difference between Parent and TOPMed studies found
  on Gen3's BioData Catalyst.
---

# Parent and TOPMed Studies

## Distinguishing Between Parent and TOPMed Studies on Gen3 BioData Catalyst

The two different study types, Parent and TOPMed, have been separated on Gen3 by Program. This division by Program is most visible mechanism to differentiate the two different studies.

![A list of studies with Parent studies, underlined in blue, and TOPMed studies, underlined in red.](../../.gitbook/assets/parent_topmed_studies2.png)

These two Programs can be further identified by the following Project name. All Parent studies will also end in an `_` \(underscore\) to further differentiate them within the Gen3 BioData Catalyst system.

## Parent and TOPMed Study Contents

The most notable difference in these two Program types are the type of data available. The following is what you can expect to find in the two Programs:

* TOPMed
  * Genomic data: This includes files like CRAM, VCFs and Cohort Level VCFs.
  * Phenotypic data: TOPMed studies, which do not have a Parent counter part study, will have phenotypic data for the patients. The phenotypic data in the graph is only DCC harmonized variables, but raw phenotypic data from dbGaP can be found in the `reference_file` node in the tar files that share this common naming scheme: `RootStudyConsentSet_phs######.<study_shorthand>.v#.p#.c#.<consent_codes>.tar.gz`.
* Parent
  * Phenotypic data: Like with TOPMed studies, any phenotypic data found within the Graph Model, will only be DCC harmonized variables. For the raw phenotypic data from dbGaP, again, it can be found in the `reference_file` node in the tar files that share this common naming scheme: `RootStudyConsentSet_phs######.<study_shorthand>.v#.p#.c#.<consent_codes>.tar.gz`.
  * DICOM: At this time, only two projects with DICOM imagining files are available: `parent-COPDGene_HMB_` and `parent-COPDGENE_DS-CS_`. These files can be found in the `imaging_file` node and are files that have the extension `.dcm`.

