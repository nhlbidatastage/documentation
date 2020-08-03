# PIC-SURE API Documentation

The PIC-SURE v2 API is a meta-api used to host any number of resources exposed through a unified set of generalized operations. The following document explains how to get started with PIC-SURE and the common endpoints you can use to query any resource registered with PIC-SURE.

 PIC-SURE Repositories:

* [PIC-SURE API](https://github.com/hms-dbmi/pic-sure): This is the repository for version 2+ of the PIC-SURE API.
* [PIC-SURE Wiki](https://github.com/hms-dbmi/pic-sure/wiki): This is the wiki page for version 2+ of the PIC-SURE API.
* [BioData Catalyst PIC-SURE](https://github.com/hms-dbmi/biodatacatalyst-pic-sure): This is the repository for the BioData Catalyst environment of PIC-SURE.
* [PIC-SURE-ALL-IN-ONE](https://github.com/hms-dbmi/pic-sure-all-in-one): This is the repository for PIC-SURE-ALL-IN-ONE.

Additional PIC-SURE Links:

* [PIC-SURE v2 API Reference Document](https://docs.google.com/document/d/1xVXRYJ1mpoaoiOxyZ8xZ56J_ZUn86hsfrh-ycoZfPRo/edit#heading=h.lypfpc292myo): This Google document contains important reference information about the PIC-SURE v2 API.
* [PIC-SURE FENCE Integration Document](https://docs.google.com/document/d/14XGD-0lZUdnCVPzuep35U5GRElIlx3MqeMHfqGYbigU): This document contains information concerning the Fence authentication and authorization service.
* [DCPPC Presentation on PIC-SURE as a meta-API](https://docs.google.com/presentation/d/16UpSrbGsF_kDTf0JMDVa86ZlXRxcQfy83YTs8gJCxPg/edit#slide=id.g416d2825d2_0_487)
* [Avillachlab-Jenkins Repository](https://github.com/hms-dbmi/avillachlab-jenkins): A link to the Avillach Lab Jenkins repository.
* [Avillachlab-Jenkins Dev Release Control](https://github.com/hms-dbmi/avillachlab-jenkins-dev-release-control): A repository for Avillach Lab Jenkins development release control.

## PIC-SURE User Interface

The PIC-SURE User Interface acts as a visual aid for running normal queries of resources through PIC-SURE.

PIC-SURE User Interface Repositories:

* [PIC-SURE HPDS UI](https://github.com/hms-dbmi/pic-sure-hpds-ui): The main High Performance Data Store \(HPDS\) UI repository.

Additional PIC-SURE User Interface Links:

[PIC-SURE UI Flow](https://docs.google.com/drawings/d/1nNvzvQOVLVU49oM2tYWG7FcK1gZOkdJO-2dv2JaWz0w/edit?usp=sharing): Links to a google drawing of the PIC-SURE UI flow.

## PIC-SURE Auth Micro-App \(PSAMA\)

The PSAMA component of the PIC-SURE ecosystem authorizes and authenticates all actions taken within PIC-SURE.

PSAMA Repos:

* [PIC-SURE Auth MicroApp Repository](https://github.com/hms-dbmi/pic-sure-auth-microapp)

Additional PSAMA Links:

* [PSAMA Core Logic](https://github.com/hms-dbmi/pic-sure-auth-microapp/tree/master/pic-sure-auth-services/src/main/java/edu/harvard/hms/dbmi/avillach/auth): This is where the core of the PSAMA application is stored in GitHub
* [Token Introspection Process in PSAMA](https://docs.google.com/document/d/1Hug2z2P6XKBqkcVNervAdXxm66LOThuTt5_PUv9CjA0/edit#heading=h.q15h874f7kvq): This Google document goes over the details of the token introspection process.

## High Performance Data Store \(HPDS\)

HPDS is a datastore designed to work with the PIC-SURE meta-API. It grants researchers fast, dependable access to static datasets and the ability to produce statistics ready dataframes filtered on any variable they choose at any time.

HPDS Repositories:

* [PIC-SURE HPDS](https://github.com/hms-dbmi/pic-sure-hpds): The main HPDS repository.
* [PIC-SURE HPDS Python Client](https://github.com/hms-dbmi/pic-sure-python-adapter-hpds): Python client library to run queries against a PIC-SURE HPDS resource.
* [PIC-SURE HPDS R Client](https://github.com/hms-dbmi/pic-sure-r-adapter-hpds): R client library to run queries against a PIC-SURE HPDS resource.
* [PIC-SURE HPDS UI](https://github.com/hms-dbmi/pic-sure-hpds-ui): The main HPDS UI repository.
* [HPDS Annotation](https://github.com/bch-gnome/hpds_annotation): This repository describes steps to prepare and annotate VCF files for loading into HPDS.

Additional HPDS Links:

* [Loading HPDS Data for PL-Biobank](https://docs.google.com/document/d/1BDtesMWtXLYe7qtxl_s3K5nN2lJW21yVPhyabonTeRM/edit#): Details how to do an ETL \(Extract, Transform, Load\) of genotype and phenotype data into HPDS.
* [pic-sure-hpds-nhanes](https://github.com/hms-dbmi/pic-sure-hpds-phenotype-load-example): An example HPDS environment load with a subset of the NHANES data.
* [pic-sure-hpds-genotype-load-example](https://github.com/hms-dbmi/pic-sure-hpds-genotype-load-example): An HPDS genotype load example.
* [Access-to-Data-using-PIC-SURE-API](https://github.com/hms-dbmi/Access-to-Data-using-PIC-SURE-API): Provides data access for users of PIC-SURE-All-In-One.

## Client Libraries

The following are the collected client libraries for the entire PIC-SURE project.

* [R Client Library](https://github.com/hms-dbmi/pic-sure-r-client)
* [Python Client Library](https://github.com/hms-dbmi/pic-sure-python-client)

## ETL - Extract, Transform, Load

The following are instructions to load data into HPDS. It contains all the scripts necessary to create the new table, generate mapping data, and extract data for HPDS to load.

* [i2b2 ACT to HPDS](https://github.com/hms-dbmi/i2b2ACTtoHPDS/tree/master/Latest)

