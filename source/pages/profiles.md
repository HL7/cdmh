---
title: Mappings and Profiles for the IG
layout: default
active: profiles
---
### Mappings

This section contains the mappings between the various CDMs, BRIDG and the FHIR Resources/profiles. In each mapping the CDM data element is mapped to the appropriate BRIDG data element and the FHIR Data Element. The column FHIR Resource/Profile/Extension identifies the specific profile and/or extension if one exists. If the profiles do not exist then they are mapped to the resource. New profiles and extensions will be added where necessary as the pilot implementations provide feedback through the ballot process.

### Mapping Conventions Used

The mappings use the US Core profiles leverages US Core profiles where they exist. 

* For the data elements required for the CDMH project which are not marked as "MUST SUPPORT" in the US core profile but present in the base resource, the CDMH project will still leverage the US Core profile and add the needed data elements.
* For the data elements required for the CDMH project, but are not present in the base resource, extensions will be added to the corresponding US Core profiles. In the mapping tables below there are proposed names to be used for these extensions. 
* For the data elements where multiple resources/profiles will/can be used, the list of the resources and profiles will be listed separated by comma.


```
We ask for feedback on these extensions before we proliferate the extensions.
```


### Mapping Semantics

The CDMH project analysis has identified many areas where semantics of the data elements have to be considered to perform the mappings. The following are specific areas where translators written to map between the source and target formats have to apply proper semantic transformation to achieve the desired results. 
* Date and Time Representations.
* Vocabulary Mappings from source vocabulary (CDMs represtation) to target vocabularies (BRIDG and FHIR representation) has to be considered to minimize or prevent data loss. The following are codes that need to be translated between the CDM models and FHIR code systems and value sets.
- Diagnosis codes from source vocabulary to ICD10-CM
- Procedure codes from source vocabulary to CPT-4
- Sex codes
- Sexual Orientation codes
- Gender Identity codes
- Race codes
- Ethnicity codes
- Encounter codes
- Encounter class codes
- Drug codes
- Medication Route codes
- Medication Dosage form codes
- Specimen types
- Observation codes
- Observation value units

#### CDMs to BRIDG Mappings 

The mappings of the various CDMs to BRIDG data model which was used as the intermediary model in the CDMH project are documented in the following spreadsheet.

[CDMs to BRIDG Mappings](https://drive.google.com/file/d/194nwCX3dBMU7cfCO8no7XFVHA6I3WlYm/view?usp=sharing)

```
**Feedback Required**

In future versions of the IG, we may consider adding a BRIDG column to the below tables to have the BRIDG mapping side by side to the FHIR mappings. Another option is to add separate sections for each CDM to BRIDG similar to what has been done for FHIR. Please provide feedback on whether any of the above options would help or if it would confuse the readers since the IG's primary intent is to provide mappings from CDMs to FHIR.

```

#### PCORnet CDM version 4 to FHIR Mappings

The table below outlines the mappings between PCORnet CDM version 4 and FHIR Resources/profiles and extensions.


{% include PCORnet_CDM_v4_FHIR.html %}



#### OMOP to FHIR Mappings

The table below outlines the mappings between OMOP and FHIR Resources/profiles and extensions.


{% include OMOP_FHIR.html %}



#### Sentinel to FHIR Mappings

The table below outlines the mappings between Sentinel and FHIR Resources/profiles and extensions.


{% include Sentinel_FHIR.html %}



#### i2b2 to FHIR Mappings

The table below outlines the mappings between i2b2 and FHIR Resources/profiles and extensions.


{% include i2b2_FHIR.html %}


<br />



### Profiles

The CDMH IG uses the US Core profiles, along with the data elements present in the base resources and proposed extensions to map Sentinel, i2b2, PCORnet CDM and OMOP to FHIR.


{% include list-extensions.xhtml %}


{% include link-list.md %}

<br />
