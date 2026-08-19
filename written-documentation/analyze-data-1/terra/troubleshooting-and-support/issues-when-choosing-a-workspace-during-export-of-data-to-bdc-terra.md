---
description: >-
  This troubleshooting guide is for the specific situation where a workspace
  does not appear as an option under the “Select an Existing Workspace” when
  exporting controlled-access data into BDC-Terra.
---

# Issues When Choosing a Workspace During Export of Data to BDC-Terra

The scenario covered in this troubleshooting guide typically occurs when the selected workspace does not meet the security and compliance requirements required for controlled-access data. The steps below focus on verifying that Secure Monitoring is enabled in the workspace so that the workspace is eligible to receive controlled-access datasets.

## Steps to troubleshoot

Step 1: Confirm that the workspace has Secure Monitoring enabled. If not, create a new workspace.

## Why this matters

BDC-Terra workspaces that do not have Secure Monitoring enabled are not eligible to receive controlled-access data from BDC-Gen3 or BDC-PIC-SURE. As a result, workspaces for which Secure Monitoring was not enabled at the will not appear in the destination workspace dropdown during data export.

Note: Secure Monitoring cannot be enabled retroactively on an existing workspace. If a workspace was created without Secure Monitoring, a new workspace must be created to meet the requirements for analyzing BDC-hosted data.

## Diagnosing the problem

1. When exporting controlled-access data from BDC-Gen3 or BDC-PIC-SURE into Terra, there is the option to select an existing workspace.

<figure><img src="../../../../.gitbook/assets/image (60).png" alt=""><figcaption></figcaption></figure>

When this option is chosen, there is a dropdown menu of BDC-Workspaces. These are workspaces to which the logged-in user can write. The problem occurs when an existing Terra workspace is not listed in the dropdown menu.

<img src="../../../../.gitbook/assets/unknown (23).png" alt="" height="391" width="624">

2. The logged-in user should navigate to the workspace on BDC-Terra and confirm whether or not the workspace was created with Secure Monitoring enabled. Workspaces with Secure Monitoring enabled will have a shield icon in the top right corner of the workspace.

<figure><img src="../../../../.gitbook/assets/image (59).png" alt=""><figcaption></figcaption></figure>

## To resolve this issue

1. Create a new Terra workspace, either before the data export begins or while importing data into a new workspace.

<img src="../../../../.gitbook/assets/unknown (24).png" alt="" height="391" width="624">

2. During workspace creation, make sure the Enable Secure Monitoring button is toggled on. (Note: if exporting data from Gen3, the workspace will automatically come with the Enable Secure Monitoring button toggled on and it cannot be toggled off.)

<img src="../../../../.gitbook/assets/unknown (25).png" alt="" height="395" width="624">

Still have questions? [Contact us!](https://biodatacatalyst.nhlbi.nih.gov/help-and-support/contact-us/)
