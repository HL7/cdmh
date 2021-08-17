### Mappings

This section contains the mappings between the various CDMs, BRIDG and the FHIR Resources/profiles. In each mapping the CDM data element is mapped to the appropriate BRIDG data element and the FHIR Data Element. The column FHIR Resource/Profile/Extension identifies the specific profile and/or extension if one exists. If the profiles do not exist then they are mapped to the resource. New profiles and extensions will be added where necessary as the pilot implementations provide feedback through the ballot process.

### Mapping Conventions and usage of US Core IG

The mappings use the US Core profiles, value sets and code systems where they exist and overlap with CDMH. 

* For the data elements required for the CDMH project which are not marked as "MUST SUPPORT" in the US core profile but present in the base resource, the CDMH project will still leverage the US Core profile and add the needed data elements.
* For the data elements required for the CDMH project, but are not present in the base resource, extensions will be added to the corresponding US Core profiles. In the mapping tables below there are proposed names to be used for these extensions. 
* For the data elements where multiple resources/profiles will/can be used, the list of the resources and profiles will be listed separated by comma.


### Mapping Semantics

The CDMH project analysis has identified many areas where semantics of the data elements have to be considered to perform the mappings. The following are specific areas where translators written to map between the source and target formats have to apply proper semantic transformation to achieve the desired results. 
* Date and Time Representations.
* Vocabulary Mappings from source vocabulary (CDMs representation) to target vocabularies (BRIDG and FHIR representation) has to be considered to minimize or prevent data loss. The following are codes that need to be translated between the CDM models and FHIR code systems and value sets.
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



#### PCORnet CDM version 4 to FHIR R4 Mappings

The table below outlines the mappings between PCORnet CDM version 4 and FHIR Resources/profiles and extensions.


{% include PCORnet_CDM_v4_FHIR.html %}



#### OMOP 5.2 to FHIR R4 Mappings

The table below outlines the mappings between OMOP and FHIR Resources/profiles and extensions.


{% include OMOP_FHIR.html %}



#### Sentinel 6.0.2 to FHIR R4 Mappings

The table below outlines the mappings between Sentinel and FHIR Resources/profiles and extensions.


{% include Sentinel_FHIR.html %}



#### i2b2/ACT 1.4 to FHIR R4 Mappings

The table below outlines the mappings between i2b2/ACT and FHIR Resources/profiles and extensions.


{% include i2b2_FHIR.html %}


<br />

