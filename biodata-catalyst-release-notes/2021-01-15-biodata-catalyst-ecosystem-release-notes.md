# 2021-01-15 BioData Catalyst Ecosystem Release Notes

### **Introduction**

The 2021-01-15 release marks the fourth release for the NHLBI BioData Catalyst ecosystem. This release includes several new features \(e.g., CWL workflows to create dataset specific files needed for GWAS\) along with documentation and tutorials to help new users get started on the system. This release also includes enhanced support for CWL tools for post-GWAS analysis and a CWL tool for Bcftools Merge and Filter. Please find more detail on the new features and user support materials in the sections below.

The 2021-01-15 data release includes the addition of both TOPMed studies and the ORCHID Study, conducted by the \(PETAL\) Clinical Trials Network of NHLBI. Multi-sample VCFs, CRAMs and unharmonized clinical files were added for 27 TOPMed studies new to BioData Catalyst. Additionally, 7 TOPMed studies previously hosted on BioData Catalyst were updated to the latest study versions. These updates include new CRAMs, unharmonized clinical files and multi-sample VCFs for Freeze 8. For each study and consent group, VCF files are available on a per chromosome basis and in an un-tarred format. The associated clinical files were added for the ORCHID study.

Please refer to the Data Release section below for more information as well as the [Data page](https://biodatacatalyst.nhlbi.nih.gov/resources/data) on the BioData Catalyst website.  
****

### **Significant new features**

**CWL workflows to create dataset specific files needed for GWAS:** Users can now find the following CWL workflows for creating dataset specific files needed for GWAS in the [Seven Bridges Public Apps Gallery](https://platform.sb.biodatacatalyst.nhlbi.nih.gov/public/apps):

* [LD Pruning](https://platform.sb.biodatacatalyst.nhlbi.nih.gov/public/apps#smgogarten/uw-gac-commit/ld-pruning/) - Filter variants based on linkage disequilibrium measures
* [KING robust](https://platform.sb.biodatacatalyst.nhlbi.nih.gov/public/apps#smgogarten/uw-gac-commit/king-robust/) and [KING IBDseg](https://platform.sb.biodatacatalyst.nhlbi.nih.gov/public/apps#smgogarten/uw-gac-commit/king-ibdseg/) - Estimate kinship coefficients
* [PC-AiR](https://platform.sb.biodatacatalyst.nhlbi.nih.gov/public/apps#smgogarten/uw-gac-commit/pc-air/) - Perform principal components analysis 
* [PC-Relate](https://platform.sb.biodatacatalyst.nhlbi.nih.gov/public/apps#smgogarten/uw-gac-commit/pc-relate/) - Estimate genetic relatedness

**CWL tools for post-GWAS analysis:** Users can now find the following CWL tools for post-GWAS analysis in the [Seven Bridges Public Apps Gallery](https://platform.sb.biodatacatalyst.nhlbi.nih.gov/public/apps):

* [SBG Loci Snapshoter](https://platform.sb.biodatacatalyst.nhlbi.nih.gov/public/apps#admin/sbg-public-data/loci-snapshoter/) - Generate screenshots of specific regions of aligned files provided as inputs
* [GENESIS LocusZoom](https://platform.sb.biodatacatalyst.nhlbi.nih.gov/public/apps#admin/sbg-public-data/genesis-locuszoom/) - Standalone tool for generating static locus zoom plots. Users can make annotated Manhattan plots on specific regions from association files generated with the GENESIS association workflows.

**CWL tool for Bcftools Merge and Filter:** Users can now find a CWL tool for [BCFtools Merge and Filter](https://platform.sb.biodatacatalyst.nhlbi.nih.gov/public/apps#smgogarten/uw-gac-commit/bcftools-merge-and-filter/) in the Seven Bridges Public Apps Gallery. This tool merges multiple VCF/BCF files from non-overlapping sample sets to create one multi-sample file and filter out any monomorphic variants. This tool is useful when working with input files that contain monomorphic variants like the TOPMed datasets.  


### **New user support materials and documentation**

**Genetic Association Testing Using the GENESIS Workflows tutorial:** Seven Bridges updated this tutorial to show how to perform an association test using the GENESIS workflows using TOPMed Freeze 8 multi-sample VCF data. Previous versions of this tutorial used TOPMed Freeze 5 data. Version 1.1 of this tutorial can be downloaded as a PDF from the [Tutorials page of the BioData Catalyst GitBook](https://bdcatalyst.gitbook.io/biodata-catalyst-tutorials/tutorials/seven-bridges-tutorials).

**ORCHID Clinical Trial Statistical Analysis Reproduction:** NHLBI BioData Catalyst has made data available to authorized investigators for the study titled: PETAL Network: Outcomes Related to COVID-19 Treated With Hydroxychloroquine Among Inpatients With Symptomatic Disease \(ORCHID\) Trial, phs002299.v1.p1. This is based on the multi-center, double blinded, randomized clinical trial conducted to assess the efficacy of hydroxychloroquine in the treatment of COVID-19. Results were published in JAMA on November 9th, 2020 \([paper available here](https://jamanetwork.com/journals/jama/fullarticle/10.1001/jama.2020.22240?utm_campaign=articlePDF&utm_medium=articlePDFlink&utm_source=articlePDF&utm_content=jama.2020.22240)\). This notebook enables anybody with authorized credentials to reproduce the ORCHID clinical trial results by showing how to 1\) Access the data using the PIC-SURE API and 2\) Reproduce the results of this study using the open-source R programming language. Available in [Seven Bridges Public Project, under PIC-SURE API](https://platform.sb.biodatacatalyst.nhlbi.nih.gov/) or through [PIC-SURE GitHub](https://github.com/hms-dbmi/Access-to-Data-using-PIC-SURE-API/tree/master/NHLBI_BioData_Catalyst).  


### **Data release**

The table below highlights which studies were included in the 2021-01-15 data release which includes both TOPMed studies and The Outcomes Related to COVID-19 treated with hydroxychloroquine among In-patients with symptomatic Disease study, or ORCHID Study, conducted by the \(PETAL\) Clinical Trials Network of NHLBI. Multi-sample VCFs, CRAMs and unharmonized clinical files were added for 27 TOPMed studies new to BioData Catalyst. Additionally, 7 TOPMed studies previously hosted on BioData Catalyst were updated to the latest study versions. These updates included new CRAMs, unharmonized clinical files and multi-sample VCFs for Freeze 8. For each study and consent group, VCF files are available on a per chromosome basis and in an un-tarred format. The associated clinical files were added for the ORCHID study. The data is now available for access across the entire ecosystem.

| Study Name | phs I.D. \# | Acronym | New to BioData Catalyst | New study version |
| :--- | :--- | :--- | :--- | :--- |
| NHLBI TOPMed: Genome-wide Association Study of Adiposity in Samoans | phs000972 | SAS |  |  |
| NHLBI TOPMed: The Genetics and Epidemiology of Asthma in Barbados | phs001143 | BAGS |  | Yes |
| NHLBI TOPMed: Rare Variants for Hypertension in Taiwan Chinese \(THRV\) | phs001387 | THRV |  | Yes |
| NHBLI TOPMed: Pharmacogenomics of Hydroxyurea in Sickle Cell Disease \(PharmHU\) | phs001466 | pharmHU | Yes |  |
| NHLBI TOPMed: Study of Asthma Phenotypes and Pharmacogenomic Interactions by Race-Ethnicity \(SAPPHIRE\) | phs001467 | SAPPHIRE\_asthma | Yes |  |
| NHLBI TOPMed: MyLifeOurFuture \(MLOF\) Hemophilia Study | phs001515 | MLOF | Yes |  |
| NHLBI TOPMed: Diabetes Heart Study \(DHS\) African American Coronary Artery Calcification \(AA CAC\) | phs001412 | AACAC |  | Yes |
| NHLBI TOPMed: Novel Risk Factors for the Development of Atrial Fibrillation in Women | phs001040 | WGHS |  | Yes |
| NHLBI TOPMed: The Vanderbilt Atrial Fibrillation Registry \(VU\_AF\) | phs001032 | VU\_AF |  |  |
| NHLBI TOPMed: The Genetic Epidemiology of Asthma in Costa Rica | phs000988 | CRA |  | Yes |
| NHLBI TOPMed - NHGRI CCDG: MGH Atrial Fibrillation Study | phs001062 | MGH\_AF |  | Yes |
| NHLBI TOPMed: Australian Familial Atrial Fibrillation Study | phs001435 | AustralianFamilialAF | Yes |  |
| NHLBI TOPMed: African American Sarcoidosis Genetics Resource | phs001207 | Sarcoidosis |  | Yes |
| NHLBI TOPMed: CHS Gene-Air Pollution Interactions in Asthma \(GAP\) | phs001602 | ChildrensHS\_GAP | Yes |  |
| NHLBI TOPMed: CHS \(Effects of Air Pollution on the Development of Obesity in Children\) | phs001604 | ChildrensHS\_MetaAir | Yes |  |
| NHLBI TOPMed - NHGRI CCDG: AFLMU | phs001543 | AFLMU | Yes |  |
| NHLBI TOPMed - NHGRI CCDG: Malmo Preventive Project \(MPP\) | phs001544 | MPP | Yes |  |
| NHLBI TOPMed - NHGRI CCDG: Intermountain INSPIRE Registry | phs001545 | INSPIRE\_AF | Yes |  |
| NHLBI TOPMed: Texas Cardiac Arrhythmia Institute - DECAF Study | phs001546 | DECAF | Yes |  |
| NHLBI TOPMed: Early-onset Atrial Fibrillation in the Estonian Biobank | phs001606 | EGCUT | Yes |  |
| NHLBI TOPMed: CHS Integrative Genomics and Environmental Research of Asthma \(IGERA\) | phs001603 | ChildrensHS\_IGERA | Yes |  |
| NHLBI TOPMed: Pulmonary Fibrosis Whole Genome Sequencing | phs001607 | IPF | Yes |  |
| NHLBI TOPMed - NHGRI CCDG: The GENetics in Atrial Fibrillation \(GENAF\) Study | phs001547 | GENAF | Yes |  |
| NHLBI TOPMed: Pulmonary Fibrosis Whole Genome Sequencing | phs001607 | IPF | Yes |  |
| NHLBI TOPMed: Chicago Initiative to Raise Asthma Health Equity \(CHIRAH\) | phs001605 | CHIRAH | Yes |  |
| NHLBI TOPMed: Pulmonary Fibrosis Whole Genome Sequencing | phs001607 | IPF | Yes |  |
| NHLBI TOPMed: Outcome Modifying Genes in Sickle Cell Disease \(OMG\) | phs001608 | OMG\_SCD | Yes |  |
| NHLBI TOPMed - NHGRI CCDG: Vanderbilt University BioVU Atrial Fibrillation Genetics Study | phs001624 | BioVU\_AF | Yes |  |
| NHLBI TOPMed: Lung Tissue Research Consortium \(LTRC\) | phs001662 | LTRC | Yes |  |
| NHLBI TOPMed CCDG: Groningen Atrial Fibrillation \(GGAF\) Study | phs001725 | GGAF | Yes |  |
| NHLBI TOPMed: Pathways to Immunologically Mediated Asthma \(PIMA\) | phs001727 | PIMA | Yes |  |
| NHLBI TOPMed: Best ADd-on Therapy Giving Effective Response \(BADGER\) | phs001728 | CARE\_BADGER | Yes |  |
| NHLBI TOPMed: Characterizing the Response to a Leukotriene Receptor Antagonist and an Inhaled Corticosteroid \(CLIC\) | phs001729 | CARE\_CLIC | Yes |  |
| NHLBI TOPMed: Pediatric Asthma Controller Trial \(PACT\) | phs001730 | CARE\_PACT | Yes |  |
| NHLBI TOPMed: TReating Children to Prevent EXacerbations of Asthma \(TREXA\) | phs001732 | CARE\_TREXA | Yes |  |
| PETAL Network: Outcomes Related to COVID-19 Treated With Hydroxychloroquine Among Inpatients With Symptomatic Disease \(ORCHID\) Trial | phs002299 | ORCHID | Yes |  |

### **For detailed platform release notes please consult the following resources:**

* Gen3 release notes
* [Terra release notes](https://support.terra.bio/hc/en-us/categories/360000693572)
* [Seven Bridges release notes](https://sb-biodatacatalyst.readme.io/blog)
* PIC-SURE release notes
* [Dockstore release notes](https://docs.dockstore.org/en/develop/changelog.html)

