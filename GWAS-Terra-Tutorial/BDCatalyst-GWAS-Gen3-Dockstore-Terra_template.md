# Template Blood Pressure Trait GWAS in NHLBI's BioData Catalyst

This template workspace was created to offer example tools for conducting a single variant, mixed-models GWAS focusing on a blood pressure trait from start to finish using the [NHLBI BioData Catalyst](https://www.nhlbidatastage.org/) ecosystem. We have created a set of documents [to get you started in the the BioData Catalyst system](https://support.terra.bio/hc/en-us/sections/360007757832). If you're ready to conduct an analysis, proceed with this dashboard: 


## Data Model

This template was set up to work with the NHLBI BioData Catalyst Gen3 data model. In this dashboard, you will learn how to import data from the Gen3 platform into this Terra template and conduct an association test using this particular data model.

### TOPMed Data

Currently, BioData Catalyst's Gen3 hosts the [TOPMed](https://www.nhlbi.nih.gov/science/trans-omics-precision-medicine-topmed-program) program, which is controlled access. If you do not already have access to a TOPMed project through dbGAP, this template workspace may not yet be helpful to you. To apply for access to TOPMed data , you must submit an application for each individual project of interest in [dbGAP](https://www.nhlbiwgs.org/topmed-data-access-scientific-community). 

If you already have access to a TOPMEd project and have been onboarded to the BioData Catalyst platform, you should be able to access your data through BioData Catalyst powered by Gen3 and use your data with this template workspace. We focused this template on analyzing a blood pressure trait, but not all TOPMed projects may contain blood pressure data. You will need to carefully consider how to update this analysis for the dataset you bring and how this may affect the scientific accuracy of the question you are asking. 


### A note about TOPMed metadata
Some types of metadata will always be present:  GUID, Case ID, Project Name, Number of Samples, Study, Gender, Age at Index, Race, Ethnicity, Number of Aliquots, SNP Array Files, Unaligned Read Files, Aligned Read Files, Germline Variation Files.

Other metadata depend on the analysis plan submitted when applying for TOPMed access. Examples include BMI, Years Smoked, years smoked greater than 89, hypertension, hypertension medications, diastolic blood pressure, systolic blood pressure, etc.

The TOPMed Data Coordinating Center (DCC) is currently harmonizing select phenotypes across TOPMed, which will also be deposited into the TOPMed accessions. The progress of phenotype metadata harmonization can [be tracked here](https://topmedphenotypes.org/).



## Outline of this template:

***Part 1: Navigate the BioData Catalyst environment***
Learn how to search and export data from Gen3 and worfklows from Dockstore into a Terra workspace. Each of these cloud-based platforms easily operate with one another for fast and secure research.  The template we have created here can be cloned for you to walk through as suggested, or you can use the basics you learn here to perform your own analysis. 


***Part 2: Explore TOPMed data in an interative Jupyter notebook***
In this Terra workspace, you can find a series of interactive notebooks to explore TOPMed data. 

First, you will need to review what clinical data tables you imported with your selected project from Gen3. Then, review the **0-terra_data_util** companion notebook. This companion notebook is available to researchers to manipulate graph-structured TOPMed data from Gen3 (which you will learn more about below). You will need to edit a few cells in this notebook to match the data table names of your project. 

Next, the **1-GWAS-preliminary-analysis** notebook will lead you through a series of steps to explore the phenotypic and genotypic data. It will call the functions in the 0-terra-data-util notebook and to consolidate your clinical data from Gen3 into a single data table that can be imported into the Jupyter notebook.  Then you will examine phenotypic distributions through a series of graph and genetic relatedness using the [HAIL genomic data analysis tool](https://hail.is/).  


***Part 3: Perform mixed-model association tests using workflows***
Next, perform mixed models genetic association tests (run as a series of batch workflows using GCP Compute engine). For details on the four workflows and what they do, scroll down to **Perform mixed model association test workflows**.  The workflows are publicly available in [Dockstore](https://dockstore.org/) in this [collection](https://dockstore.org/organizations/bdcatalyst/collections/GWAS).       

Mixed models require two steps within the [GENESIS](https://bioconductor.org/packages/release/bioc/html/GENESIS.html) package in [R](https://www.r-project.org/about.html):     
1) Fitting a null model assuming that each genetic variant has no effect on phenotype and 2) Testing each genetic variant for association with the outcome, using the fitted null model.
	

***Part 4: Interactive GWAS summarization in notebook***
Finally, we provide an optional notebook **2-GWAS-summarization** for further summarization of the GWAS results. This notebook provides visible code, editable by the user, that aggregates variants into individual loci grouped by lead variant and generates customizable visualizations. 


-----

# Part 1: Navigate the NHLBI BioData Catalyst multi-platform ecosystem

## 1a) Link your Terra account to external services
Before you're able to access genomic data from Gen3 in the Terra data table,  you need to link your Terra account to external services. Link your profile [by following these instructions](https://support.terra.bio/hc/en-us/articles/360038086332?flash_digest=2f492682b688b21da27c701af68656ac095d5803).

## 1b) Create an Authorization Domain to protect your controlled-access data

Because this workspace was created to be used with controlled access data, it should be registered under an Authorization Domain that limits its access to only researchers with the appropriate approvals. Learn how to set up an Authorization Domain [here](https://support.terra.bio/hc/en-us/articles/360039415171) before proceeding

## 1c) Create your own workspace for computing in the cloud 
1. At the top right corner of this template. Use your mouse to click the circle with three dots. This will open a window where you can click "clone".  Cloning creates a copy of this workspace that you own and can use to work through this tutorial, or use a a template for your own analyses. 

![](https://github.com/nhlbidatastage/documentation/blob/master/GWAS-Terra-Tutorial/images/Terra-clone.png?raw=true)

2. After you hit clone, a pop-up window appears asking you to fill out some information. 
- Workspace name: Enter a name a name that is meaningful for your records.
- Billing Project: Select the billing projects available to you. If you are a new user, you can use the [$300 of free credits offered](https://support.terra.bio/hc/en-us/articles/360027940952-Free-credits-FAQs).
- Authorization Domain: Assign the authorization domain that you generate above to protect your data.

## 1d) Export a TOPMed project with blood pressure data from Gen3

1. Start by learning about Gen3's graph-structured data model for NHLBI's BioData Catalyst using this [orientation document](https://support.terra.bio/hc/en-us/articles/360038087312).
2. Once you better understand the graph, log into [Gen3](https://gen3.datastage.io) through the NIH portal using your eRA Commons username and password. 
3. Navigate to the [Gen3 Explorer](https://gen3.datastage.io/explorer) view to see what datasets you currently have and do not have access to. On the left hand side, you can use the [faceted search tool](https://gen3.org/resources/user/access-data/) to narrow your results to specific projects. 
4. First, under "Files" and "Access", select "Data with Access" to filter through projects that you currently have access to.
5. Next, under "Filters", you can select a specific type of metadata you are interested in studying. Here, select the "Diagnosis" tab and under "BP Diastolic" move the left hand side of the sliding bar from 0 to 35.  This will make your search range 35 - 163. This will only show the TOPMed projects that contain that metadata type. 
6. In all of TOPMed, there are 23 studies with diastolic blood pressure metadata. You may see anywhere from 0 to 23, depending on what projects you have applied for and received access to. 
12. Next, click on the "Subject" tab. If you have access to a TOPMed project with blood pressure data, this will list all of the project names. Select only a single project to use in this template. 
14. Once selected, click the button "Export all to Terra", wait until the Terra window appears, and add your data to your copy of this template workspace. 

-----

# Part 2: Explore TOPMed data in Jupyter Notebooks   
## 2a) Copy multi-sample VCFs to your workspace 
Genomic files in the BioData Catalyst project are hosted in controlled access buckets. Using DRS, you can send your credentials to access these buckets. In order to interact with controlled access multi-sample VCF files in the proceedings notebooks, we first need to copy the VCF to our workspace bucket. The first notebook you will open, **1-vcf-download**, will let you select which VCF to copy to your workspace from the Reference File data table. Because these multi-sample VCFs are very large, this process currently takes a long time. 

## 2b) Consolidate data tables from Gen3 
Next, you will use a set of functions to consolidate the graph structure data model into a single consolidated table that you can easily interact with in a notebook. 

1. Review what data tables came into Terra with the project you selected by opening a new window of this workspace and going to the data tab. 
2. In this template, we have set up our analysis to work with the data tables: "subject", "blood_pressure_test", "demographic", "exposure", "lab_result", "medical_history", "medication", and "sample". Check to see if you have these tables of if you are missing any.
3. Next, open the  **2-terra_data_util** companion notebook. This companion notebook is available to researchers to manipulate graph-structured TOPMed data from Gen3. 
4. Read the instructions in the beginning to edit the first few cells in this notebook to match the clinical data tables you imported from Gen3. If your project does not have one of the data tables listed in step 1 above, you will need to remove that data table from the consolidation function in the 0-terra_data_util notebook before proceeding. 


## 2c) Prepare your phenotypic and genotypic data for input into association test workflows
Now that you can interact with the Gen3 structured data more easily, you will use an interactive notebook to explore your phenotypic and environmental data and performs several analyses to prepare the data for use in batch association workflows. 

1. [Learn how to customize your interactive analysis compute](https://support.terra.bio/hc/en-us/articles/360038125912) to work with the data you imported. 
3. Open the **3-GWAS-preliminary-analysis** notebook and set your runtime configuration. We have given a suggested configuration within the notebook.
4. Call functions from the 0-terra_data_util notebook to reformat multiple data tables into a single entity that can be loaded as a dataframe in the notebook.
5. Subset the dataframe to include only your traits of interest and remove any individuals that lack data for these traits.
6. Visualize phenotype and environmental variable distributions in a series of plots.
7. Import the multi-sample VCF from the "Reference File" data table using DRS. You can learn more about GA4GH's Data Repository Service [here](https://support.terra.bio/hc/en-us/articles/360039330211).
8. Filter your VCF to only common variants to increase statistical power. Genetic analyses in this notebook utilize the [Hail software](https://hail.is/). Hail is a framework for distributed computing with a focus on genetics. Particularly relevant for whole genome sequence ([WGS](https://en.wikipedia.org/wiki/Whole_genome_sequencing)) analysis, Hail allows for efficient, nearly boundless computing (in terms of variant and sample size).    
9. Perform a principal component analysis ([PCA](https://en.wikipedia.org/wiki/Principal_component_analysis)) to assess if population stratification. Genetic stratification can strongly affect association tests and should be accounted for.
10. Generate a genetic relatedness matrix ([GRM](https://hail.is/docs/0.2/methods/genetics.html?highlight=pc_rel#hail.methods.genetic_relatedness_matrix)) to account for closely related individuals in your association testing workflows.
11. Generate a new "sample_set" data table that holds the derived files we created in the steps above using the [FireCloud Service Selector (FISS) package](https://github.com/broadinstitute/fiss).  The files in this data table will be used in the workflows we run in Part 3.     



### Time and cost estimate
You are able to adjust the runtime configuration to fit your computational needs in the Jupyter notebook. We recommend selecting the default environment and selecting the custom profile to use and configure the spark cluster for parallel processing.  Using the profile suggested profile below and a project with around 1000 samples, running this notebook on this dataset takes about 60 minutes and $11.37 to compute.
 

When working in a notebook that may have compute times over 30 minutes, learn more about Terra's [auto-pause feature](https://support.terra.bio/hc/en-us/articles/360029761352-What-you-need-to-know-about-notebook-auto-pause-) and [how to adjust auto-pause](https://support.terra.bio/hc/en-us/articles/360027570951-Manually-setting-auto-pause-for-notebooks-using-gsutil) for your needs. Please carefully consider how adjusting auto-pause can remove protections that help you from accidentally accumulating cloud costs that you did not need.

-----

# Part 3: Perform mixed-model association tests using workflows
In Part 2, we explored the data we imported from Gen3 and performed a few important steps for preparing our data for association testing. We generated a new "sample_set" data table that holds the files we created in the interactive notebook. These files will be used in our batch workflows that will perform the association tests. Below, we describe the four workflows in this workspace and their cost estimates for running on the sample set we create in this tutorial.  

The workflows used in this template were imported from [Dockstore](www.dockstore.org) and their parameters were configured to work with Terra's data model.  If you're interested in searching other docker-based workflows, [learn more about how they can easily be launched in Terra](https://support.terra.bio/hc/en-us/articles/360038137292).


#### [1-vcfToGds](https://dockstore.org/workflows/github.com/manning-lab/vcfToGds)

This workflow converts genotype files from Variant Call Format ([VCF](https://en.wikipedia.org/wiki/Variant_Call_Format)) to Genomic Data Structure ([GDS](https://www.biostat.washington.edu/sites/default/files/modules/GDS_intro.pdf)), the input format required by the R package GENESIS.       

##### Time and cost estimates    

| Sample Set Name | Sample Size | # Variants | Time | Cost $ |
| -------  | --------  | -------- | -------- | ---------- |
| systolicbp | 1,052 samples | 6,429,788 | 6m | $2.26

Inputs:
* VCF  genotype file (or chunks of VCF files)

Outputs:
* GDS genotype file

#### [2-genesis_nullmodel](https://dockstore.org/workflows/github.com/AnalysisCommons/genesis_wdl/genesis_nullmodel)

- This workflow generates a mixed model under the hypothesis of no variant effect using the GENESIS software.        

##### Time and cost estimates    

| Sample Set Name | Sample Size | Time | Cost |
| -------  | -------- | -------- | ---------- |
|  systolicbp | 1,052 samples | 4m | $0.02

Inputs:
* GDS genotype file
* Genetic Relatedness Matrix
* Trait outcome name
* Trait outcome type
* CSV file of covariate traits
* Sample ID list

Outputs:
* A null model as an RData file


#### [3-genesis_tests](https://dockstore.org/workflows/github.com/AnalysisCommons/genesis_wdl/genesis_tests)

This workflow generates per-variant association statistics with our mock phenotype data, using the null model.      

##### Time and cost estimates    

| Sample Set Name | Sample Size | # Variants | Time | Cost |
| -------  | -------- | -------- | -------- | ---------- |
| systolicbp | 1,052 samples | 6,429,788 | 8m | $0.55 

Inputs:
* GDS genotype file
* Null model as an RData file

Outputs:
* Compressed csv file(s) containing raw results


#### [4-summaryCSV](https://dockstore.org/workflows/github.com/manning-lab/singleVariantAssociation/summaryCSV)

This workflow combines multiple summary statistics files produced above and generates quantile-quantile (QQ) and Manhattan (MH) plots (common descriptive figures of the GWAS results). The workflow outputs the plots (as a pdf) and two CSV files: one with all results combined into a single table and one a table of top results with p-value less than the specified threshold.      

##### Time and cost estimates    

| Sample Set Name | Sample Size | # Variants | Time | Cost |
| -------  | -------- | -------- | -------- | ---------- |
|  systolicbp | 1,052 samples | 6,429,788 | 17m | $0.06

Inputs:
* Compressed csv file(s) containing raw results

Outputs:
* CSV file containing all associations
* CSV file containing top associations
* PNG file of QQ and Manhattan plots

-----

# Part 4: Interactive GWAS summarization in a notebook

The final workflow (4-summaryCSV) outputs two csv files with association results (the top candidates and all associations) as well as a png containing summary figures. The **4-GWAS-summarization** notebook is another resource for viewing results of your analyses and the notebook feature allows you to edit for specific use cases.

# Bring your own data
Both the notebook and workflow can be adapted to other genetic datasets. The steps for adapting these tools to another dataset are outlined below:

***Update the data tables***  Learn more about uploading data to Terra [here](https://support.terra.bio/hc/en-us/articles/360025758392-Managing-data-with-the-data-table-).  You can use functions available from the terra_data_util companion notebook to consolidate new data tables you generate.

***Update the notebook***
Accommodating other datasets may require modifying many parts of this notebook. Inherently, the notebook is an interactive analysis where decisions are made as you go. It is not recommended that the notebook be applied to another dataset without careful thought. 

***Run an additional workflow***
You can search [Dockstore](www.dockstore.org) for available workflows and export them to Terra following [this method](https://docs.dockstore.org/en/develop/launch-with/terra-launch-with.html). 


### Helpful resources to master this tutorial

* If you have never used Terra before, peruse the [Terra knowledge base](https://support.terra.bio/hc/en-us). You can also [physically attend](https://support.terra.bio/hc/en-us/articles/360031181251-Terra-1-day-Workshop-) or [watch a recording](https://support.terra.bio/hc/en-us/articles/360031719611-Terra-workshop-at-BroadE-July-25-2019) of one of the Broad Institute Introduction to Terra workshops. 

* [Controlling cloud costs](https://support.terra.bio/hc/en-us/articles/360029748111)

* [Intro to Jupyter notebooks in Terra](https://app.terra.bio/#workspaces/help-gatk/Jupyter%20Notebooks%20101)

* [Intro to Hail using a Terra workspace](https://app.terra.bio/#workspaces/help-gatk/Hail-Notebook-Tutorials)

* [GWAS tutorial using open data from the 1000 Genomes Project](https://app.terra.bio/#workspaces/broad-t2d-dev/Running_GWAS_in_Terra)


### Authors, contact information, and funding

This template was created for the [NHLBI's BioData Catalyst](https://www.nhlbidatastage.org/) project in collaboration with the [Computational Genomics Platform](https://cgpgenomics.ucsc.edu/) at [UCSC Genomics Institute](https://ucscgenomics.soe.ucsc.edu/) and the [Data Sciences Platform](https://www.broadinstitute.org/data-sciences-platform) at [The Broad Institute](https://www.broadinstitute.org/). The association analysis tools were contributed by the [Manning Lab](https://manning-lab.github.io/).

Contributing authors include:
* [Beth Sheets](mailto:esheets@ucsc.edu) (UC Santa Cruz Genomics Institute)
* Michael Baumann (Broad Institute, Data Sciences Platform)
* Brian Hannafious (UC Santa Cruz Genomics Institute)
* [Tim Majarian](mailto:tmajaria@broadinsitute.org) (Manning Lab)
* Alisa Manning (Manning Lab)


----

### Workspace change log 

| Date | Change | Author | 
| -------  | -------- | -------- |
| Jan 31, 2020 | Replaced text with new Broad documentation | Beth |
| Jan 30, 2020 | Template updates | Beth |
| Jan 3, 2020 | Updates from BDC F2F | Beth |
| December 3, 2019 | Gen3 updates | Beth |
| November 22, 2019 | Updates from Alisa | Beth |
|  October 22, 2019 | User experience edits from Beri | Beth|
