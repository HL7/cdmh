---
title: Mappings and Profiles for the IG
layout: default
active: profiles
---
### Mappings

This section contains the mappings between the various CDMs and the FHIR Resources/profiles. In each mapping the CDM data element is mapped to the appropriate FHIR Data Element. The column FHIR Resource/Profile/Extension identifies the specific profile and/or extension if one exists. If the profiles do not exist then they are mapped to the resource. New profiles and extensions will be added where necessary as the pilot implementations provide feedback through the ballot process.

### Mapping Semantics

The CDMH project analysis has identified many areas where semantics of the data elements have to be considered to perform the mappings. The following are specific areas where translators written to map between the source and target formats have to apply proper semantic transformation to achieve the desired results. 
* Date and Time Representations.
* Vocabulary Mappings from source vocabulary (CDMs represtation) to target vocabulary (FHIR representation) has to be considered to minimize or prevent data loss. 
- Diagnosis codes from source vocabulary to ICD10-CM
- Procedure codes from source vocabulary to CPT-4
- Sex codes
- Sexual Orientation codes
- Gender Identity codes
- Race codes
- Ethnicity codes
- Encounter codes
- Drug codes
- Medication Route codes
- Medication Dosage form codes

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

The CDMH IG uses the US Core profiles and the data elements present in the base resources to map Sentinel, i2b2, PCORnet CDM and OMOP to FHIR.


{% include list-extensions.xhtml %}


{% include link-list.md %}

<br />
