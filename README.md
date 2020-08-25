---
description: >-
  This is a repository for documentation related to the platforms and services
  that are part of the  NHLBI BioData Catalyst ecosystem.
---

# BioData Catalyst Documentation - Ecosystem Overview

## Welcome to NHLBI BioData Catalyst

Welcome to the NHLBI BioData Catalyst ecosystem and thank you for joining our community of practice. The ecosystem offers secure workspaces to support your data analysis in addition to a number of bioinformatics tools for analysis. The ecosystem currently hosts datasets from the Transomics for Precision Medicine \(TOPMed\) program. There is a lot of information to understand and many resources \(documentation, learning guides, videos, etc.\) available, so we developed this overview to help you get started. If you have additional questions, please use the links at the very end of this document, under the **"Questions"** section, to contact us.

## About NHLBI BioData Catalyst and Our Community

**What is NHLBI BioData Catalyst?**

The NHLBI BioData Catalyst ecosystem is a cloud-based platform providing tools, applications, and workflows in secure workspaces. It is designed to be nimble and responsive to the ever-changing conditions of the biomedical and data science communities. Though the primary goal of the BioData Catalyst project is to build a data science ecosystem, at its core, this is a people-centric endeavor. BioData Catalyst is also building a community of practice working collaboratively to solve technical and scientific challenges.

**What are we doing and why does it matter?**

By increasing access to the NHLBI’s datasets and innovative data analysis capabilities, the NHLBI BioData Catalyst ecosystem accelerates efficient biomedical research that drives discovery and scientific advancement, leading to novel diagnostic tools, therapeutics, and prevention strategies for heart, lung, blood, and sleep disorders.

**Who is developing NHLBI BioData Catalyst?**

