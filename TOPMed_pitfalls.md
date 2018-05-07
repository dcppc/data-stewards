# TOPMed Pitfalls
07 May 2018
Submitted in response to Data Stewards [Github Issue 6](https://github.com/dcppc/data-stewards/issues/6) by Ben Heavner (bheavner...at...uw.edu) for TOPMed

Because of the access-controlled nature of the data, TOPMed is structured so that users have to make specific proposals and describe their intended data usage prior to gaining access to the data via dbGaP, so there is lots of opportunity for the community to evaluate the intended data usage and any potential for misuse. Our organizational structure is intended to prevent widespread significant data misuse, and seems to have succeeded at that goal so far.

However, we have seen widespread misunderstanding of what the data is, what the data cleaning process is, and what aspects of the data can be meaningfully analyzed - issues such as people wanting to do statistical analysis on variables that are not comparable (thus “phenotype harmonization”). We have also encountered scaling challenges as the genotype data volume grows with each new data freeze/release. This data set is very rich, but meaningful analysis is very difficult.

A few concrete reasons that meaningful analysis is difficult include:

- It requires harmonizing lots of heterogeneous, legacy phenotype data;
-- This includes 1) determining which phenotype variables are measuring the same thing across studies as well as 2) processing the data values such that they can be analyzed across studies.
-- These data were collected individually by each study and posted to dbGaP, oftentimes long before the beginning of the TOPMed project.

- The genotype data size makes computation challenging on local resources (very large matrices mean very large memory requirements and processing times);

- The consent value for a given subject can change over time, so the current consent values for all subjects must be tracked.

Here are some potential pitfalls regarding phenotypic data (there are many others that are not listed):

- Files provided by dbGaP are a mostly consistent format, with some quirks:
    - Occasionally additional tab delimiters are present in the file.
    - Occasionally rows have fewer tab delimiters than expected because the remaining values in the row are all blank.

- Sometimes a subject has enrolled in two different studies, and thus has two different phenotype records. Sometimes this information is provided by dbGaP, but often it is not known.

- Failure to properly account for missing codes
    - Some study variables use integers as both the data values (e.g, 1-5) and as a other or missing code (e.g., 9). Failure to notice missing codes and exclude values appropriately. Examples of variables that use integers as both the data value and the missing code:
        - NPBRAAK, phv00162070.v2.p10
        - BP37, phv00104051.v1.p1

- SUBJECT_IDs are not uniquely assigned across studies, so one subject in one study could have the same SUBJECT_ID as a different subject in another study. Solution: Include study in the subject identifiers.

- Failure to perform appropriate additional data QC
    - Phenotype data on dbGaP may need more QC applied. This is very specific to the phenotype concept.
    - Internal inconsistencies in study data:
        - Example: Recorded white blood cell subtype counts do not add up to recorded total wbc count for some Framingham subjects. Which measurement is correct (if any)?
        - Example: Diastolic blood pressure higher than systolic blood pressure for some subjects.
    - Possible biologically invalid values
        - Difficult to determine whether an outlier is a recording error vs. a true value (ie due to a loss-of-function variant)

- Performing cross-study analyses for binary traits with different case definitions.
    - Example: One study used a different cutoff for determining diabetes status than another study. Analyzing these variables together is not appropriate. Solution: need to redefine diabetes status the same way for both studies using blood sugar, other measurements, etc.
