---
layout: post
title: "qPCR Target Selection and Relative Quantification in Stylophora pistillata"
date: 2026-06-11
categories: stylophora-bioinformatics
---

# qPCR Assignment: Gene Selection and Relative Quantification

## Part 1: qPCR Gene Selection and Justification

### Characterizing Gene Expression in *Stylophora pistillata* Under Thermal Stress

#### Introduction
In this assignment, I investigate the transcriptional response of the reef-building coral *Stylophora pistillata* to acute thermal stress (32°C compared to a 25°C control). Thermal stress induces cellular toxicity, oxidative stress, and can lead to the breakdown of the coral-dinoflagellate symbiosis (coral bleaching). To monitor these cellular alterations, I selected two target genes representing different cellular compartments and physiological pathways, and one robust housekeeping gene.

---

### Target Gene 1: Heat Shock Protein 70 (HSP70)
* **Biological Function:** HSP70 is a molecular chaperone involved in protein folding, preventing protein aggregation, and degrading damaged proteins under cellular stress.
* **Experimental Condition/Stress:** Acute thermal stress (32°C exposure for 24 hours).
* **Justification & Relevance:** High temperatures destabilize protein structures in coral host cells. HSP70 is a classic proteotoxic stress marker. Measuring its expression allows us to quantify the immediate cellular rescue mechanism activated by the host to maintain proteostasis during temperature anomalies.
* **Expected Expression Changes:** I expect a significant up-regulation (hypothesized fold-change > 5) in the heat-stressed corals compared to the control group, as the cells actively synthesize chaperones to mitigate protein denaturation.

---

### Target Gene 2: Cytochrome c Oxidase Subunit I (COX1)
* **Biological Function:** COX1 is a core component of the mitochondrial respiratory chain (Complex IV), driving ATP synthesis through oxidative phosphorylation. 
* **Experimental Condition/Stress:** Acute thermal stress (32°C exposure for 24 hours).
* **Justification & Relevance:** Thermal stress impairs mitochondrial efficiency in corals, often leading to the overproduction of Reactive Oxygen Species (ROS) and metabolic shift or metabolic depression. Monitoring a mitochondrial-encoded gene like COX1 helps evaluate whether the metabolic capacity of the host is being shut down or compensatory up-regulated to meet the energy demands of stress survival.
* **Expected Expression Changes:** I hypothesize a biphasic or down-regulated expression pattern (fold-change < 0.5). While minor stress might induce a brief metabolic spike, prolonged thermal stress typically damages mitochondrial membranes and suppresses mitochondrial transcription, leading to reduced COX1 expression.

---

### Reference (Housekeeping) Gene: $\beta$-actin
* **Biological Function:** $\beta$-actin is a major structural component of the eukaryotic cytoskeleton, essential for cell motility, structure, and intracellular transport.
* **Justification for Stability:** Unlike metabolic or stress-response genes, structural proteins like $\beta$-actin maintain highly stable transcription levels across variable environmental conditions. In *Stylophora pistillata*, $\beta$-actin has been shown to maintain consistent expression profiles during thermal fluctuations, ensuring that changes in target gene Ct values reflect true biological responses rather than fluctuations in template concentration or loading errors.

---

## Part 2: Data Interpretation using the $\Delta\Delta C_t$ Method

### Theoretical Background of Relative Quantification

Relative quantification determines the changes in steady-state mRNA levels of a target gene relative to a reference gene and a calibrator sample (typically the untreated or control group). 

The mathematical framework is based on the **$\Delta\Delta C_t$ Method** (Livak & Schmittgen, 2001), which assumes that the amplification efficiencies of both the target and reference genes are approximately equal and close to 100% (Efficiency = 2).

#### The Mathematical Pipeline

1. **First Normalization ($\Delta C_t$):** Corrects for variations in RNA input and cDNA synthesis quality within each sample.
   $$\Delta C_t = C_{t,\text{Target}} - C_{t,\text{Reference}}$$

2. **Second Normalization ($\Delta\Delta C_t$):** Compares the experimental (treated) sample to the calibrator (control) sample.
   $$\Delta\Delta C_t = \Delta C_{t,\text{Treated}} - \Delta C_{t,\text{Control}}$$

3. **Calculating Relative Expression (Fold Change):**
   $$\text{Fold Change} = 2^{-\Delta\Delta C_t}$$

---

### Step-by-Step Calculation Example

Below is the experimental dataset generated from *Stylophora pistillata* cDNA samples (Control vs. Heat Stress) and the step-by-step pipeline execution.

#### 1. Raw Data Analysis

| Experimental Group | Replicate | $C_t$ Target (HSP70) | $C_t$ Reference ($\beta$-actin) | $\Delta C_t$ ($C_{t,\text{Target}} - C_{t,\text{Ref}}$) | Mean $\Delta C_t$ |
| :--- | :--- | :---: | :---: | :---: | :---: |
| **Control (25°C)** | Rep 1 | 24.2 | 18.1 | 6.1 | |
| **Control (25°C)** | Rep 2 | 24.4 | 18.3 | 6.1 | **6.1** |
| **Heat Stress (32°C)** | Rep 1 | 20.1 | 18.2 | 1.9 | |
| **Heat Stress (32°C)** | Rep 2 | 19.9 | 18.0 | 1.9 | **1.9** |

#### 2. Computing $\Delta\Delta C_t$ and Fold Change

Using the mean values calculated in the dataset above:

$$\Delta\Delta C_t = \Delta C_{t,\text{Treated}} - \Delta C_{t,\text{Control}}$$
$$\Delta\Delta C_t = 1.9 - 6.1 = -4.2$$

$$\text{Fold Change} = 2^{-\Delta\Delta C_t} = 2^{-(-4.2)} = 2^{4.2} \approx 18.38$$

---

### Summary of Hypothesized qPCR Outcomes

| Gene Symbol | Functional Category | Expected Response (25°C $\rightarrow$ 32°C) | Primary Cellular Rationale |
| :--- | :--- | :--- | :--- |
| **`$\beta$-actin`** | Housekeeping Reference | **Stable Baseline** (No Change) | Structural actin maintains constitutive expression under brief environmental anomalies. |
| **`HSP70`** | Molecular Chaperone | **Significant Upregulation** | Transcriptional activation is triggered to fold denaturing proteins and combat heat damage. |
| **`COX1`** | Mitochondrial Respiration | **Downregulation / Suppression** | Severe prolonged heat damages mitochondrial integrity, suppressing target metabolic transcription. |

---

### Data Visualization and Interpretation

#### Final Graph Description
The results should be plotted as a bar chart where the Y-axis represents the **Relative Expression Level (Fold Change)** and the X-axis presents the experimental groups (**Control** vs. **Heat Stress**). 
* The Control bar is set exactly at **1.0** (since $2^{0} = 1$).
* The Heat Stress bar reaches **18.38**, accompanied by standard error bars calculated from the biological replicates.

#### Biological Interpretation
The qPCR data demonstrates a profound **18.38-fold up-regulation** of HSP70 transcript abundance in *Stylophora pistillata* following a 24-hour exposure to elevated temperatures (32°C). 

This sharp increase supports our initial biological hypothesis: the hyperthermal conditions induced severe proteotoxic stress within the coral coenosarc. The host cells responded by heavily transcribing molecular chaperones to counter protein denaturation. 

Because the internal reference gene ($\beta$-actin) remained highly stable across both treatments (hovering at Ct $\approx$ 18.1), we can confidently conclude that the observed shift represents a targeted physiological response to the environmental manipulation rather than an experimental artifact.