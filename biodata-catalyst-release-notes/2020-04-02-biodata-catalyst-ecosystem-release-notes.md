# 2020-04-02 BioData Catalyst Ecosystem Release Notes

### **Introduction**

The 2020-04-02 release marks the first significant release for the NHLBI BioData Catalyst ecosystem. This release offers an integrated system of [platforms and services](https://biodatacatalyst.nhlbi.nih.gov/resources/services) for researchers to search metadata of hosted datasets, find data files, and analyze data files in workspace environments which support a variety of different analysis modalities. 

The hosted data for this release includes TOPMed multi-sample VCF data for ~55,000 sequenced participants within 32 TOPMed studies included in [Freeze 5b as well as CRAM files for those participants. In addition, this release includes raw phenotype files](https://www.nhlbiwgs.org/topmed-whole-genome-sequencing-project-freeze-5b-phases-1-and-2#Summary5b) for participants in TOPMed studies, providing clinical information such as BMI and lipids levels. In some cases, these data are in different dbGaP accessions than the genomic data. The hosted data is stored in both Amazon Web Services and Google Cloud and users have the option to run computation on either cloud provider. To access the hosted TOPMed data on BioData Catalyst, users must have dbGaP approval. Please refer to the [Data page](https://biodatacatalyst.nhlbi.nih.gov/resources/data) on the BioData Catalyst website for more information.

For more in depth information please see the "List of significant new features" below.

### **List of significant new features**

The following features in this release support primarily TOPMed researchers ranging in technical skills \(both command-line and GUI\) and with approval for the controlled TOPMed studies in dbGaP:

* **System login and data access:** Researchers can log into the BioData Catalyst platforms using their eRA Commons ID. Approvals for TOPMed studies in dbGaP are recognized by the platforms. 
* **Search TOPMed phenotypic data:** Create cohorts on PIC-SURE by searching and selecting phenotypic variables of interest from dbGaP and then export cohorts to Seven Bridges or Terra for use in analysis workspaces. Users can also explore the TOPMed phenotype variables harmonized by the TOPMed Data Coordinating Center.  
* **Find and access TOPMed genomics files, raw phenotype data files, and reference data files:** Use the Explorer feature on Gen3 and the Data Browser feature on Seven Bridges.  
* **Bring your own data:** Use one of several options to upload/import data files to the workspace environments.
* **Run analyses at Scale:** Analyze thousands of samples at once using batch processing capabilities in secure workspaces. Ability to run computation on Google Cloud and Amazon Web Services. Utilize visual user interface, Jupyterlab Notebooks and Jupyter Notebooks, RStudio, API, and command line.
* **Association studies:** Execute single variant and multiple variant association studies utilizing the GENESIS pipelines, Hail, and others. Utilize Annotation Explorer to create variant grouping files for multiple variant association studies. 
* **Collaborate with other users:** Share workspaces, files, and tools with other BioData Catalyst users. 
* **Documentation:** Access documentation for each of the platforms.
* **Track cloud costs:** Track cloud storage and compute costs on Seven Bridges and Terra.

**Data Releases**  


| **Hosted TOPMed study accessions with genomic data from Freeze 5b** |  |  |
| :--- | :--- | :--- |
| **Study Name** | **Acronym** | **phs I.D. \#** |
| **NHLBI TOPMed: Genetics of Cardiometabolic Health in the Amish** | **Amish** | **phs000956** |
| **NHLBI TOPMed: Atherosclerosis Risk in Communities** | **ARIC** | **phs001211** |
| **NHLBI TOPMed: The Genetics and Epidemiology of Asthma in Barbados** | **BAGS** | **phs001143** |
| **NHLBI TOPMed: Cleveland Clinic Atrial Fibrillation Study** | **CCAF** | **phs001189** |
| **NHLBI TOPMed: The Cleveland Family Study** | **CFS** | **phs000954** |
| **NHLBI TOPMed: Cardiovascular Health Study** | **CHS** | **phs001368** |
| **NHLBI TOPMed: Genetic Epidemiology of COPD** | **COPDGene** | **phs000951** |
| **NHLBI TOPMed: The Genetic Epidemiology of Asthma in Costa Rica** | **CRA** | **phs000988** |
| **NHLBI TOPMed: Diabetes Heart Study** | **DHS** | **phs001412** |
| **NHLBI TOPMed: Boston Early-Onset COPD Study** | **EOCOPD** | **phs000946** |
| **NHLBI TOPMed: Framingham Heart Study** | **FHS** | **phs000974** |
| **NHLBI TOPMed: Genes-Environments and Admixture in Latino Asthmatics** | **GALAII** | **phs000920** |
| **NHLBI TOPMed: Genetic Study of Atherosclerosis Risk** | **GeneSTAR** | **phs001218** |
| **NHLBI TOPMed: Genetic Epidemiology Network of Arteriopathy** | **GENOA** | **phs001345** |
| **NHLBI TOPMed: Genetic Epidemiology Network of Salt Sensitivity** | **GenSalt** | **phs001217** |
| **NHLBI TOPMed: Epigenetic Determinants of Lipid Response to Dietary Fat and Fenofibrate** | **GOLDN** | **phs001359** |
| **NHLBI TOPMed: Heart and Vascular Health Study** | **HVH** | **phs000993** |
| **NHLBI TOPMed: Genetics of Left Ventricular Hypertrophy** | **HyperGEN** | **phs001293** |
| **NHLBI TOPMed: The Jackson Heart Study** | **JHS** | **phs000964** |
| **NHLBI TOPMed: Whole Genome Sequencing of Venous Thromboembolism** | **Mayo\_VTE** | **phs001402** |
| **NHLBI TOPMed: The Multi-Ethnic Study of Atherosclerosis** | **MESA** | **phs001416** |
| **NHLBI TOPMed: Massachusetts General Hospital \(MGH\) Atrial Fibrillation Study** | **MGH\_AF** | **phs001062** |
| **NHLBI TOPMed: Partners HealthCare Biobank** | **Partners** | **phs001024** |
| **NHLBI TOPMed: San Antonio Family Heart Study** | **SAFS** | **phs001215** |
| **NHLBI TOPMed: Study of African Americans, Asthma, Genes and Environment** | **SAGE** | **phs000921** |
| **NHLBI TOPMed: African American Sarcoidosis Genetics Resource** | **Sarcoidosis** | **phs001207** |
| **NHLBI TOPMed: Genome-wide Association Study of Adiposity in Samoans** | **SAS** | **phs000972** |
| **NHLBI TOPMed: Rare Variants for Hypertension in Taiwan Chinese** | **THRV** | **phs001387** |
| **NHLBI TOPMed: The Vanderbilt Atrial Fibrillation Ablation Registry** | **VAFAR** | **phs000997** |
| **NHLBI TOPMed: The Vanderbilt Atrial Fibrillation Registry** | **VU\_AF** | **phs001032** |
| **NHLBI TOPMed: The Women's Genome Health Study** | **WGHS** | **phs001040** |
| **NHLBI TOPMed: Women's Health Initiative** | **WHI** | **phs001237** |

| **Hosted TOPMed study accessions with phenotype data**   |  |  |
| :--- | :--- | :--- |
| **Study Name** | **Acronym** | **phs I.D. \#** |
| **Atherosclerosis Risk in Communities** | **ARIC** | **phs000280** |
| **Cleveland Clinic Atrial Fibrillation Study** | **CCAF** | **phs000820** |
| **The Cleveland Family Study** | **CFS** | **phs000284** |
| **Cardiovascular Health Study** | **CHS** | **phs000287** |
| **Genetic Epidemiology of COPD** | **COPDGene** | **phs000179** |
| **Framingham Heart Study** | **FHS** | **phs000007** |
| **Genes-Environments and Admixture in Latino Asthmatics** | **GALAII** | **phs001180** |
| **Genetic Study of Atherosclerosis Risk** | **GENESTAR** | **phs001074** |
| **Genetic Epidemiology Network of Arteriopathy** | **GENOA** | **phs001238** |
| **Genetic Epidemiology Network of Salt Sensitivity** | **GENSALT** | **phs000784** |
| **Heart and Vascular Health Study** | **HVH** | **phs001013** |
| **The Jackson Heart Study** | **JHS** | **phs000286** |
| **The Multi-Ethnic Study of Atherosclerosis** | **MESA** | **phs000209** |
| **Massachusetts General Hospital \(MGH\) Atrial Fibrillation Study** | **MGH\_AF** | **phs001001** |
| **Women's Health Initiative** | **WHI** | **phs000200** |

Information on the status of data releases is forthcoming.

#### **For detailed platform release notes please consult the following resources:**

* Gen3 release notes 
* [Terra release notes](https://support.terra.bio/hc/en-us/categories/360000693572)
* [Seven Bridges release notes](https://sb-biodatacatalyst.readme.io/blog)
* PIC-SURE release notes
* [Dockstore release notes](https://docs.dockstore.org/en/develop/changelog.html)



