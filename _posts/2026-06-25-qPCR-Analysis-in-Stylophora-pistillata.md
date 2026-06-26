---
layout: post
title: "qPCR Analysis in Stylophora pistillata"
date: 2026-06-25
---
## Introduction

In this assignment, I analyzed the gene expression changes of the reef-building coral *Stylophora pistillata* under acute thermal stress (32°C compared to a 25°C control). Thermal stress, a critical consequence of the global climate crisis, induces cellular toxicity, oxidative stress, and triggers coral bleaching, which causes the coral to expel its vital symbiotic algae. To monitor these cellular alterations and understand the host's physiological response, I selected two target genes representing different cellular compartments and pathways, and one stable housekeeping gene.

---

## Part 1: qPCR Gene Selection and Justification

### Target Gene 1: Heat Shock Protein 70 (HSP70)

**Why did you choose this gene?**
Because of the global climate crisis, coral reefs are facing unprecedented thermal stress. I chose HSP70 because it serves as the most critical marker for understanding how *S. pistillata* attempts to survive these rising ocean temperatures. It allows me to measure the active cellular response to the heat that is currently threatening the survival of coral reefs worldwide.

**Biological Function:**
A molecular chaperone involved in protein folding and preventing aggregation during periods of cellular proteotoxic stress.

**Expected Changes:**
Significant upregulation in heat-stressed corals to mitigate protein damage caused by thermal anomalies.

**Condition & Relevance:**
Climate change is causing extreme temperature fluctuations. Tracking HSP70 allows us to quantify the deployment of the coral's molecular repair machinery, providing a direct link between environmental thermal stress and the organism's physiological response.
<br>
<br>


### Target Gene 2: Cytochrome c Oxidase Subunit I (COX1)

**Why did you choose this gene?**
I selected COX1 because, in the context of warming oceans, the metabolic cost for corals to maintain homeostasis is increasing significantly. I wanted to see if the mitochondrial machinery, which is essential for survival in a warming environment, remains functional or begins to collapse under the pressure of climate-driven heat stress.

**Biological Function:**
Essential for ATP production in the mitochondrial respiratory chain.

**Expected Changes:**
Downregulation after 24 hours, reflecting metabolic depression and mitochondrial damage.

**Condition & Relevance:**
This gene helps pinpoint the bioenergetic state of the host cell under extreme temperature stress, which is a direct consequence of the changing climate affecting reef ecosystems.

### Reference (Housekeeping) Gene: Beta-actin

**Why did you choose this gene?**
Structural proteins like Beta-actin are typically constitutively expressed and maintain stable transcription levels across diverse experimental conditions. This stability is essential to ensure that differences in target gene $C_t$ values reflect true biological responses to the experimental stress, rather than variations in input RNA or reverse transcription efficiency.

---

## Part 2: Data Interpretation (Relative Quantification)

### The ΔΔCₜ Method

Relative quantification is performed using the Livak method (ΔΔCₜ). This approach normalizes the target gene expression to the reference gene, accounting for variations in input RNA or reverse transcription efficiency.

**The calculation pipeline:**

1. **ΔCₜ:** Calculate the difference between target and reference genes:

$$\Delta C_t = C_{t,target} - C_{t,reference}$$
<br>


2. **ΔΔCₜ:** Compare experimental to control:

$$\Delta\Delta C_t = \Delta C_{t,treatment} - \Delta C_{t,control}$$
<br>


3. **Fold Change:** Calculate relative expression:

$$Fold Change = 2^{-\Delta\Delta C_t}$$


<br>

### Results

<div align="center">

| Experimental Group | Target (HSP70) | Reference (Beta-actin) | ΔCₜ |
| --- | --- | --- | --- |
| Control (25°C) | 24.3 | 18.2 | 6.1 |
| Heat Stress (32°C) | 20.0 | 18.1 | 1.9 |

</div>

<br>
<br>


**Detailed Calculations:**



ΔCt (Control) = 24.3 - 18.2 = 6.1


ΔCt (Heat Stress) = 20.0 - 18.1 = 1.9


ΔΔCt = 1.9 - 6.1 = -4.2


**Fold Change** = $2^{-(-4.2)}$ = **18.38**






<br>

### Interpretation
The data demonstrates an 18.38-fold increase of HSP70 expression under heat stress. This confirms that the coral host cells actively responded to the thermal anomaly by deploying molecular chaperones. The reference gene (Beta-actin) remained stable throughout the experiment, validating the biological significance of this result.


---

### **Note on Data Source**
*The data for this study are based on my previous work: [Bioinformatics Project: Primer Design and Phylogeny of Stylophora pistillata](https://cori933.github.io/Corals-Lab-notebook/stylophora-bioinformatics/).*
