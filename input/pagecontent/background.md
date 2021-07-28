<!-- TOC  the css styling for this is \pages\assets\css\project.css under 'markdown-toc'-->

* Do not remove this line (it will not be displayed)
{:toc}


<!-- end TOC -->



###  Background

Section 937(a)(£) of the Public Health Service Act (PHS Act), as amended by section 6301(b) of the Affordable Care Act of 2010 (ACA), PL 111-148, 124 Stat. 119 (March 23, 2010), authorizes the Secretary of the U.S. Department of Health and Human Services (HHS) to provide for the coordination of relevant Federal programs to build data capacity for patient-centered outcomes research. The Office of the Assistant Secretary for Planning and Evaluation (ASPE) is delegated to coordinate the Department's effort.

The current project, titled Harmonization of Various Common Data Models and Open Standards for Evidence Generation, is a multiagency collaboration led by the Food and Drug Administration (FDA). Other agencies include the National Cancer Institute (NCI), National Center for Advancing Translational Sciences (NCATS), the Office of the National Coordinator for Health Information Technology (ONC) and the National Library of Medicine (NLM).

The purpose of this project is to provide patient-centered outcomes researchers as well as other researcher at various Federal Government Agencies, academia, etc. with access to broader observational data by leveraging existing PCORTF investments such as US-Core, Data Access Framework Research Implementation Guide (DAF-Research IG). The project leverages the lessons learned from [ONC Query Health initiative](https://www.ncbi.nlm.nih.gov/pubmed/24699371) completed in 2013/2014. Subsequently efforts in HL7 towards a language for clinical decision support and quality measurement and subsequently a harmonization of those effors into [CQL](https://cql.hl7.org/) which enabled specification of query semantics against various data models including FHIR. In addition FHIR has developed StructureMap and ConceptMap resources which can be used for mapping and transformation between models. CDMH uses many of these concepts to build the necessary mappings and profiles that can be leveraged to make data captured and stoed in different models available for researchers.

###  Purpose and Goals of the Project 

The purpose and goals of the overall project are as follows

* Develop a common data architecture to create user driven queries of the following four common data model (CDMs) of four networks (Sentinel, i2b2/ACT, OHDSI and PCORnet).

	- FDA’s Sentinel data model version 6.0.2
	- Patient-Centered Outcomes Research Network (PCORNET) data model version 4.0
	- Informatics for Integrating Biology & the Bedside (i2b2)/ACT data model version 1.4
	- Observational Medical Outcomes Partnership (OMOP) data model version 5.2

* Creating mapping between the above CDMs to Biomedical Research Integrated Domain Group (BRIDG) which serves as an intermediary model in the project. This is explained further in the abstract model section below.
* Create mappings between the above CDMs and Fast Healthcare Interoperability Resources (FHIR) profiles and resources. These mappings will facilitate broader access to data from multiple networks.
* The common architecture and mappings are intended to enable researchers from public and private sectors (e.g. FDA, NIH, Centers for Disease Control and Prevention (CDC), biopharmaceutical industry and patient-centered outcomes researchers) to access observational data also known as Real World Data (RWD).

### Abstract Model, Actors and Definitions

This section outlines the abstract model, the specific actors and definitions that will be used for creating the implementation guide. Figure 1 below shows a pictorial representation of the data flows and the actors for the CDMH IG.

{% include img.html img="cdmh-abstract-model.png" caption="Figure 1: CDMH Abstract Model" %}

The steps involved in the CDMH project includes creating a query, distributing the query to the various organizations (data partners), and collecting the results, and then finally viewing the results. These steps are is outlined in the above diagram and the definitions of the various actors can be found below.

**Researcher Portal:** Researcher Portal actor represents the capabilities that will be used by the researcher to compose the queries, distribute the queries and then view the returned results. Typically in a Researcher Portal implementation there will be many modular components, some of which are outlined below

- **Query Composer:** Query Composer represents the user interface and related functionality that will be used by the researcher to compose the queries. 
- **Query Translator:** Query Translator represents the capability that translates the composed query into the various CDM formats required by each of the Data Partner organization.
- **Query Distributor:** Query Distributor represents the capability that distributes the queries to the various Data Partners.
- **Data Partner Manager:** Data Partner Manager provides the capability to manage each Data Partner and its related meta data that identifies the organization, point of contact, researchers that are allowed access etc.
- **Result Translator:** Result Translator translates the results received from the various Data Partners into formats such as FHIR, BRIDG/Study Data Tabulation Model (SDTM) for consumption by researchers.
- **Result Viewer:** Result Viewer provides the capability to view the results for a researcher. 
- **Vocabulary Services:** Vocabulary Services represent the necessary mapping software to map codesystems/valuesets/codes from the various CDMs to standard formats.
- **Security Services:** Security Services represent the capability to protect privacy, allow authorized researchers to access specific Data Partners to submit queries and view results. 
	
**Data Partner:** Data Partner is any network or organization that is participating in the overall CDMH project and supports a data model or data models that can be queried by authorized researchers. The Data Partner holds the research data in a database conforming tousing one of the Common Data Models formats which and has appropriate security controls to verify/validate queries before releasing the results of a query.

**Data Partner Client:** Data Partner Client represents the capability that allows the Data Partner network or organization to control the queries being run and results being submitted to the Researchers. 

**CDMs:** Common Data Models (CDMs) represent various physical representations of data that are commonly used by research networks and organizations currently. For CDMH project purposes, FDA's Sentinel,PCORnet CDM, i2b2 and OMOP data models are being considered for mapping to FHIR.  

####  BRIDG Intermediary Model and its role in CDMH project

The abstract model shown above allows researchers to compose queries in a uniform format and send them to the data partners for execution. In order to compose queries that can be executed against the different data models, the researcher has two options 
1. Compose queries in the different formats required by each data partner.
2. Compose queries in a common format using and intermediary model and then translate the query from intermediary model to the various formats required by the data partners. 

For CDMH, Option 1 was not considered as it would add a significant burden on the researchers and the user interface to compose queries in each format and the maintenance of the overall solution would be complex. Hence Option 2 was chosen with BRIDG serving as the intermediary model. 
Leveraging BRIDG as the intermediary model has many benefits some of which are listed below
* Ability to use a common model for composing the queries making the system design easier and maintainable.
* Well defined semantics of BRIDG makes it easier for others to understand the data.
* Allows for converting from a single intermediary models to any number of CDMs, which can be done once centrally thus reducing any burden on the data partners. 
* Allows for converting results from the data partners to a common model from where it can be mapped and translated to other formats including FHIR.

In the current phase of the project, BRIDG was chosen as the intermediary model to gain experience with the overall project and its implementation. In future phases, FHIR may be considered for playing the role of the intermediary model.

As as result of the architecture choices and decision made, the CDMH project developed a mapping between the various CDMs and BRIDG and then mapped BRIDG to FHIR. These mappings have been leveraged to finalize the mappings of the CDMs to FHIR and are outlined in the Mappings and Profiles section of the IG.


###  Expected Benefits of the CDMH Project

The following benefits will be realized by the industry using the CDMH project artifacts.

* Allows researchers to query multiple research networks using disparate data models using a single researcher portal.
* Allows researchers to view results from multiple research networks using disparate data models. 
* Allows Data Partners invested in different CDM models to continue to use the existing data models but participate in multiple research programs without requiring new infrastructure.
* Standards based mapping will allow for supporting more use cases in the future without changes to the infrastructure. 

###  Relationship between DAF-Research FHIR IG and CDMH FHIR IG

The DAF-Research FHIR IG outlines the overall workflows used to extract data from EHR systems, populate the CDMs and then allow the researcher to query these CDMs using mutliple formats embedded in FHIR resources and receive results using FHIR format. The CDMH FHIR IG complements the DAF-Research IG by providing the mappings from different CDMs to FHIR that can be used across multiple use cases. There are few overlaps between the CDMH and DAF-Research IG which will be harmonized on subsequent updates to DAF-Research and CDMH FHIR IGs. 


