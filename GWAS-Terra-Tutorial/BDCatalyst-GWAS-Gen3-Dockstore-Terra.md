# Template for conducting a blood pressure trait GWAS in NHLBI's BioData Catalyst

This template was created to offer example code and pointers for conducting a single variant, mixed-models GWAS focusing on a blood pressure trait from start to finish using the [NHLBI BioData Catalyst](https://www.nhlbidatastage.org/) ecosystem. Currently, BioData Catalyst's Gen3 hosts the [TOPMed](https://www.nhlbi.nih.gov/science/trans-omics-precision-medicine-topmed-program) program. If you do not already have access to a TOPMed project through dbGAP, this template workspace may not be helpful to you. To apply for access to TOPMed data , you must submit an application for each individual project of interest in [dbGAP](https://www.nhlbiwgs.org/topmed-data-access-scientific-community). 

If you already have access to a TOPMEd project, you should be able to access your data through BioData Catalyst powered by Gen3 and use your data with this template workspace. We focused this template on analyzing a blood pressure trait, but not all TOPMed projects may contain blood pressure data. You will need to carefully consider how to update this analysis for the dataset you bring and how this may affect the scientific accuracy of the question you are asking. 

### TOPMed Metadata

Some types of metadata will always be present:  GUID, Case ID, Project Name, Number of Samples, Study, Gender, Age at Index, Race, Ethnicity, Number of Aliquots, SNP Array Files, Unaligned Read Files, Aligned Read Files, Germline Variation Files.

Other metadata depend on the analysis plan submitted when applying for TOPMed access. Examples include BMI, Years Smoked, years smoked greater than 89, hypertension, hypertension medications, diastolic blood pressure, systolic blood pressure, etc.

The TOPMed Data Coordinating Center (DCC) is currently harmonizing select phenotypes across TOPMed, which will also be deposited into the TOPMed accessions. The progress of phenotype metadata harmonization can [be tracked here](https://topmedphenotypes.org/).



### Data disclaimer
Because this workspace was created to be used with controlled access data from BioData Catalyst, it should be registered under an [Authorization Domain](https://support.terra.bio/hc/en-us/articles/360026775691-Managing-data-privacy-and-access-with-Authorization-Domains) that limits its access to only researchers with the appropriate approvals. We provide you with instructions below on how to set up an authorization domain. When you copy a workspace with an Authorization Domain, all copies will also be protected under the same Authorization Domain and cannot be shared with external users.  **How you use this controlled access data are held accountable to your own IRB approval and data use restrictions.** 



### A brief outline of this tutorial is as follows:

***Part 1: Navigate the BioData Catalyst multi-platform environment***
Walk through a series of steps to learn how to search and export data from Gen3 and worfklows from Dockstore into a Terra workspace. Each of these cloud-based platforms easily operate with one another for fast and secure research.  The template we have created here can be cloned for you to walk through as suggested, or you can use the basics you learn here to perform your own analysis. 


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
This ecosystem encompasses multiple platforms that interoperate to allow researchers to discover, access, store, and compute large sets of data generated from biomedical and behavioral research. Data is secure in the cloud, where you can scale analyses easily and cost-efficiently. 

## Link your Terra account with your Gen3 and eRa Commons accounts.
1. If you have already done this step, you can skip to creating your own workspace. 
2. Go to the Terra "hamburger" menu at the top left and click to open the menu bar. 
3. Click on your profile. You can also go directly to this page using this [link](https://app.terra.bio/#profile).
4. On the right hand side of your profile page under "Identity & External Services", link both NIH and DCP Framework Services by University of Chicago services.
5. This should show a link expiration deadline for each external service. You will need to relink these services once they expire to continue to access data you import into Terra from Gen3.

## Create an Authorization Domain to protect your controlled-access data

1. Find instructions on creating an authorization domain [here](https://support.terra.bio/hc/en-us/articles/360026775691-Managing-data-privacy-and-access-with-Authorization-Domains).

## Create your own workspace for computing in the cloud 
1. At the top right corner of this template. Use your mouse to click the circle with three dots. This will open a window where you can click "clone".  Cloning creates a copy of this workspace that you own and can use to work through this tutorial, or use a a template for your own analyses. 

![](https://github.com/nhlbidatastage/documentation/blob/master/GWAS-Terra-Tutorial/images/Terra-clone.png?raw=true)

2. After you hit clone, a pop-up window appears asking you to fill out some information. 
- Workspace name: Enter a name a name that is meaningful for your records.
- Billing Project: Select the billing projects available to you. If you are a new user, you can use the [$300 of free credits offered](https://support.terra.bio/hc/en-us/articles/360027940952-Free-credits-FAQs).
- Authorization Domain: Assign the authorization domain that you generate above to protect your data.

## Find  TOPMed genotype and harmonized phenotype data in Gen3

1. Log into [Gen3](https://gen3.datastage.io) through the NIH portal using your eRA Commons username and password. 
2. Once logged in, navigate to the [Gen3 data dictionary](https://gen3.datastage.io) and review what harmonized metadata files are available and how they are linked to one another in the graph structure. This graph structure only represents genomic data and harmonized metadata from the [TOPMed DCC](https://topmedphenotypes.org/). Unharmonized metadata can be found in the Reference File node in the Gen3 graph, but it is not used in this template. 
3. If you are new to graph models, read through the [Gen3 dictionary documentation](https://gen3.org/resources/user/dictionary/)  to learn more. 
4. In this example, we will only focus on a small part of the graph. Near the center of the graph, click on the "Subject" box.  The subject refers to a collection of all data related to a specific subject in the context of a specific experiment.
 ![Gen3 TOPMed graph](https://github.com/nhlbidatastage/documentation/blob/master/GWAS-Terra-Tutorial/images/Gen3graph.png?raw=true)
5. Click on one of the blue node boxes below "Subject" that is linked by a single line (for example, "Demographic"). Each of these blue boxes represents clinical data collected for individuals in a study (see the key on the right hand side of the graph). The node "Demographic"  refers to the characterization of the patient by means of segmenting the population (e.g., characterization by age, sex, or race). You can click through other clinical trait nodes to see what metadata are available in the TOPMed graph. This graph represents all metadata in the entire TOPMed project, but metadata  will vary by project due to the analysis plan submitted for each project. 
![Gen3 demographic graph node example](https://github.com/nhlbidatastage/documentation/blob/master/GWAS-Terra-Tutorial/images/Gen3-demographic-node.png?raw=true)
7. Navigate to the [Gen3 Explorer](https://gen3.datastage.io/explorer) view to see what datasets you currently have and do not have access to. On the left hand side, you can use the [faceted search tool](https://gen3.org/resources/user/access-data/) to narrow your results to specific projects. 
8. First, under "Files" and "Access", select "Data with Access" to filter through projects that you currently have access to.
9. Next, under "Filters", you can select a specific type of metadata you are interested in. This will only show the TOPMed projects that contain that metadata type. If you don't see a specific type of metadata you are interested in. You can go back and select "Data without Access". This will let you use the faceted search to find which TOPMed projects you may want to request access to for your study. You will not be able to export these data until you are granted access through the dbGAP application process.
![Gen3 faceted search filters](https://github.com/nhlbidatastage/documentation/blob/master/GWAS-Terra-Tutorial/images/Gen3-faceted-search.png?raw=true)
10. For this template, select "Data with Access", then below select the "Diagnosis" tab and under "BP Diastolic" move the left hand side of the sliding bar from 0 to 35. 
11. In all of TOPMed, there are 23 studies with diastolic blood pressure metadata. You may see anywhere from 0 to 23, depending on what projects you have received access to. 
12. Next, click on the "Subject" tab. If you have access to a TOPMed project with blood pressure data, this will list all of the project names. Select only a single cohort.
14. Once selected, click the button "Export all to Terra".
![](https://github.com/nhlbidatastage/documentation/blob/master/GWAS-Terra-Tutorial/images/Gen3-ExportalltoTerra.png?raw=true)
8. You should see an "Export in Progress" banner appear. This process generally takes from 30 seconds to several minutes, depending on the size of the files. The metadata files and cloud bucket address links to genomic files are bundled into a PFB format and sent to Terra to import. 
![Gen 3 export](https://github.com/nhlbidatastage/documentation/blob/master/GWAS-Terra-Tutorial/images/Gen3-exportprogress.png?raw=true)
9. When the data export is ready, a new Terra window appears asking you to select a destination workspace. Select the copy of this workspace that you previously made here or you can create a new workspace to place your files. 
![Terra import data from Gen3](https://github.com/nhlbidatastage/documentation/blob/master/GWAS-Terra-Tutorial/images/Terra-ImportData.png?raw=true)


## Find reproducible workflows in [Dockstore](https://dockstore.org) 
For this tutorial, we have already loaded Dockstore workflows into the workspace and configured their inputs for this specific tutorial. However, we describe how you can easily import workflows into a Terra workspace in case you want to conduct other analyses with the data in this tutorial. 

1. In your Terra workspace, go to the workflows tab. 
2. Select "Find a Workflow".
![](https://github.com/nhlbidatastage/documentation/blob/master/GWAS-Terra-Tutorial/images/Terra-findworkflows.png?raw=true)
4. At the bottom left, select the Dockstore icon under "Find additional workflows"..
5. This will open the search feature in Dockstore where you can browse easily reproducible workflows that have been written in workflow languages with their associated Docker images and json parameter files.
6. We will find workflows for DataSTAGE projects by clicking the "Organizations" button along the top banner. 

![](https://github.com/nhlbidatastage/documentation/blob/master/GWAS-Terra-Tutorial/images/Dockstore.png?raw=true)
6. Scroll down and click on the DataSTAGE organization. This will display collections of workflows, including the one we use in this tutorial under the collection "Genome Wide Association Study".

![](https://github.com/nhlbidatastage/documentation/blob/master/GWAS-Terra-Tutorial/images/Dockstore-GWAS.png?raw=true)
7. Four workflows will appear. Each one can be exported to Terra by clicking on a single workflow to view its contents, then clicking "Launch with Terra" at the lower right.


![](https://github.com/nhlbidatastage/documentation/blob/master/GWAS-Terra-Tutorial/images/Dockstore-exportTerra.png?raw=true)
8. This will generate a new page asking you to "Select the workspace destination". 
9. Navigate to the workspace you chose and select the workflows tab to check that each workflow was imported successfully.

-----
# Conduct a common variant GWAS in Terra
Now that you have learned how to import data and workflows into a workspace, the next step in this tutorial shows you how to view the data and conduct some initial analyses before performing association tests with the batch workflows. Terra integrates Jupyter notebooks for interactive data analysis.  The next part of this tutorial will walk you through several important data preparation steps for performing a GWAS using a Jupyter notebook.

# Part 2: Explore TOPMed data in a Jupyter Notebook   

For the next step in this tutorial, you will navigate to the notebooks section of workspace and open the **1-GWAS-preliminary-analysis** notebook. This interactive analysis explores the phenotype data and performs several analyses to prepare the data for use in batch association workflows. This notebook will cover the following steps:

1. Use functions that were created to easily reformat TOPMed data in the Gen3 grap format into a single entity that can be loaded as a dataframe in your notebook.
2. Subset the dataframe to include only our traits of interest and remove any individuals that lack data for these traits.
3. Visualize phenotype distributions in a series of plots.
4. Filter genomic data to common variants for statistical power.
5. Perform a principal component analysis ([PCA](https://en.wikipedia.org/wiki/Principal_component_analysis)) to assess if population stratification is detected in your cohort or not. If it is, it should be accounted for in association testing.
6. Generate a genetic relatedness matrix ([GRM](https://hail.is/docs/0.2/methods/genetics.html?highlight=pc_rel#hail.methods.genetic_relatedness_matrix)) for downstream use in association testing.
7. Generate a new "sample_set" data table that holds the derived files we created in the steps above. The files in this data table will be used in the workflows we run in Part 3.     

Genetic analyses in this notebook utilize the [Hail software](https://hail.is/). Hail is a framework for distributed computing with a focus on genetics. Particularly relevant for whole genome sequence ([WGS](https://en.wikipedia.org/wiki/Whole_genome_sequencing)) analysis, Hail allows for efficient, nearly boundless computing (in terms of variant and sample size).    

To facilitate the downstream analysis, this notebook is set up to save output data to the workspace bucket and then write the associated metadata and derived genetic data to the data model using the [FireCloud Service Selector (FISS) package](https://github.com/broadinstitute/fiss).     

For more information on using Terra's data table  see this article on ["Linking data in a Google bucket to the workspace data table"](https://support.terra.bio/hc/en-us/articles/360025758392). 

Once you have successfully completed the 

### Time and cost estimate
You are able to adjust the runtime configuration to fit your computational needs in the Jupyter notebook. We recommend selecting the default environment and selecting the custom profile to use and configure the spark cluster for parallel processing.  Using the suggested profile below and a project with around 1000 samples, running this notebook on this dataset takes about 60 minutes and $1.37 to compute.

![](https://github.com/nhlbidatastage/documentation/blob/master/GWAS-Terra-Tutorial/images/Terra_notebook_configuration.png?raw=true)
 

When working in a notebook that may have compute times over 30 minutes, learn more about Terra's [auto-pause feature](https://support.terra.bio/hc/en-us/articles/360029761352-What-you-need-to-know-about-notebook-auto-pause-) and [how to adjust auto-pause](https://support.terra.bio/hc/en-us/articles/360027570951-Manually-setting-auto-pause-for-notebooks-using-gsutil) for your needs. Please carefully consider how adjusting auto-pause can remove protections that help you from accidentally accumulating cloud costs that you did not need.

-----

# Part 3: Perform mixed-model association tests using workflows
In Part 2, we explored the data we imported from Gen3 and performed a few important steps for preparing our data for association testing. We generated a new "sample_set" data table that holds the files we created in the interactive notebook. These files will be used in our batch workflows that will perform the association tests. Below, we describe the four workflows in this workspace and their cost estimates for running on the sample set we create in this tutorial.  

We have already configured input and output parameters for each workflow in the workflows tab. If you clone the workflows in this tutorial to other Terra workspaces, these parameters will come along. 


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

The final workflow (4-summaryCSV) outputs two csv files with association results (the top candidates and all associations) as well as a png containing summary figures. The **2-GWAS-summarization** notebook is another resource for viewing results of your analyses and the notebook feature allows you to edit for specific use cases.

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

This workspace is a product of the [Manning Lab](https://manning-lab.github.io/) and [NHLBI's BioData Catalyst](https://www.nhlbidatastage.org/), in collaboration with the [Computational Genomics Platform](https://cgpgenomics.ucsc.edu/) at [UCSC Genomics Institute](https://ucscgenomics.soe.ucsc.edu/) and the [Data Sciences Platform](https://www.broadinstitute.org/data-sciences-platform) at [The Broad Institute](https://www.broadinstitute.org/). Contributing authors include:

* [Tim Majarian](mailto:tmajaria@broadinsitute.org) (Manning Lab)
* Alisa Manning (Manning Lab)
* [Beth Sheets](mailto:esheets@ucsc.edu) (UC Santa Cruz Genomics Institute)
*  Michael Baumann (UC Santa Cruz Genomics Institute)

----

### Workspace change log 

| Date | Change | Author | 
| -------  | -------- | -------- |
| Jan 23, 2020 | Remade as template | Beth
| Jan 3, 2020 | Updates from BDC F2F | Beth
| December 3, 2019 | Gen3 updates | Beth |
| November 22, 2019 | Updates from Alisa | Beth |
|  October 22, 2019 | User experience edits from Beri | Beth|