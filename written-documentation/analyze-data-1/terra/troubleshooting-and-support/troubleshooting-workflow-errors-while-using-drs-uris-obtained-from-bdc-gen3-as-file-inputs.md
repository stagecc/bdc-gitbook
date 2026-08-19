---
description: >-
  This troubleshooting guide addresses issues that researchers could encounter
  while using BDC-hosted data (accessed as DRS URIs) as inputs to WDL workflows
  on BDC-Terra.
---

# Troubleshooting Workflow Errors  While Using DRS URIs Obtained from BDC-Gen3 as File Inputs

This troubleshooting guide supplements the [How to troubleshoot failed workflows](https://support.terra.bio/hc/en-us/articles/360027920592-How-to-troubleshoot-failed-workflows) support page with BDC-specific guidance related to using BDC-hosted data (represented as DRS URI file links) as workflow file inputs. DRS URIs are file links to the BDC-hosted data stored on BDC-Gen3. These troubleshooting steps could be the most useful when a workflow fails immediately after submission with errors related to missing or inaccessible data files, or produces HTTP errors such as 400 (Bad Request) or 404 (Not Found). The scenarios covered here focus on resolving problems related to incorrect or outdated DRS URIs, expired or missing external identity links, and insufficient data access permissions.

## Scenario 1 — Error observed: "400: Bad Request when accessing controlled DRS data"

**What could have happened:**

* Terra account is not linked to the required external identity.
* The authorization link to the external identity has expired.
* The workflow configuration is incorrect, such as a typo in the input attribute name.
* The linked identity does not have access to the requested dataset.

**Possible solutions:**

* Link the required external identity in Terra.
* Renew the expired authorization link.
* Check the workflow input configuration and confirm the attribute name is correct.
* Request access to the dataset, or use a DRS URI for data you are authorized to access.

## Scenario 2 — Error observed: "404: DRS URI not found"

**What could have happened:**

* The DRS URI contains a typo.
* The DRS URI no longer resolves because the referenced file identifier is outdated.
* The DRS data provider is unavailable or not functioning properly.

**Possible solutions:**

* Copy the DRS URI directly from the Terra data table instead of entering it manually.
* Re-export or refresh the file references from Gen3 to get the current DRS URIs.
* Verify that the external account link is active and try unlinking and re-linking if needed.
* Check whether the DRS data provider is currently available.

## Troubleshooting Steps

### Step 1: Verify that the workflow is using the correct DRS URI

#### Why this matters

Workflow file inputs can be defined by file paths or by data tables. If a workflow fails immediately, Terra often could not locate or access an input file. This can happen if the workflow input points to the wrong table attribute, if the DRS URI was entered incorrectly, or if access to the referenced file failed.

#### Example error message

<img src="../../../../.gitbook/assets/unknown (1).png" alt="" height="372" width="624">

**To resolve this issue if the workflow input points to the wrong table attribute or if the DRS URI was entered incorrectly:**

1. Log into Terra.
2. Open the workspace and go to the data table that contains the file reference.
3. Locate the DRS URI for the input file.
4. Copy the DRS URI directly from the table instead of entering it manually.

<img src="../../../../.gitbook/assets/unknown (2).png" alt="" height="328" width="624">

5. If the workflow input comes from a table, confirm that the workflow input attribute name exactly matches the table column name.

<img src="../../../../.gitbook/assets/unknown (3).png" alt="" height="348" width="624">

6. Re-run the workflow with the corrected input.

***

### Step 2: Verify that the required external identity is linked and active

#### Why this matters

Accessing BDC-hosted data with DRS URIs on BDC-Terra requires an active external identity link to NHLBI BioData Catalyst Framework Services. These links expire after 15 days.

#### Example error message

<img src="../../../../.gitbook/assets/unknown (4).png" alt="" height="400" width="624">

**To resolve this issue:**

1. Log in to Terra.
2. Open Profile > External Identities.

<img src="../../../../.gitbook/assets/unknown (5).png" alt="" height="373" width="624">

3. Confirm that the NHLBI BioData Catalyst Framework Services account link is not expired.

<img src="../../../../.gitbook/assets/unknown (6).png" alt="" height="391" width="624">

4. If the account is not linked then log into the NHLBI BioData Catalyst Framework Services. If the link is expired, then renew the NHLBI link.
5. Re-run the workflow.

***

### Step 3: Verify that your linked identity has access to the dataset in BDC-Gen3

#### Why this matters

A linked external identity is not enough by itself; that identity must also be authorized for the dataset you are trying to access. BDC documentation says to verify access in BDC-Gen3 under the Exploration tab using the Data Access panel, with Data with Access selected. ([Checking Access | BDC Documentation](https://bdcatalyst.gitbook.io/biodata-catalyst-documentation/written-documentation/data-access/check-my-access-to-data))

#### Example error message

<img src="../../../../.gitbook/assets/unknown (7).png" alt="" height="395" width="624">



**To resolve this issue:**

1. Log in to BDC-Gen3 using your NIH credentials.
2. Open the Profile tab.

<img src="../../../../.gitbook/assets/unknown (8).png" alt="" height="359" width="624">

3. Verify your project of interest shows up on the projects list.
4. If it does not, request access through the appropriate data access process before re-running the workflow.

**Related resources**

[Exploration | BDC Documentation](https://bdcatalyst.gitbook.io/biodata-catalyst-documentation/written-documentation/explore-available-data/gen3-discovering-data/exploration)

***

### Step 4: Refresh outdated DRS URIs after a new export or release

#### Why this matters

If a DRS URI no longer resolves, the referenced file identifier may be outdated. Terra’s DRS troubleshooting guidance specifically recommends verifying the external link and confirming that the DRS provider is functioning properly.

#### Example error message

<img src="../../../../.gitbook/assets/unknown (9).png" alt="" height="372" width="624">

**To resolve this issue:**

1. Return to BDC-Gen3 and confirm that the GUID is not the same as your previous file’s DRS URI, located in the ga4gh\_drs\_uri column in the data table in your workspace.

<img src="../../../../.gitbook/assets/unknown (26).png" alt="" height="235" width="624">

<img src="../../../../.gitbook/assets/unknown (27).png" alt="" height="317" width="624">

2. If the DRS URI and GUID do not match, locate the file in BDC-Gen3.
3. Make sure that the GUID in the file matches the DRS URI you will use in your workflow.

<img src="../../../../.gitbook/assets/unknown (28).png" alt="" height="291.35562675021697" width="624">

<img src="../../../../.gitbook/assets/unknown (29).png" alt="" height="317" width="624">

4. Prepare the more recent file in Gen3 for export to a Terra workspace.
5. Update the workflow inputs with the updated DRS URIs.
6. Re-run the workflow.

## **Related resources**

[How to access controlled data on external servers (i.e., Gen3)](https://support.terra.bio/hc/en-us/articles/360038086332-How-to-access-controlled-data-on-external-servers-i-e-Gen3)

[How to use DRS URIs in a workflow (GCP)](https://support.terra.bio/hc/en-us/articles/6635144998939-How-to-use-DRS-URIs-in-a-workflow-GCP)

[How to access data with DRS URIs](http://support.terra.bio/hc/en-us/articles/6635247495579-How-to-access-data-with-DRS-URIs)

[Overview: Interoperable data (GA4GH DRS URIs)](https://support.terra.bio/hc/en-us/articles/360039330211-Overview-Interoperable-data-GA4GH-DRS-URIs)

[Exploration | BDC Documentation](https://bdcatalyst.gitbook.io/biodata-catalyst-documentation/written-documentation/explore-available-data/gen3-discovering-data/exploration)
