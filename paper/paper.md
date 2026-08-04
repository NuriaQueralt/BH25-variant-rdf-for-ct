---
title: 'Variant annotation in RDF for clinical trials matching'
title_short: 'Variants for clinical trials'
tags:
  - Variant annotation
  - GA4GH VRS
  - RDF
  - Clinical trials
authors:
  - name: Núria Queralt-Rosinach
    orcid: 0000-0003-0169-8159
    affiliation: 1
  - name: Toshiaki Katayama
    orcid: 0000-0003-2391-0384
    affiliation: 2
  - name: Jose Emilio Labra Gayo
    orcid: 0000-0001-8907-5348
    affiliation: 3
  - name: Claude Nanjo
    orcid: 0009-0002-1208-8858
    affiliation: 4
affiliations:
  - name: Leiden University Medical Center, The Netherlands
    index: 1
  - name: Database Center for Life Science, Japan
    index: 2
  - name: WESO Lab - University of Oviedo, Spain
    index: 3
  - name: University of Utah, USA
    index: 4
date: 15 September 2025
cito-bibliography: paper.bib
event: BH25JP
biohackathon_name: "DBCLS BioHackathon 2025"
biohackathon_url:   "https://2025.biohackathon.org/"
biohackathon_location: "Mie, Japan, 2025"
group: genome-variation
git_url: https://github.com/NuriaQueralt/BH25-variant-annotation-rdf
authors_short: Queralt-Rosinach \emph{et al.}
---

# Abstract
Precision oncology depends on semantic, interoperable representations of genomic variants (GV)—particularly structural variants (SVs)—to match patients with clinical trials. In this __exploratory project__, we investigated the use of __RDF and the GA4GH VRS Schema__ to standardize variant annotations and integrate them with clinical trial data. Our work, developed in collaboration with the _Pangenome Graphs_ and _Platform for Precision Medicine_ groups, prototypes an RDF-based data harmonization that paves the way for __improved semantic interoperability__ in precision medicine, especially for cancer research and AI-driven discovery.

# Introduction
__Background__: Precision oncology relies on the accurate description of genomic variants for each patient to tailor precise interventions. However, there is a lack of semantic representations of patient data that enable the identification of ongoing clinical trials with experimental drugs suited to individual patients. Without standardized, machine-readable variant annotations, matching patients to relevant trials remains inefficient, hindering the full potential of precision medicine.

