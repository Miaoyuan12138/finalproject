# BST260 Final Project Proposal: Data Gaps in Rare Genetic Diseases

## To: BST260 Teaching Team, Fall 2026

### Project theme

For my final project, I would like to study rare genetic diseases and
the uneven amount of information available across different diseases. I
am particularly interested in genetics and rare diseases, and I would
like to use this project to understand not only disease characteristics,
but also possible gaps in the biomedical knowledge available for
different rare conditions.

I plan to use two public biomedical data resources:
**Orphanet/Orphadata** and **ClinVar**. Since these datasets were not
the main datasets used in class, I am requesting approval to introduce
them for this project.

The overall theme of my project is:

> **Which rare genetic diseases are better characterized, and what
> disease characteristics are associated with having more documented
> genetic evidence?**

The project will contain two main vignettes. The first will describe the
epidemiologic and natural-history landscape of rare genetic diseases
using Orphanet. The second will examine genetic evidence in ClinVar and
connect it with disease-level information from Orphanet.

## Vignette 1: The landscape of rare genetic diseases

### Research question

**Among rare genetic diseases, how is estimated disease prevalence
associated with age of onset and other natural-history
characteristics?**

### Dataset

I plan to use public data from **Orphanet/Orphadata**, which provides
structured information on rare diseases, including epidemiology, disease
classifications, associated genes, inheritance, and natural history.

The unit of analysis will be a **rare disease** rather than an
individual patient.

Depending on the completeness of the downloaded data, I plan to focus on
diseases classified as having a known or suspected genetic origin.

### Exposure

The main exposure will be **estimated disease prevalence**.

Orphanet reports epidemiologic information in several formats, including
prevalence estimates and prevalence categories. I will create a
consistent disease-level prevalence variable when possible.

Because prevalence information may not be available for every disease, I
will describe the amount and pattern of missing prevalence information
rather than simply removing all diseases with missing values without
discussion.

### Outcomes

The main outcome will be **age of onset**, represented using the
natural-history categories available in Orphanet.

Depending on data availability, I may also examine age of death or
inheritance pattern as secondary disease characteristics.

Age of onset is categorical or ordinal rather than a precisely measured
continuous outcome for many rare diseases, so I will preserve this
limitation in the analysis rather than treating approximate categories
as exact ages.

### Additional variables

I plan to consider several disease characteristics that may affect the
observed relationship, including:

- mode of inheritance;
- number of genes associated with the disease;
- broad disease classification or medical specialty;
- whether onset is primarily pediatric or adult.

These variables may reflect both biological differences between diseases
and differences in how diseases are recognized and studied.

### Planned analysis

I plan to:

- document the provenance and structure of the Orphanet data;
- describe the distribution of prevalence across rare diseases;
- visualize age-of-onset patterns;
- compare prevalence across inheritance and onset groups;
- examine missingness in epidemiologic and natural-history information;
- use appropriate regression or grouped summaries to study associations
  between disease characteristics.

A major part of this vignette will be evaluating how much information is
actually available for different rare diseases rather than assuming that
missing information is random.

## Vignette 2: Genetic evidence and research gaps in rare diseases

### Research question

**Among rare genetic diseases, are more prevalent diseases associated
with a larger number of pathogenic or likely pathogenic variants
documented in ClinVar?**

### Dataset

The second dataset will be **ClinVar**, a public archive maintained by
the National Center for Biotechnology Information that contains
submitted interpretations of human genetic variants and their
relationships to disease.

ClinVar includes variant-level information such as:

- associated condition;
- gene;
- clinical significance;
- review status;
- type of variant;
- evidence submitted by laboratories or other organizations.

The main unit of analysis for my final analysis will again be a **rare
disease**.

I plan to summarize variant-level ClinVar records into disease-level
measures and then link diseases to Orphanet using available disease
identifiers or cross-references such as OMIM, MONDO, or related
standardized identifiers.

### Exposure

