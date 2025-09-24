---
description: >-
  How to get started with PIC-SURE and the common endpoints you can use to query
  any resource registered with PIC-SURE
---

# PIC-SURE API Documentation

The PIC-SURE v2 API is a meta-API used to host any number of resources exposed through a unified set of generalized operations.

&#x20;PIC-SURE Repositories:

* [PIC-SURE API](https://github.com/hms-dbmi/pic-sure): This is the repository for version 2+ of the PIC-SURE API.
* [PIC-SURE Wiki](https://github.com/hms-dbmi/pic-sure/wiki): This is the wiki page for version 2+ of the PIC-SURE API.
* [BioData Catalyst PIC-SURE](https://github.com/hms-dbmi/biodatacatalyst-pic-sure): This is the repository for the BDC environment of PIC-SURE.
* [PIC-SURE-ALL-IN-ONE](https://github.com/hms-dbmi/pic-sure-all-in-one): This is the repository for PIC-SURE-ALL-IN-ONE.

Additional PIC-SURE Links:

* [DCPPC Presentation on PIC-SURE as a meta-API](https://docs.google.com/presentation/d/16UpSrbGsF_kDTf0JMDVa86ZlXRxcQfy83YTs8gJCxPg/edit#slide=id.g416d2825d2_0_487)
* [Avillachlab-Jenkins Repository](https://github.com/hms-dbmi/avillachlab-jenkins): A link to the Avillach Lab Jenkins repository.
* [Avillachlab-Jenkins Dev Release Control](https://github.com/hms-dbmi/avillachlab-jenkins-dev-release-control): A repository for Avillach Lab Jenkins development release control.

## Client Libraries

The following are the collected client libraries for the entire PIC-SURE project.

* [R Client Library](https://github.com/hms-dbmi/pic-sure-r-client)
* [Python Client Library](https://github.com/hms-dbmi/pic-sure-python-client)

## PIC-SURE User Interface

The PIC-SURE User Interface acts as a visual aid for running normal queries of resources through PIC-SURE.

PIC-SURE User Interface Repositories:

* [PIC-SURE HPDS UI](https://github.com/hms-dbmi/pic-sure-hpds-ui): The main High Performance Data Store (HPDS) UI repository.

Additional PIC-SURE User Interface Links:

* [PIC-SURE UI Flow](https://docs.google.com/drawings/d/1nNvzvQOVLVU49oM2tYWG7FcK1gZOkdJO-2dv2JaWz0w/edit?usp=sharing): Links to a google drawing of the PIC-SURE UI flow.

## PIC-SURE Auth Micro-App (PSAMA)

The PSAMA component of the PIC-SURE ecosystem authorizes and authenticates all actions taken within PIC-SURE.

PSAMA Repos:

* [PIC-SURE Auth MicroApp Repository](https://github.com/hms-dbmi/pic-sure-auth-microapp)

Additional PSAMA Links:

* [PSAMA Core Logic](https://github.com/hms-dbmi/pic-sure-auth-microapp/tree/master/pic-sure-auth-services/src/main/java/edu/harvard/hms/dbmi/avillach/auth): This is where the core of the PSAMA application is stored in GitHub

## High Performance Data Store (HPDS)

HPDS is a datastore designed to work with the PIC-SURE meta-API. It grants researchers fast, dependable access to static datasets and the ability to produce statistics-ready dataframes filtered on any variable they choose at any time.

HPDS Repositories:

* [PIC-SURE HPDS](https://github.com/hms-dbmi/pic-sure-hpds): The main HPDS repository.
* [PIC-SURE HPDS Python Client](https://github.com/hms-dbmi/pic-sure-python-adapter-hpds): Python client library to run queries against a PIC-SURE HPDS resource.
* [PIC-SURE HPDS R Client](https://github.com/hms-dbmi/pic-sure-r-adapter-hpds): R client library to run queries against a PIC-SURE HPDS resource.
* [PIC-SURE HPDS UI](https://github.com/hms-dbmi/pic-sure-hpds-ui): The main HPDS UI repository.
* [HPDS Annotation](https://github.com/bch-gnome/hpds_annotation): This repository describes steps to prepare and annotate VCF files for loading into HPDS.
