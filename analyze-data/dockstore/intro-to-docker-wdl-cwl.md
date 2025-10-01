---
description: Technologies for reproducible analysis in the cloud
---

# Intro to Docker, WDL, CWL

## Introduction to Docker

Docker is a fantastic tool for creating light-weight containers to run your tools. It gives you a fast, VM-like environment for Linux where you can automatically install dependencies, make configurations, and setup your tool exactly the way you want, just as you would on a “normal” Linux host. You can then quickly and easily share these Docker images with the world using registries like Quay.io (indexed by Dockstore), Docker Hub, and GitLab.&#x20;

[Learn how to create a Docker image ](https://docs.dockstore.org/en/develop/getting-started/getting-started-with-docker.html)

## Introduction to Workflow Languages

There are multiple workflow languages currently available to use with docker technology. In the BioData Catalyst ecosystem, SevenBridges uses CWL and Terra uses WDL. To learn more about how these language compare and differ, read Dockstore's documentation on [tools](https://docs.dockstore.org/en/develop/getting-started/dockstore-tools.html) and [workflows](https://docs.dockstore.org/en/develop/getting-started/dockstore-workflows.html).&#x20;

Once you have picked what language works best for you, prepare your pipeline for analysis in the cloud with these tutorials aimed at bioinformaticians:

[Learn how to create a tool in Common Workflow Language (CWL](https://docs.dockstore.org/en/develop/getting-started/getting-started-with-cwl.html))&#x20;

[Learn how to create a tool in Workflow Descriptor Language (WDL](https://docs.dockstore.org/en/develop/getting-started/getting-started-with-wdl.html))

## Best Practices for Secure and FAIR Workflows

Dockstore’s integration with BioData Catalyst allows researchers the ability to easily launch reproducible tools and workflows in secure workspace environments for use with sensitive data. This privilege to work with sensitive data requires assurances of safe software.&#x20;

We believe we can enhance the security and reliability of tools and workflows through open, community-driven best practices that exemplify the FAIR (Findable, Accessible, Interoperable, Reusable) guiding principles. We have established a best practices framework for [secure and FAIR workflows](https://docs.dockstore.org/en/develop/advanced-topics/best-practices/best-practices-secure-fair-workflows.html) published in Dockstore. We ask that users try to implement these practices for all workflows they develop.\
