# Performing Genome Wide Association Studies \(GWAS\) in Terra

#### Author: Beth Sheets \(UC Santa Cruz, Genomics Institute\)

Terra provides powerful support for performing Genome Wide Association Studies \(GWAS\). The following featured and template workspaces include Jupyter notebooks for phenotypic and genomic data preparation \(using Hail\) and workflows \(using GENESIS\) to perform single or aggregate variant association tests using mixed models. We will continue to provide more resources for performing more complex GWAS scenarios in BioData Catalyst. 

####  Kinship Matrices

These workspaces cover how to generate Genetic Related Matrices using Hail for input into a GWAS. Users with access to kinship matrices from the TOPMed DCC may wish to exclude these steps and instead import these files using the[ bring your own data instructions](https://bdcatalyst.gitbook.io/biodata-catalyst-documentation/analyze-data/terra/using-your-own-data-with-terra). 

### Tutorial Workspace

This workspace was created to walk users through a GWAS with training data that includes synthetic phenotypic data \(modeled after traits available in TOPMed\) paired with 1000 Genomes open access data. This tutorial aims to familiarize users with the Gen3 data model so that they can become empowered to use this data model with any [existing tutorials ](https://app.terra.bio/#library/showcase)available in Terra. 

* [**BioData Catalyst GWAS Tutorial**](https://terra.biodatacatalyst.nhlbi.nih.gov/#workspaces/biodata-catalyst/BioData%20Catalyst%20GWAS%201000%20Genomes%20Tutorial)

### Template Workspace

This template is an example workspace that asks researchers to export TOPMed projects \(for which they have access\) into an example template for conducting a common variant, mixed-models GWAS of a blood pressure trait. Our goal was to include settings and suggestions to help users interact with data exactly as they receive it through BioData Catalyst.  Accommodating other datasets may require modifying many parts of this notebook. Inherently, the notebook is an interactive analysis where decisions are made as you go. It is not recommended that the notebook be applied to another dataset without careful thought.

* [**BioData Catalyst GWAS blood pressure trait**](https://terra.biodatacatalyst.nhlbi.nih.gov/#workspaces/biodata-catalyst/BioData%20Catalyst%20GWAS%20blood%20pressure%20trait)\*\*\*\*



