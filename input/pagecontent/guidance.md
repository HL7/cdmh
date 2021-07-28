{:.no_toc}

<!-- TOC  the css styling for this is \pages\assets\css\project.css under 'markdown-toc'-->

* Do not remove this line (it will not be displayed)
{:toc}


### Creating Translators

The CDMH project envisions open source translators to be created using the mappings provided in the CDMH IG to translate from Sentinel, i2b2, PCORnet CDM and OMOP to FHIR and vice-versa. These translators will be useful for data extraction, querying data and converting results from CDM formats to FHIR.

### Implementation Guidance on Mapping Semantics

The CDMH project analysis has identified many areas where semantics of the data elements have to be considered to perform the mappings. The following are specific areas where translators written to map between the source and target formats have to apply proper semantic transformation to achieve the desired results. 
* Date and Time Representations.
* Vocabulary Mappings from source vocabulary (CDMs representation) to target vocabulary (FHIR representation) has to be considered to minimize or prevent data loss. 
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
