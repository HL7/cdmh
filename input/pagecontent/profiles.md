### Mappings

This section contains the mappings between the various CDMs, BRIDG and the FHIR Resources/profiles. In each mapping the CDM data element is mapped to the appropriate BRIDG data element and the FHIR Data Element. The column FHIR Resource/Profile/Extension identifies the specific profile and/or extension if one exists. If the profiles do not exist then they are mapped to the resource. New profiles and extensions will be added where necessary as the pilot implementations provide feedback.

### Mapping Conventions and usage of US Core IG

The mappings use the US Core profiles, value sets and code systems where they exist and overlap with CDMH. 

* For the data elements required for the CDMH project which are not marked as "MUST SUPPORT" in the US core profile but present in the base resource, the CDMH project will still leverage the US Core profile and add the needed data elements.
* For the data elements required for the CDMH project, but are not present in the base resource, extensions will be added to the corresponding US Core profiles. 
* For the data elements where multiple resources/profiles will/can be used, the list of the resources and profiles will be listed separated by comma.
* Wherever identifiers or id elements are used to map to CDM Id columns it is assumed that as part of the loading process if there needs to be any processing required such as de-identification it is performed and the process will be used to re-link back to the original record when needed for identification.



#### CDMs to BRIDG Mappings 

The mappings of the various CDMs to BRIDG data model which was used as the intermediary model in the CDMH project are documented in the following spreadsheet. BRIDG was chosen as the intermediary model as it was required for submitting data to FDA.

[CDMs to BRIDG Mappings](https://drive.google.com/file/d/194nwCX3dBMU7cfCO8no7XFVHA6I3WlYm/view?usp=sharing)



#### PCORnet CDM version 4 to FHIR R4 Mappings

The table below outlines the mappings between PCORnet CDM version 4 and FHIR Resources/profiles and extensions.


{% include PCORnet_CDM_v4_FHIR.html %}



#### OMOP 5.2 to FHIR R4 Mappings

The table below outlines the mappings between OMOP and FHIR Resources/profiles and extensions.


{% include OMOP_FHIR.html %}


1: codes, Codings and CodeableConcept data types in FHIR which are used to convey specific concepts about a resource have to be mapped to OMOP Vocabulary which contains a large number of concepts with a specific concept_id that is used in the various tables. (For e.g In OMOP table CONDITION_OCCURRENCE, the condition_concept_id contains an id present in the OMOP vocabulary and the FHIR Condition.code value has to be mapped to the OMOP concept_id using guidance present in the [OMOP Common Data Model](https://ohdsi.github.io/CommonDataModel/) and [OMOP OHDSI Documentation](https://ohdsi.github.io/TheBookOfOhdsi/CommonDataModel.html#visitOccurrence). In this case, Condition.code from FHIR resource would actually be retained in the CONDITION_SOURCE_VALUE element).

2: Identifiers in the FHIR resources should be used to generate the ID elements of the OMOP tables unless they are auto-generated. If IDs in OMOP tables are auto-generated, then the identifiers should be stored in the OMOP tables under the <TABLENAME>_SOURCE_VALUE element. For e.g If the PERSON_ID is auto-generated, then the Patient.identifier from the FHIR resource should be stored in the PERSON_SOURCE_VALUE column in the OMOP PERSON table. This will allow linkages between the FHIR resources and OMOP tables when data is extracted for population of the OMOP tables. If the FHIR resources do not contain identifiers, then the id element of the FHIR resources can be used to map back and forth between FHIR resources and OMOP tables created from the FHIR resources.

3: The concept_ids identified should be used by queries to retrieve the data from OMOP tables for analysis instead of using the <DOMAIN>_SOURCE_VALUE elements.
 


#### Sentinel 6.0.2 to FHIR R4 Mappings

The table below outlines the mappings between Sentinel and FHIR Resources/profiles and extensions.


{% include Sentinel_FHIR.html %}



#### i2b2/ACT 1.4 to FHIR R4 Mappings

The table below outlines the mappings between i2b2/ACT and FHIR Resources/profiles and extensions.


{% include i2b2_FHIR.html %}


<br />

