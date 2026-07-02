# Data Dictionaries via PIC-SURE API

The PIC-SURE API can be used to extract the data dictionary. This can be done regardless of authorization to access data and can be done with one, multiple, or all studies.

## Descriptions of Fields in PIC-SURE Data Dictionary

Note that there are several types of studies available in PIC-SURE:

1. dbGaP format compliant: ingested by dbGaP in the dbGaP recommended format ([https://www.ncbi.nlm.nih.gov/gap/docs/submissionguide/](https://www.ncbi.nlm.nih.gov/gap/docs/submissionguide/))
2. dbGaP ingested, but not format-compliant
3. Not ingested by dbGaP: are not format-compliant and do not have a study accession (phs number)

### PIC-SURE Data Dictionary Fields

* **conceptPath**: The concept path used to uniquely identify a variable when exported to users. For more information about concept paths and data organization, please refer to the [Data Organization in BDC-PIC-SURE page](https://pic-sure.gitbook.io/nhlbi-biodata-catalyst-powered-by-pic-sure/data-in-pic-sure/data-organization-in-bdc-pic-sure).&#x20;
* **name**: ID associated with the variable. For studies in dbGaP format, this is provided as “phvXXXXXXXX”. Non-compliant studies instead have a short text ID provided that can be a duplicate of the "display" field.
* **display:** A short text ID associated with a variable. These are often not human-readable as they are mostly derived from the column names in datasets. For non-compliant studies, this can be a duplicate of the "name" field.
* **description**: A text field with a human-readable description of the variable.&#x20;
* **dataType:** Describes the data type of the variable, either "Categorical" (set of discrete values) or "Continuous" (numeric).&#x20;
* **studyId**: ID associated with a study. For dbGaP-assosciated studies this is in the format phsxxxxxx. Non-dbGaP studies can be in other formats. The field is consistent with the DBGAP ACCESSION NUMBER in BDC Powered by Gen3.
* **values**: An array of all unique values included for the variable.
* **min**: Field generated internally for use in the PIC-SURE user interface elements for specific studies. Describes the minimum associated with continuous variables.&#x20;
* **max**: Fields generated internally for use in the PIC-SURE user interface elements for specific studies. Describes the maximum associated with continuous variables.
* **allowFiltering:** boolean True/False value that determines whether a variable is able to be filtered in Open PIC-SURE. A value of False means that the variable is not filterable in Open PIC-SURE. For further information about stigmatizing variables, please refer to this documentation: [https://github.com/hms-dbmi/biodata\_catalyst\_stigmatizing\_variables/tree/main](https://github.com/hms-dbmi/biodata_catalyst_stigmatizing_variables/tree/main)
* **studyAcronym**: Abbreviation of the study name, such as "FHS" for Framingham Heart Study.
