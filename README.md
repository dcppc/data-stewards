# Commons Data Stewards Github Repo

**This document derived from March 5th, 2018 data steward conference call.**

## Introduction
- Short introduction to the [Data Commons](https://docs.google.com/document/d/1bl2pLzjqXJLP2rpwXVuytx3HnCYRhZ7YBPEPOJz34Ak/edit)
- The KCs are described [here](https://docs.google.com/document/d/1bl2pLzjqXJLP2rpwXVuytx3HnCYRhZ7YBPEPOJz34Ak/edit). See, in particular, KC7, which is [focused on indexing](https://docs.google.com/document/d/19XnfSvzbVsM-z2ud4rOgpnKG9HrdpdDqLG0mQvzNDxM).
- There are many dimensions of the commons and at different levels of maturity
- It is recognized that much of this should be driven by usecases, and the DCPPC-  developers should be sharing these with the Data Stewards as soon as possible. Our use-case situation is complicated - we need to push forward in the meantime

## Purpose and approach
- We want this to be a partnership wrt role definition, how things change over time, how to make best use of resources
- We recognize that Push/pull models, protocols will change over time

## Agreement: for each data source we will record:
- Version
- Short manifest, preferably computable
- Point of contact (POC)
- Schema version
- Is this possible: Description for generation dataset in the manifest - how it would be re-generated and transferred to the full stacks if that POC turned into a pump
---
## Data Stewards points of contact:
- TOPMed: -- Albert Smith albertvs@umich.edu -- Cathy Laurie cclaurie@uw.edu
- GTEx: -- Francois Aguet francois@broadinstitute.org -- Kristin Ardlie kardlie@broadinstitute.org
- MODs -- Mike Cherry cherry@stanford.edu -- Travis Sheppard tshepp@stanford.edu

**The Alliance manifest is [[here](https://docs.google.com/document/d/1QsZNNV-4XHQUy0QaNfNkjn5bblWdaprQhHJjq5loWOU/edit)]**
## Agreement - Alliance / MODs
- The Alliance site ([alliancegenome.org](http://www.alliancegenome.org)), cloud file access, GOC API will be used to obtain gene function (aka GO annotations) 
- Items such as these can be obtained from DC cloud file access, and soon Alliance API. 
  - Disease associations (Disease Ontology)
  - Chromosomal features (Sequence Ontology)
  - Orthology/Conservation/Homologs schema 
  - Basic Gene Information
  - Expression (soon) - available from select MODs now
  - Phenotypes (soon) - available from select MODs now
  - Physical and Genetic interactions (soon) - available from select MODs now
  - Others are in progress and well be release when available
The Alliance is currently focusing on data types are that are shared between all member projects.  If the data you require is only available from a subset of the MODs please file a ticket.
