# Performing GWAS in Terra with example costs

#### Author: Beth Sheets \(UC Santa Cruz, Genomics Institute\)

Terra provides powerful support for performing Genome-Wide Association Studies \(GWAS\). The following featured and template workspaces include Jupyter notebooks for phenotypic and genomic data preparation \(using Hail\) and workflows \(using GENESIS\) to perform single or aggregate variant association tests using mixed models. We will continue to provide more resources for performing more complex GWAS scenarios in BioData Catalyst. 

####  Kinship Matrices

A Jupyter notebook in both workspaces covers uses Hail to generate Genetic Related Matrices  for input into the GWAS workflows. Users with access to kinship matrices from the TOPMed consortium may wish to exclude these steps and instead import kinship files using the[ bring your own data instructions](https://bdcatalyst.gitbook.io/biodata-catalyst-documentation/analyze-data/terra/using-your-own-data-with-terra). 

### Tutorial Workspace

This workspace was created to walk users through a GWAS with training data that includes synthetic phenotypic data \(modeled after traits available in TOPMed\) paired with 1000 Genomes open access data. This tutorial aims to familiarize users with the Gen3 data model so that they can become empowered to use this data model with any [existing tutorials ](https://app.terra.bio/#library/showcase)available in Terra. 

* [**BioData Catalyst GWAS Tutorial**](https://terra.biodatacatalyst.nhlbi.nih.gov/#workspaces/biodata-catalyst/BioData%20Catalyst%20GWAS%201000%20Genomes%20Tutorial)

### Template Workspace

This template is an example workspace that asks researchers to export TOPMed projects \(for which they have access\) into an example template for conducting a common variant, mixed-models GWAS of a blood pressure trait. Our goal was to include settings and suggestions to help users interact with data exactly as they receive it through BioData Catalyst.  Accommodating other datasets may require modifying many parts of this notebook. Inherently, the notebook is an interactive analysis where decisions are made as you go. It is not recommended that the notebook be applied to another dataset without careful thought.

* [**BioData Catalyst GWAS blood pressure trait**](https://terra.biodatacatalyst.nhlbi.nih.gov/#workspaces/biodata-catalyst/BioData%20Catalyst%20GWAS%20blood%20pressure%20trait)\*\*\*\*

## Cost Examples

Below are reported costs from using 1,000 and 10,000 samples to conduct a GWAS using the BioData Catalyst GWAS Blood Pressure Trait template workspace. The costs were derived from single variant tests that used Freeze 5b VCF files that were filtered for common variants \(MAF &lt;0.05\) for input into workflows. The way these steps scale will vary with the number of variants, individuals, and parameters chosen. TOPMed Freeze 5b VCF files contain 582 million variants and Freeze 8 increases to ~1.2 billion. For GWAS analyses with Freeze 8 data, computational resources and costs are expected to be significantly higher.

| Analysis Step | Cost \(n=1,000; Freeze5b\) | Cost \(n=10,000; Freeze 5b\) |
| :--- | :--- | :--- |
| [GWAS Preliminary Analysis Notebook](https://app.terra.bio/#workspaces/biodata-catalyst/BioData%20Catalyst%20GWAS%20blood%20pressure%20trait/notebooks/launch/2-GWAS-preliminary-analysis.ipynb) | $29.34 \($19.56/hr for 1.5 hours\) | $336 \($56/hr for 6 hours\) |
| [vcfTogds](https://dockstore.org/workflows/github.com/manning-lab/vcfToGds:master?tab=info) workflow | $1.01 | $5.01 |
| [genesis\_GWAS](https://dockstore.org/workflows/github.com/AnalysisCommons/genesis_wdl/genesis_GWAS:v1_4_1?tab=info) workflow | $0.94 | $6.67 |
| **TOTAL** | **$32.29** | **$347.68** |

These costs were derived from running these analyses in Terra in June 2020.







