{:.no_toc}

<!-- TOC  the css styling for this is \pages\assets\css\project.css under 'markdown-toc'-->

{:toc}


### Creating Translators

The CDMH project envisions open source translators to be created using the mappings provided in the CDMH IG to translate from FHIR to one of the common data models namely Sentinel, i2b2, PCORnet CDM and/or OMOP and viceversa. These translators will be useful for data extraction, querying data and converting results from CDM formats to FHIR.

### Implementation Guidance on Mapping Semantics

The CDMH project analysis has identified many areas where semantics of the data elements have to be considered to perform the mappings. The following are specific areas where translators written to map between the source and target formats have to apply proper semantic transformation to achieve the desired results. 

#### Date and Time Representations.

Dates and Times in FHIR format differ from dates and times in the common data models. So translators performing date and time translations have to read the individual components of the dates and times namely year, month, day, hour, minutes, seconds and time zones and construct the desired date and date/time elements during the mapping process.

#### Vocabulary Mappings

Vocabulary mappings between FHIR and the common data models differ for many data elements and mappings for individual domains and data elements have to be created to ensure proper mapping. Some examples of these mappings have been created as ConceptMaps and are available on the [FHIR Artifacts](artifacts.html) page. Extensive mappings required for each domain and data elements are beyond the scope of this project. Mappings have to be performed to minimize data loss and the data models have provided guidance on mapping between source systems and the common data models. The guidance can be found at 

* [PCORNet Common Data Model and its Guidance](https://pcornet.org/wp-content/uploads/2020/12/PCORnet-Common-Data-Model-v60-2020_10_221.pdf)
* [PCORNet Common Data Model Forum](https://github.com/CDMFORUM)
* [OMOP Common Data Model](https://ohdsi.github.io/CommonDataModel/)
* [OMOP ODHSI Guidance](https://ohdsi.github.io/TheBookOfOhdsi/index.html)
* [Sentinel Data Model](https://www.sentinelinitiative.org/methods-data-tools/sentinel-common-data-model/sentinel-common-data-model)
* [i2b2 Data Model](https://community.i2b2.org/wiki/display/BUN/i2b2+Common+Data+Model+Documentation)
* [FHIR Server implementation on i2b2](https://www.researchgate.net/publication/319117737_A_Fast_Healthcare_Interoperability_Resources_FHIR_layer_implemented_over_i2b2)

##### Mappings between Vocabularies

* [SNOMED to ICD Mapping](https://www.nlm.nih.gov/research/umls/mapping_projects/snomedct_to_icd10cm.html)
* [RxNorm to NDC Mapping](https://www.nlm.nih.gov/research/umls/rxnorm/docs/techdoc.html)

#### Mandatory FHIR elements not mapped directly to Common Data Models

FHIR Resources contain mandatory elements as per the specification which are not mapped to any of the Common Data Models. These elements will be populated by the EHR as per their workflows. The guidance below indicates the mandatory values for each of the profiled resources that are expected to be extracted from the EHR for populating common data models. 

* AdverseEvent resources with ``actuality`` code of "actual"
* Condition resources with ``category`` code of "problem-list-item" or "encounter-diagnosis" 
* Encounter resources with ``status`` code of "finished" 
* Group resources with ``type`` code of "person" and ``exclude`` flag of "false" 
* MedicationDispense resources with ``status`` code of "completed" 
* MedicationRequest resources with ``status`` code of "active" or "completed" 
* MedicationStatement resources with ``status`` code of "active" or "completed" or "intended" or "not-taken" 
* Observation resources representing LabResults with ``status`` code of "final" 
* Observation resources representing VitalSigns with ``status`` code of "final" 
* Procedure resources with ``status`` code of "completed" 
* ResearchStudy resources with ``status`` code of "active" or "administratively-completed" or "approved" or "closed-to-accrual" or "closed-to-accrual-and-intervention" or "completed" 