The ecosystem is funded by the National Heart, Lung, and Blood Institute \(NHLBI\). Researchers and other professionals receive funding from the NHLBI to work on the development of the ecosystem, together often referred to as “The NHLBI BioData Catalyst Consortium” or “The Consortium” for short. You can find [a list of partners and platforms powering the ecosystem](https://biodatacatalyst.nhlbi.nih.gov/about) on the about page of the project’s website and a [list of the principal investigators](https://bdcatalyst.gitbook.io/biodata-catalyst-documentation/community-conduct/who-we-are) is available in our documentation.

**Learn about our culture.**

The NHLBI BioData Catalyst community follows a [statement of conduct](https://bdcatalyst.gitbook.io/biodata-catalyst-documentation/community-conduct/statement-of-conduct) that reflects the Consortium’s dedication to providing a harassment-free experience for everyone.

**Find out the meanings of our terms and acronyms.**

Like many professional communities, NHLBI BioData Catalyst has adopted terms to help us communicate quickly and more efficiently, but that can be a challenge for newcomers. To help, we created the NHLBI BioData Catalyst [glossary](https://bdcatalyst.gitbook.io/biodata-catalyst-documentation/biodata-catalyst-glossary/bdc_glossary) of terms and acronyms. If ever there is a time when an ecosystem term or acronym is unfamiliar and isn’t in the glossary, please [contact us](https://biodatacatalyst.nhlbi.nih.gov/contact) so we can give you the information and add it to the glossary for future newcomers.

## The NHLBI BioData Catalyst Ecosystem and Services

**Learn about the platforms and services available in the ecosystem.**

The NHLBI BioData Catalyst ecosystem features the following platforms and services.

**Explore Available Data**

* _BioData Catalyst Powered by Gen3_ - Hosts genomic and phenotypic data and enables faceted search for authorized users to create and export cohorts to workspaces in a scalable, reproducible, and secure manner.
* _BioData Catalyst Powered by PIC-SURE_ - Enables access to all clinical data, feasibility queries to be conducted, and allows cohorts to be built in real-time and results to be exported via the API for analysis.

**Analyze Data in Cloud-based Shared Workspaces**

* _BioData Catalyst Powered by Seven Bridges_ - Collaborative workspaces where researchers can find and analyze hosted datasets \(e.g. TOPMed\) by using hundreds of optimized analysis tools \(e.g. Jupyterlab, RStudio\) and workflows \(pipelines\).
* _BioData Catalyst Powered by Terra_ - Secure collaborative place to organize data, run and monitor workflow \(e.g. WDL\) analysis pipelines, and perform interactive analysis using applications such as Jupyter Notebooks and the Hail GWAS tool.

**Use Community Tools on Controlled-access Datasets**

* _Dockstore_ - Catalog of Docker-based workflows \(from individuals, labs, organizations\) that export to Terra or Seven Bridges.

The NHLBI BioData Catalyst website provides further details about the [platforms and services](https://biodatacatalyst.nhlbi.nih.gov/resources/services) available in the ecosystem. We encourage you to create accounts on all the platforms as you get to know BioData Catalyst.

## Ecosystem Access, Hosted Data, and System Services

**How does data access work?**

The BioData Catalyst ecosystem manages access to the hosted controlled data using data access approvals from the NIH Database of Genotypes and Phenotypes \([dbGaP](https://dbgap.ncbi.nlm.nih.gov/aa/wga.cgi?page=login)\). _**Therefore, users who want to access a hosted controlled study on the ecosystem must be approved for access to that study in dbGaP.**_

**How do I login?**

Users log into BioData Catalyst platforms with their eRA Commons credentials and authentication is performed by iTrust. Every time a user logs in, the ecosystem checks his/her user credentials to ensure s/he can only access the data for which s/he has dbGaP approval. 

While all of the platforms within BioData Catalyst use eRA Commons credentials and iTrust performs authorization and authentication, respectively, there are some slight differences between the platforms when getting set up:

* _BioData Catalyst Powered by Gen3_ - Users do not set up usernames on Gen3. Upon the first time logging in, select “Login from NIH”, then enter eRA commons credentials at the prompt. This ‘User Identity’ is used to track the user on the system. 
* _BioData Catalyst Powered by PIC-SURE_ - Similar to Gen3, user identities are used - researchers log into the system by selecting “Log in with eRA Commons.” 
* _BioData Catalyst Powered by Seven Bridges_ - Users set up platform accounts. The first time on the system, users select to “Create an account” and then proceed with entering their eRA Commons credentials. The user is then prompted to fill out a registration form with their name, email, and preferred username. Users are also asked to acknowledge that they have read the Privacy Act notice and then they can proceed to the platform. 
* _BioData Catalyst Powered by Terra_ - Users initially log in using Google credentials and are asked to agree to the Terms of Service and Privacy Act notice. User activity is tracked via the Google credentials, but users can link their eRA Commons credentials to the account to get access to hosted datasets.

Details about how data access works on the NHLBI BioData Catalyst ecosystem are [on the website](https://biodatacatalyst.nhlbi.nih.gov/resources/data/).

**How do I check which data I can access?**

We recommend users first check their access to data before logging in. Do this by going to the [Accessing BioData Catalyst page](https://biodatacatalyst.nhlbi.nih.gov/resources/data/) and clicking on the **“Check My Access”** button. Once you confirm your data access, go to the [Platforms and Services](https://biodatacatalyst.nhlbi.nih.gov/resources/services) page from which you click on the “**Launch**” hyperlink for the platform or service you wish to use. Platforms and services have login/sign in links on their pages that bring you to the pages on which you enter your eRA Commons credentials. [Documentation](https://bdcatalyst.gitbook.io/biodata-catalyst-documentation/data-access/check-my-access-to-data) on checking your access to data is also available.

**What data are available in the ecosystem?**

The NHLBI BioData Catalyst currently hosts a subset of datasets from TOPMed including phs numbers with genomic data and related phs numbers with phenotype data. You can find information about which [TOPMed studies](https://drive.google.com/file/d/1936teBZlvBKbQf1hmdx5JImAxJFbVoIx/view?usp=sharing) are currently hosted on the [Data page](https://biodatacatalyst.nhlbi.nih.gov/resources/data) of the website as well as in the [Release Notes](https://bdcatalyst.gitbook.io/biodata-catalyst-documentation/biodata-catalyst-release-notes/2020-04-02-biodata-catalyst-ecosystem-release-notes).

**Harmonized data available.**

There are limited amounts of harmonized data available at this time. The TOPMed Data Coordinating Center curation team has normalized the patient values for the forty-four \(44\) variables they found are shared across seventeen \(17\) NHLBI studies. Information about the 17 studies and the 44 clinical variables can be found in the [_BioData Catalyst Powered by PIC-SURE User Guide_](https://bdcatalyst.gitbook.io/biodata-catalyst-documentation/explore_data/pic-sure-for-biodata-catalyst-user-guide/harmonized-data).

**Bring your own data and workflows into the system.**

We allow researchers to bring their own data and workflows into the ecosystem to support their analysis needs. Researchers can bring their own datasets into [_BioData Catalyst Powered by Seven Bridges_](https://sb-biodatacatalyst.readme.io/docs/upload-to-the-platform) and [_BioData Catalyst Powered by Terra_](https://bdcatalyst.gitbook.io/biodata-catalyst-documentation/analyze-data/terra/using-your-own-data-with-terra). Users can also bring their own workflows to the system. Users can either add workflows to [Dockstore](https://bdcatalyst.gitbook.io/biodata-catalyst-documentation/analyze-data/dockstore/contribute-to-the-community) in CWL or WDL, or they can [create CWL tools](https://sb-biodatacatalyst.readme.io/docs/about-the-common-workflow-language) directly on _BioData Catalyst Powered by Seven Bridges_ and [develop custom workflows](https://bdcatalyst.gitbook.io/biodata-catalyst-documentation/analyze-data/terra/batch-analysis-with-workflows/bringing-your-own-tools-developing-custom-workflows) for use on _BioData Catalyst Powered by Terra._

**Learn about Genome-wide association study and genetic association testing on BioData Catalyst.**

Walk through our self-paced genome-wide association study and genetic association testing [tutorials](https://bdcatalyst.gitbook.io/biodata-catalyst-tutorials/).

**Share your workflows.**

We encourage users to publish their workflows so they can be used by other researchers working in the NHLBI BioData Catalyst ecosystem. Share your workflows via [Dockstore](https://bdcatalyst.gitbook.io/biodata-catalyst-documentation/analyze-data/dockstore/contribute-to-the-community).

**Costs and cloud credits.**

There is no charge for the storage of the data that is **already available** in the ecosystem. Costs are incurred for computation, the storage of derived results, and the storage of **any new** data uploaded to the BioData Catalyst ecosystem. Cloud credits are available on the system, and you can [learn more here](https://bdcatalyst.freshdesk.com/support/solutions/articles/60000610275-how-much-does-it-cost-to-use-biodata-catalyst-do-you-offer-cloud-credits-).

## Publications About NHLBI BioData Catalyst, Citing Us, and Our Help Desk

**Let us know about your publications and see how you can cite us.**

If you are writing a manuscript about research you conducted using NHLBI BioData Catalyst, please use [the citation available here](https://biodatacatalyst.nhlbi.nih.gov/about#citation) \(scroll to the bottom of the page\).

Immediately after learning your manuscript has been accepted, please email [BDCatalystOutreach@nih.gov](mailto:BDCatalystOutreach@nih.gov) to let us know. Please include in your email the manuscript title, the name of the publication that accepted your manuscript, and information about pre-publication posting \(if it will take place\), along with your name and contact information.

## Questions?

**Learn more, ask questions, or request help.**

Answers to [frequently asked questions](https://biodatacatalyst.nhlbi.nih.gov/faqs/) are available on the website, as are many resources that can be found under [Learn & Support](https://biodatacatalyst.nhlbi.nih.gov/resources/learn). You can also use a form to [Contact Us](https://biodatacatalyst.nhlbi.nih.gov/contact), and if you aren’t sure which selections to make on the form, please see our [help desk directory](https://bdcatalyst.freshdesk.com/support/solutions/articles/60000666868-where-do-i-direct-my-question-regarding-biodata-catalyst-and-the-help-desk-).

