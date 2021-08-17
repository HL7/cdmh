<!-- TOC  the css styling for this is \pages\assets\css\project.css under 'markdown-toc'-->

{:toc}


<!-- end TOC -->



###  Introduction

The Common Data Models Harmonization (CDMH) FHIR Implementation Guide (IG) will focus on mapping and translating observational data extracted for Patient Centered Outcome Research (PCOR) and other purposes into FHIR format.  Data is extracted from the different networks each of which may use a different data model for their data representation. The project focuses on the Common Data Models (CDMs) from the following four networks: 
* Patient Centered Outcome Research Network (PCORNet) 
* Informatics for Integrating Biology and Bedside (i2b2) Accrual to Clinical Trials (ACT), also known as i2b2/ACT.
* Observational Medical Outcomes Partnership (OMOP) 
* Food and Drug Administration's Sentinel 

The CDMH project is led by FDA in collaboration with other Federal Government Agencies and specific networks tackles the various aspects such as querying the data and getting the results back from the queries; however, the CDMH FHIR IG only focuses on mapping and translating the results obtained from queries to a FHIR format. The following benefits are expected from translation of observational data into a FHIR format:
* The data can be published using FHIR format using well defined RESTful APIs for other authorized users.
* Leveraging FHIR tools, techniques and apps being developed using FHIR standard.
* Provide a roadmap where by the developed mappings and translations can be re-used for data extraction from clinical information systems, which is elaborated as part of Data Access Framework Research (DAF-Research) Implementation Guide. 

The capabilities described as part of the CDMH FHIR IG are intended to be leveraged to build US data infrastructure for a Learning Health System (LHS) along with other PCOR Trust Fund (PCORTF) investments such as DAF-Research IG, Structured Data Capture (SDC) IG, Patient Reported Outcomes (PRO) FHIR IG, Women’s Health Technologies Coordinated Registry Network (CRN) FHIR IG.

The CDMH FHIR IG will leverage the US-Core IG and profiles for the resources that overlap with US-Core. 
The CDMH FHIR IG will leverage DAF-Research IG for future phases where by queries and workflows can be automated using FHIR standard. 

The CDMH FHIR IG will create profiles of profiles leveraging US-Core, DAF-Research as necessary and will create new profiles and extensions for Resources based on the four Common Data Model requirements. 

The next section provides a road map for the reader to walk through the implementation guide.


###  Guidance to the readers

The following table will provide a road map to the reader to follow and absorb the content of the implementation guide.

| Topic to Read  | What it Contains and its relationship to CDMH IG | Where can I find the content ? |
|:---------------|:------------------------------------------------|-------------------------------:|
| US-Core | The set of FHIR profiles mostly commonly implemented by vendors, also contains many of the definitions used for the CDMH IG. (For e.g Definition of“Supported”).|[US-Core Definitions]({{site.data.fhir.uscoreR4}}index.html) |
| CDMH Overview | The artifact provides an overview of the CDMH project.| [Overview](background.html)|
| Mappings and Profiles | The artifact defines the various mappings, profiles, extensions and resources that make up the CDMH FHIR IG.| [Mappings and Profiles](profiles.html)|
| Implementation Guidance | The artifact contains guidance and examples that will help implementers of CDMH FHIR IG.| [Implementation Guidance](guidance.html)|
| DAF-Research | The PCORTF sponsored IG outlines mechanisms to perform queries in distributed networks which is leveraged by the CDMH IG.| [DAF-Research](http://hl7.org/fhir/us/daf-research/)|