__Challenge__: The need for semantic representations was a central focus at the DBCLS BioHackathon 2024, where two parallel projects emerged: one aimed at standardizing [genomic variation](https://github.com/NuriaQueralt/ga4gh-vrs-rdf-schema/tree/main) [@citesAsAuthority:vrsrdfBH2024], and another at integrating [clinical trials](https://github.com/LLTommy/BH24-SemClinTrial). These efforts underscore the urgency of addressing data harmonization and interoperability in genomic research.

A particularly pressing challenge lies in representing __structural variants (SVs)__—large-scale genomic alterations (typically >50 base pairs) that include gains, losses, or rearrangements of genes or regulatory elements, unlike single nucleotide polymorphisms (SNPs). SVs play a major role in disease etiology, cancer genomics [@citesAsAuthority:LoboMartins2026], gene regulation, and evolution. Despite their significance, several obstacles persist in computational biology: data harmonization (inconsistent representations across databases), genotype assignment (difficulties in accurately classifying SVs), functional prediction (limited tools for interpreting the biological impact of SVs), or knowledge embedding (challenges in integrating SV data into RDF knowledge graphs for AI-driven reasoning). For the semantic web, the lack of a standardized representation for SVs in RDF formats limits their utility in knowledge graphs and AI applications, directly impacting clinical genomics and discovery.

__Objective__: To address these gaps, our project focused on two key goals:

  1. Updating the GA4GH VRS RDF Schema developed during BioHackathon 2024 to adjust to the new v2 of the GA4GH VRS standard to better support patient-to-clinical-trial matching use case.
  2. Assessing the state-of-the-art in structural variant representation, with a focus on enabling seamless integration into RDF-based knowledge graphs.
     
By leveraging RDF, we aim to improve interoperability, standardization, and the accuracy of patient-trial matching, ultimately advancing precision oncology.

# Related work
## 1. GA4GH VRS standard: evolution from v1 to v2
The __GA4GH Variant Representation Specification (VRS)__ [@citesAsAuthority:Wagner2021] has undergone significant updates from v1 to v2 to address the growing complexity of genomic variant data. VRS v2 introduces a more flexible and extensible framework, enabling the representation of a broader range of variant types, including structural variants. This update aligns with the need for __standardized, machine-readable annotations__ in precision medicine, facilitating interoperability across databases and tools. However, the adoption of VRS in __RDF-based knowledge graphs__ remains limited, particularly for SVs, which are critical for clinical genomics and AI-driven discovery.

## 2. Aligning diverse RDF variant representations
During the International SWAT4HCLS conference held on 24-27th February 2025 in Barcelona (Spain), we detected an emerging number of novel RDF models to represent variant information in datasets. Building on the momentum from the __DBCLS BioHackathon 2024__, our project at the __SWAT4HCLS BioHackathon 2025__ focused on bridging the gap between diverse genomic variant representations in RDF. Our approach was to use the GA4GH VRS RDF schema as the standard. We leveraged the updated __GA4GH VRS RDF Schema__ to align the different models and prototype a pipeline for annotating variant models mappings to VRS in RDF. This effort aimed to demonstrate how semantic representations can enhance the __interoperability__ of variant data for clinical applications.

## 3. State-of-the-art in clinical trials models and RDF schemas
Current approaches to clinical trial matching often rely on __siloed databases__ (e.g., ClinVar, COSMIC) or proprietary formats, which hinder data integration and reuse. In the semantic web, RDF-based schemas such as BioPAX, TransMed, and OBAN have been proposed to model clinical trials and biomedical data. However, these schemas often lack __comprehensive support for genomic variants__, particularly SVs, and do not fully exploit the potential of __knowledge graphs__ for AI-driven reasoning. __Recent work__ has explored the use of __ontologies__ (e.g., SO, OBO) and __SPARQL queries__ to improve trial matching, but challenges remain in __standardizing variant representations__ and ensuring seamless integration with existing clinical trial databases.

## Our contributions to current research
  __1. GA4GH VRS RDF for Semantic Clinical Trials:__
 We explored how to extend the GA4GH VRS RDF Schema to explicitly support patient-to-clinical-trial matching, enabling the representation of variants in a way that aligns with semantic web standards. This contribution envisions to facilitate the automated querying and reasoning of variant data within RDF knowledge graphs, improving the efficiency of trial matching.

  __2. Structural Variants Representation:__
 We investigated how to address the gap in standardized RDF representations for SVs by assessing the state-of-the-art and proposing solutions to integrate SVs into knowledge graphs. Our work intends to enable the harmonization of SV data across databases, supporting AI-driven analysis and clinical decision-making.

  __3. Precision Oncology Use Case:__
 We defined how to demonstrate the practical application of our RDF-based approach in a precision oncology use case, aiming at showcasing how semantic representations of variants can enhance the accuracy and scalability of clinical trial matching. This use case highlights the potential of our method to accelerate discovery and improve patient outcomes in precision medicine.


# Method
## Materials
__Use of standards:__
 We adhered to established standards such as __GA4GH VRS v2, RDF/OWL__, and __ShEx__ to ensure interoperability and semantic consistency. These standards provided the foundation for representing genomic variants and clinical trial data in a structured, queryable format.

__Use case-driven approach:__
 Our methodology was guided by real-world use cases, particularly __patient-to-clinical-trial matching__ in precision oncology. This approach ensured that our solutions were practical and directly addressed the needs of researchers and clinicians.

## Plan
  1. Analyse GA4GH VRS new version, i.e., v2
  2. Analyse clinical trials description of variants, molecular biomarkers in clinicaltrials.gov
  3. Search for existing (if any) clinical trials RDF models, otherwise use the one developed in BH24
  4. Update GA4GH VRS RDF model for v2 prioritizing the components needed for the clinical trials or pangemone graph use cases
  5. Ensure interoperability with phenotypic description using Phenopackets-rdf
  6. Instantiate examples in phenopackets-store
  7. Link variant to clinical trial data
  8. Query to match patient-variant to clinical trials

## Collaborations

  * __Pangenome graphs:__
 Collaborated with the Pangenome Graphs group to explore how __structural variants (SVs)__ could be represented in RDF, leveraging their expertise in graph-based genomic data models. This partnership helped us refine our approach to SV annotation and integration into knowledge graphs.

  * __Personalized medicine platform:__
 Worked with the Platform for Precision Medicine group to define a __clinical application__ that aligns our RDF-based variant annotations with their infrastructure, ensuring compatibility with existing tools and workflows for clinical decision-making.

# Results
## GA4GH VRS model
  * Analysed the new version of the model released, i.e., v2, in [GA4GH VRS GitHub](https://github.com/ga4gh/vrs/blob/2.0/schema/vrs/vrs-source.yaml). While SV representation is under development, we found that the current model links to SV via the [DerivativeMolecule object](https://github.com/ga4gh/vrs/blob/2.0/schema/vrs/json/DerivativeMolecule). We opened an [issue on github](https://github.com/orgs/ga4gh/projects/12/views/1?pane=issue&itemId=84884943&issue=ga4gh%7Cvrs%7C572) for documentation on the current state of development for the SV representation.
  * Identified how to update the GA4GH VRS RDF Schema to support patient-to-clinical-trial matching, enabling semantic representations of variants that align with clinical trial criteria.
  * Started updating the VRS RDF model to align with v2 of the standard using ShEx by prioritizing the GV attributes such as SV.
  * Next: Demonstrate how the model improves interoperability and queryability of variant data using SPARQL.

## Clinical trials model  
  * Analysed [ClinicalTrials.gov](https://clinicaltrials.gov/) to understand how GV and molecular biomarkers are described. We found that the database uses tags such as “BRCA Mutation” and “Mutation Burden” in the *Condition* field (see [exemple](https://clinicaltrials.gov/study/NCT06792721?term=Mutation%20Burden&rank=3#study-overview)). It remains unclear what vocabularies or ontologies, if any, are used to represent this mutation information. Overall, ClinicalTrials.gov describes GV and biomarkers in the Study title and summary, *Eligibility criteria*, and Intervention fields primarily using free-text. This finding is in accordance with what we observed last year in the BH24 Semantic clinical trials project.
  * Identified clinical trials models [@citesAsAuthority:Lin2020],[@citesAsAuthority:Mathes2024] that enable to represent GV information for the precision oncology driving use case.
  * Next: Investigate if [RDFPortal](https://rdfportal.org/) represents clinical trials data and, if so, whether there is an RDF schema for variants.
  * Next: Develop an RDF-based model for clinical trials that integrates genomic variant data (including SVs) with trial eligibility criteria.
  * Next: Showcase how this model facilitates automated matching of patients to trials using semantic reasoning.

## Implementation of GA4GH VRS RDF schema v2
  * Designed a RDFization prototype pipeline with the updated GA4GH VRS RDF Schema v2 based on [Phenopackets store](https://github.com/monarch-initiative/phenopacket-store/blob/main/notebooks/ADA/phenopackets/PMID_28823388_3-month-oldgirl.json) data and the [ShExML tool](https://shexml.herminiogarcia.com/).
  * Next: Validate the schema’s ability to represent complex variants (e.g., SVs) and support AI-driven reasoning in knowledge graphs.

## Structural variants representation
  * Assessed the state-of-the-art in structural variant representation [@citesAsAuthority:Collins2020],[@citesAsAuthority:Kawashima2023]. To point out that we could not identify any existing semantic or RDF schema for SVs during the hackathon week.
  * Received feedback on current developments from BioHackathon participants such as the [ACTG haplotype notation](https://jogo.csml.org/) from the Pangenome Graphs group, and engaged in discussions & brainstorming about existing tools [@citesAsAuthority:Siren2021],[@citesAsAuthority:Edwards2025] and graphical approaches [@citesAsAuthority:Li2024],[@citesAsAuthority:Schloissnig2025] to represent and annotate SVs, e.g., using GFA file format and [Bandage](https://rrwick.github.io/Bandage/).
  * Next: Develop an RDF schema focusing on interoperability with existing semantic web data resources and global standards such as GA4GH VRS.

## Potential new use cases

  __1. Structural Variants Representation:__
 From our collaboration with the _Pangenome Graphs_ group, we identified opportunities to extend our RDF schema to better capture __SVs__ in pangenome contexts, enabling more comprehensive genomic analyses.

  __2. Precision Oncology:__
 In partnership with the Platform for _Precision Medicine_ group, we explored how our RDF-based approach could be integrated into their workflows to enhance __real-time trial matching__ for cancer patients.

# Discussion
Precision oncology relies on accurate and interoperable representations of genomic variants to match patients with suitable clinical trials. However, the lack of __semantic, standardized annotations__—particularly for __structural variants (SVs)__—hampers efficient trial matching and AI-driven discovery. In this hacking project, we explored how to address this gap by leveraging __RDF (Resource Description Framework)__ to enhance the __GA4GH Variant Representation Specification (VRS) Schema__ and integrate it with clinical trial data.

__GA4GH VRS RDF for semantic clinical trials:__ We started the update of the __GA4GH VRS RDF Schema__ to support __patient-to-clinical-trial matching__, with a focus on representing SVs in a machine-readable, queryable format. Even though there is not a GV/SV schema that enables data harmonization from the VRS model to _ClinicalTrials.org_, we identified current developments and defined a strategy that makes the matching possible by refining our model based on [ERDERA](https://erdera.org/) standards and developed during BioHackathon 2024. Updating the semantic model of VRS driven by the clinical trial matching use case, helped us to focus and prioritize the modelling, which is a hard and time expensive effort. In addition, the [Global Alliance for Genomics \& Health or GA4GH](https://www.ga4gh.org/) is interested in new clinical applications using their variant standards such as when extracting patient genomic data then, how to enable automated clinical trial matching.

__Structural variants representation:__ We explored graph-based approaches to drive the semantic SV modelling based on the GA4GH standard representation. This will set the basis for data integration and for the development of new AI tools for genotype assignment such as using pangenome graphs or for population-aware genomics medicine. 

__Data standardization challenge for precision medicine:__ Our exploratory work developed during the BioHackathon week just emphasized the magnitude of the current challenge that is to harmonize genomic variant data. From our discussions and sharing knowledge, experiences and resources, it was clear that one reason is because genetic diversity is a very complex biological question. To tackle this big problem is crucial to work with different communities and researchers worldwide, and BioHackathon venues offer a unique space to seed these collaborations and start building community and tools for precision medicine together. Last but not least, pairing with global efforts such as GA4GH and ERDERA is paramount to support standardization and adoption.

__BH enabled collaboration and finding use cases:__ Collaborating with the _Pangenome Graphs_ and Platform for _Precision Medicine_ groups, we identified two use cases to demonstrate the practical application of our RDF-based approach:

  * Structural variant representation use case. ACTG-Haplotype Notation. Graphical representation via GFA and bandage. Future: we prototyped an RDF-based pipeline that enables __semantic reasoning__ over variant data, improving interoperability and scalability.
  * Precision oncology use case. RDF resources for semantic clinical trials representation: Clinical Trials Ontology, RDFPortal. Future: demonstrate via prototype how to query patient-clinical trial matching queries via __personalized medicine platform__.
    
 Overall, our main findings are that there is not a semantic standard neither for genomic variants nor for structural variants and we defined precision medicine use cases to drive their semantic modelling for data harmonization and AI. Our exploratory results set the foundation to demonstrate how RDF can bridge genomic and clinical trial data, facilitating __AI-driven analysis__ and __precision oncology applications__. 

This work contributes to ongoing efforts in the __SWAT4HCLS, ERDERA, and GA4GH communities__, paving the way for standardized, semantic representations of genomic variants in clinical and research settings.

## Impact
1. **ERDERA**: Our work aligns with the goals of __ERDERA__ (European Rare Disease Research Alliance) by providing a standardized framework for representing genomic variants, which can improve data sharing and collaboration in rare disease research.
2. **Pangenome graphs**: Contributed to the Pangenome Graphs community by exploring how RDF can represent __SVs__ in a way that supports graph-based analyses, fostering interoperability across genomic datasets.
3. **Platform for precision medicine**: Defined a use case to enhance the capabilities of the Platform for Precision Medicine by enabling semantic integration of variant data, which can streamline __patient-trial matching__ and support personalized treatment strategies.
4. **GA4GH**: Our work aligns with the goals of GA4GH and will set a foundation to support the __GA4GH BRCA Challenge__ by providing a semantic framework for representing __BRCA variants__, which can improve the accuracy and efficiency of clinical interpretations.

## Future work
- Update current GA4GH VRS RDF model expressed in ShEx to v2
Transition the existing GA4GH VRS RDF model (expressed in ShEx) to v2, incorporating feedback from the community and addressing gaps in SV representation.

- Annotate variant data 
Implement a RDFization workflow to annotate variant data in the [Phenopackets store](https://github.com/monarch-initiative/phenopacket-store/blob/main/notebooks/ADA/phenopackets/PMID_28823388_3-month-oldgirl.json) using the [ShExML tool](https://shexml.herminiogarcia.com/). This will enable the automated conversion of Phenopacket data into RDF, facilitating integration into knowledge graphs.

We welcome feedback and contributions from the community. Please, use the issue and pull requests system at https://github.com/NuriaQueralt/ga4gh-vrs-rdf-schema.


## Acknowledgements
We thank the organizers of the DBCLS BioHackathon 2025 for providing the venue and support for this work. We also acknowledge the developers of GA4GH VRS for providing the foundational model that made this work possible. We would like to thank the contributions of Mana Nagasaki, Shuhua Xu, Yosuke Kawai, and Raúl Mateos who shared their needs, tools and domain knowledge for all the informative and inspirational discussions maintained along the week. 

## References
