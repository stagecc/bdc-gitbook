---
description: A step-by-step tutorial to help researchers working with Gen3 data in Terra
---

# Getting Started with Gen3 Data on Terra Tutorial

## Overview

This [hands-on tutorial](https://terra.biodatacatalyst.nhlbi.nih.gov/#workspaces/fc-product-demo/BioDataCatalyst-Gen3-data-on-Terra-Tutorial) has been developed to help researchers working with Gen3 data in Terra. The tutorial includes step-by-step instructions to cover the entire analysis process:&#x20;

* How to link your Gen3 and Terra accounts
* How to find and export Gen3 data to a project workspace
* Understanding the structure of Gen3 data in Terra and how to make exported data more familiar
* How to run an interactive analysis in a Jupyter notebook
* How to configure and run a bulk analysis using workflow tools&#x20;

Reading the documentation and following the step-by-step instructions will help familiarize you with Terra. The content on this page is available in a [tutorial workspace](https://terra.biodatacatalyst.nhlbi.nih.gov/#workspaces/fc-product-demo/BioDataCatalyst-Gen3-data-on-Terra-Tutorial) in Terra.

## Tutorial Overview

| 1. Link Gen3 and Terra accounts | 2. Access dataset in Gen3 | 3. Export data to workspace | 4. Consolidate Gen3 data tables | 5. Tidy workspace tables | 6. Analyze data in a notebook | 7. Run a bulk analysis workflow |
| ------------------------------- | ------------------------- | --------------------------- | ------------------------------- | ------------------------ | ----------------------------- | ------------------------------- |
| 2 minutes                       | 3 minutes                 | 10 minutes                  | 20 minutes                      | 2 minutes                | 20 minutes                    | 5 minutes                       |

![Tutorial flow diagram](https://storage.cloud.google.com/terra-featured-workspaces/BioData%20Catalyst/Gen3-data-tutorial-flow.png)

#### A few caveats

* You should run through the steps below **in order**
* Note that you do not have to go through all of the steps in one sitting, only in the correct order
* Time estimates are conservative - many steps will take less time

#### How long does the tutorial take and how much does it cost?

Working through all of the tutorial steps should take just over an hour total (you can break it up and do at different times). The total computation cost of running both notebooks and the workflow will be less than $1.00.

### Science overview

The tutorial models steps typical in a research journey using synthetic Gen3 phenotypic data and public-access 1,000 genomes genomic data. The data are stored in the BDC instance on the Gen3 platform. Phenotypic data are contained in the `lab results` and `demographic` nodes in Gen3 (and corresponding tables in Terra). The data are exported to Terra in the form of fifteen individual data tables connected to each other by UUIDs. The notebook section of the tutorial demonstrates how to select a subset of Gen3 tables you need - based on the data required for your analysis - and consolidate into one table with familiar subject ID conventions. This process of converting Gen3 data to a format that is more intuitive in Terra will be the same no matter what your final analysis. Section 7 covers how to run a bulk analysis workflow on the genomic data exported from Gen3. You would use the same process to do any bulk analysis on genomic data, such as aligning reads or calling variants.&#x20;

### Data disclaimer

The tutorial uses a synthetic, public-access dataset derived from 1,000 Genomes data and stored in the BDC instance in Gen3. For more information about how the synthetic data were generated, see [this workspace](https://terra.biodatacatalyst.nhlbi.nih.gov/#workspaces/amp-t2d-op/2019_ASHG_Reproducible_GWAS-V2).

## Step-by-step Instructions

### Set up tutorial workspace

Estimated time: one minute

Before you begin, you will need to create your own editable copy (clone) of this WORKSPACE to work in.

1. Click on the round circle with three dots in the upper right corner of the workspace.&#x20;
2. Select "Clone" from the dropdown menu.
3. Rename your new workspace something memorable. It may help to write down or memorize the name of your workspace.
4. Choose your billing project (could be free credit).
5. Select the Gen3 BioData Catalyst authorization domain.
6. Click the "Clone Workspace" button to make your own copy. You'll be automatically redirected to your new workspace.
7. Open a second tab of these instructions, to make it easier to follow along.

### Follow-along worksheet

Work from your copy of this workspace following these [step-by-step instructions](https://00f74ba44b74848332b1a9c44be0aefbc4b341dc74-apidata.googleusercontent.com/download/storage/v1/b/terra-featured-workspaces/o/BioData%20Catalyst%2FWorksheet%20-%20Analysing%20BioData%20Catalyst%20Gen3%20Data%20on%20Terra.pdf?jk=AFshE3XFS_QoulNqy6fDmxmh5C2zwjMUPe4SLDU48BDbxAelVTqNAqiV-6SVq9jkM67qiyKRFfxi7wgXsIXdOei9M-4NeQnuKwG0J2kHA8EipcV0LoxM7dB0xhkFhw_j1nSYcXZXi9MX2TR0JZN_53Pxw9Bj-3OF-1fZ63tiVzCE7BWbcqRL_QzyRW93czbwag9vUowKmLVdWFJZKNvrdbUHlnp6teF4q5HZ9bmljZcDjkxbpOcY_2eGASrzB03sRXEh3trGgYUCs7UIsnzVKMCsWmTeBJGwI9CQxpuja-SOAe32nWHWMS3XP959YVRzgFIc4LjjVD5fbEvQ3J751vbYtyx6UKF7uKGoyDtZ_dyIMdaZAGfbjDrDmI7iX0a0AHM_S8AELTPeTJrIOoq_eaFxutKj7CTRA1j_dCnEolujRmLlSD6prTZiyXZRWYnYmf_8SmTzIF5CyDBP2rk2URHVr2ldhjiCngwuXCVS2bZ2lNzGuc8wjCMr5XqS-MT062tU6CuxkzipP28xUGBbkc_kjUeY-7P2zoHqrx_UMc66Vgj8P848ffDMLQLKZpDDsMj1edKN-2OuqgVCeX6a6Z7VvR6j8Tpu0L08AacakLFZGnhPPTN1K_5nelvfymVccLDj40i4Pb598eEzz9stMj-f2ftiSDrnU1WeD1YpTdyPs5R2rImF_-7XP94jJvRgyXSMr9g9ZuQh_Dt44Vgl0TpJU95Lvlvqt20Vswe_0pGouQzYbZRkUDsa_nWZ2Rh0S8_Fyp8juoAIgEC4G9E5JQyPrG-G99l2umY5n44ENWShIgknP69ydHcBbqRRnamdGu4WX0vSSngfl_3_DN-nCZU8-7t4r7AID0izmTIZGSns8RcAhZGIFxjfdunbmJw-8Oovp3-bsd3AhkYbr9FWn54YX4pSmYoZRi3SieISnUgtl46X2an52LKZnTrf6havcQ0SyQob1Z7ATx98AUvAUi5dYdSAxVg9yKyC2-2-YIXFqcRMAC_o1g\&isca=1). You can skim summaries of each step below.

### Step 1. Link your Terra profile with Gen3

Estimated time: 2 minutes

If you haven't linked your Terra and Gen3 accounts yet, you need to follow these [steps](https://support.terra.bio/hc/en-us/articles/360038086332) before you can analyze genomic data from Gen3 inside your Terra workspace.

### Step 2. Access synthetic dataset on Gen3 platform

Estimated time: 5 minutes

This section walks through the process of accessing the public-access tutorial dataset (**tutorial-synthetic\_data\_set\_1**) by going to the [Gen3 platform](https://gen3.biodatacatalyst.nhlbi.nih.gov/).

### Step 3. Export data to workspace

Estimated time: 10 minutes - mostly exporting time

In this step you will practice exporting a Gen3 dataset to Terra. This process will be the same no matter what Gen3 data you are using. As part of this step, you will also learn about the structure of the exported data in a Terra workspace.

### Step 4. Consolidate and format exported Gen3 data

Estimated time: 20 minutes

In this step, you will run the notebook **1-Consolidate-Gen3-data-in-Terra-tutorial**. The tutorial notebook resolves some of the challenges of Gen3 data exported to Terra. In particular, it consolidates the tables that contain phenotypic data into one Terra table and reorganizes the tables and subject IDs to be more familiar. The notebook is also a good introduction to interactive analysis in a Jupyter notebook.

#### **Notebook outline**

* Set up the notebook environment
* Discover all of the metadata available from the Gen3 export
* Define and use a set of custom functions to
  * Merge the metadata in a consolidated Pandas dataframe
  * Reformat a bit of the Gen3 graph language to be more familiar TOPMed nomenclature
  * Push the consolidated dataframe to a workspace data table      &#x20;

### Step 5. Tidy up the consolidated table

Estimated time: 3 minutes

The consolidated table generated in Step 4 has almost 50 columns, including all of the Gen3 metadata from phenotypic data nodes. To help make the table more manageable to read without scrolling left and right, you can select the columns you want to see when you expand the table. This will allow you to focus on the information you need, without having to scroll across tens of columns. Your selections will persist even when you leave the workspace.

### Step 6. Analyze consolidated data ("2-Analyze Gen3 data" notebook)

Estimated time: 15 minutes

In this step you will run the notebook **2-Analyze-consolidated-data-tutorial**, which pulls data from the consolidated table into the notebook environment and does a bit of plotting analysis.

#### **Notebook outline**

* Import the consolidated phenotypic data from the new data table to the notebook compute environment
* This is where you would begin your project-specific analysis (in R or Python). We will explore the data by generating a few plots in the notebook.

### Step 7. Run a workflow on genomic data

Estimated time: 5 minutes

Another mode of analysis in the Terra platform is bulk analysis with workflows. This mode is what you would typically use to do automated analysis steps such as processing genomic data. Bulk analysis uses workflow tools, which you can add to your workspace from another workspace, or by searching Dockstore or the Broad Methods Repository. In this step you will learn how to run a bulk analysis workflow to process genomic data in the the synthetic dataset from the Gen3 platform.

### Next steps and additional resources

Congratulations! You have accessed and analyzed your first Gen3 data in Terra. Now that you have the basics of how to work with Gen3 data, here are some additional BDC and TOPMed resources to explore.

* [**BioData Catalyst Utilities Collection**](https://terra.biodatacatalyst.nhlbi.nih.gov/#workspaces/biodata-catalyst/BioData%20Catalyst%20Collection) workspace: This workspace includes the terra\_data\_util notebook, a notebook for unarchiving tar files, and eventually a vcf merge notebook
* Getting Started with Gen3&#x20;
* GWAS template&#x20;
* TOPMed alignment workflows

### Gen3 data overview

To understand what you will see when you export Gen3 data to a Terra workspace, it helps to first understand how the data is organized in Gen3. A diagram of the graph structure of the synthetic data in Gen3 is below on the left. Each box is a Gen3 data node and each line represents UUIDs connecting the metadata of the two nodes. Administrative nodes are purple, clinical data are in blue boxes, and genomic data are green boxes. When you export a project's data to a Terra workspace, each node in the graph gets imported as its own data table. Your data page will look like the figure on the right. The synthetic data in this tutorial is captured in 15 tables, corresponding to the 15 nodes in the graph structure.

![](broken-reference)

Each data table includes **all of the metadata fields** associated with the Gen3 node, in alphabetical order. The lab\_results table, for example, looks like this:

![Screen shot of demographic table](broken-reference)

You might see from this example several features specific to the Gen3 data structure that can be challenging to work with in Terra:

* There are 15 separate tables from the export - not all of them include data that you will need       &#x20;
  * The phenotypic data we want to use for this tutorial are in two _separate_ tables (`demographic` and `lab_results`)   &#x20;
* The first column in each table is not the subject ID you are used to, is not human-readable, and is not used across levels. Rather, a UUID connects each node to the node directly above it in the graph.         &#x20;
  * The  familiar subject ID (called \`submitter ID in Gen3 tables) is buried (in the 13th column of the lab\_results table, for example)    &#x20;
  * The subject ID is only indirectly connected to the phenotypes in the `lab_results` and `demographics` tables with two different UUIDs (i.e. two separate lines connect their nodes)       &#x20;
* There are 16 columns (metadata fields) in the `lab_results` table, and the five or six we want to include in our analysis aren't easy to pick out because they are far to the right of the table&#x20;

To learn more about the structure of Gen3 data, see [this article](https://support.terra.bio/hc/en-us/articles/360038087312).

### Authors

Workspace author: Allie Hajian\
Notebook code, edits and bug-squashing: Michael Baumann, Beth Sheets

This workspace was completed under the NHLBI BioData Catalyst project.

#### Workspace change log

| Date           | Change        | Author |
| -------------- | ------------- | ------ |
| March 22, 2020 | initial draft | Allie  |