The primary exposure will be **rare-disease prevalence**, obtained from
Orphanet.

I may analyze prevalence either as a continuous or ordinal variable,
depending on how consistently prevalence is recorded.

### Outcome

The primary outcome will be the **number of pathogenic or likely
pathogenic ClinVar variants documented for each disease**.

This is a count outcome, so I will consider a count-based model such as
Poisson regression if its assumptions are reasonable.

I will also examine the total number of ClinVar records and the number
of genes represented for each disease as secondary measures of how
extensively a disease has been genetically characterized.

### Potential confounders and adjustment variables

Before examining the relationship between prevalence and ClinVar
evidence, I plan to consider:

- number of genes known to be associated with the disease;
- inheritance pattern;
- age-of-onset category;
- broad disease category or medical specialty.

For example, a disease involving many genes may naturally have more
documented pathogenic variants even if its prevalence is low.

### Interpretation

I do not plan to interpret the number of ClinVar variants as a direct
measure of biological complexity.

Instead, it may reflect a combination of:

- true genetic heterogeneity;
- disease prevalence;
- availability of genetic testing;
- research interest;
- clinical recognition;
- number of laboratories submitting data;
- historical differences in how long a disease has been studied.

Therefore, an important goal will be to distinguish **biological
interpretation from ascertainment and research bias**.

### Planned analysis

I plan to:

- clean and summarize ClinVar variant-level data;
- identify pathogenic and likely pathogenic records;
- aggregate variants and genes by disease;
- link ClinVar conditions with Orphanet diseases using standardized
  identifiers when possible;
- visualize the distribution of genetic evidence across rare diseases;
- compare highly characterized and poorly characterized diseases;
- model the association between prevalence and the amount of documented
  genetic evidence;
- investigate diseases that are unusual relative to the overall pattern.

For example, I may identify rare diseases that have relatively high
prevalence but very little ClinVar evidence, or extremely rare diseases
that have unusually extensive genetic characterization.

## Cross-dataset objective

The two vignettes address different aspects of the same problem.

The Orphanet vignette describes the **epidemiology and natural history
of rare diseases**, while the ClinVar vignette describes the **available
genetic evidence**.

Combining the two datasets will allow me to ask whether the amount of
genetic knowledge available for a disease is related to how common the
disease is and to other disease characteristics.

I am especially interested in the possibility that the missingness
itself is informative. A disease with limited prevalence information,
few known genes, and few ClinVar records may represent a real knowledge
gap rather than simply an incomplete row in a dataset.

## Data science components

This project will involve several topics that connect directly with
BST260:

- importing and cleaning public biomedical datasets;
- joining datasets from different sources;
- handling different disease identifiers and naming systems;
- tidy data transformation;
- exploratory visualization;
- missing-data analysis;
- grouped summaries;
- regression modeling;
- count data;
- uncertainty and interpretation;
- distinguishing association from causation.

The data-integration step is also scientifically important because
Orphanet and ClinVar describe diseases from different perspectives and
do not necessarily use exactly the same naming conventions.

## Expected limitations

Several limitations will be important.

First, rare-disease prevalence estimates are often uncertain and may
differ across populations.

Second, ClinVar is based on submitted genetic interpretations, so the
absence of variants does not mean that a disease has no genetic basis.

Third, diseases with greater clinical recognition, better access to
genetic testing, or more research funding may have more ClinVar records.

Fourth, linking diseases between Orphanet and ClinVar may not always be
one-to-one because disease terminology and classification can differ
across databases.

For these reasons, I will interpret the analysis as a study of both
rare-disease biology and the structure of available biomedical
knowledge, rather than making causal claims.

## Final goal

The final project will use rare diseases as a setting to examine an
issue that I find especially interesting in health data science: **the
data we observe are partly determined by what medicine has chosen or
been able to measure and study**.

Rather than treating missing data and unequal amounts of genetic
evidence only as technical problems, I want to investigate what these
patterns may tell us about gaps in rare-disease knowledge.
