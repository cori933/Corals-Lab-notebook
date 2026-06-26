---
layout: post
title: "RT-qPCR Gene Selection and Relative Quantification"
date: 2026-06-26
categories: [RT-qPCR, gene-expression, Stylophora-pistillata]
---

# RT-qPCR Assignment: Gene Selection and Relative Quantification

## Part 1: Proposed RT-qPCR experiment in *Stylophora pistillata*

### Why I chose this topic


 Coral reefs are strongly affected by climate change and marine heatwaves. Higher seawater temperatures can damage the coral host, disturb the relationship between the coral and its symbiotic algae, and eventually contribute to coral bleaching.

This also connects to the paper I presented about selective breeding and coral heat tolerance. In that paper, the main question was whether corals with higher heat tolerance could be selected and bred to produce offspring that survive heat stress better. For this RT-qPCR assignment, I wanted to connect that bigger ecological question to a molecular question: which genes are activated when the coral is exposed to heat?


### Experimental idea

The environmental condition I would like to test is thermal stress.

My planned comparison is:

| Group | Condition |
|---|---|
| Control | 25°C |
| Heat stress | 32°C for 24 hours |
<br>

The idea is to compare coral samples (*Stylophora pistillata*) kept under normal temperature with coral samples exposed to elevated temperature. After the treatment, I would extract total RNA from the coral tissue, convert the RNA (using Reverse transcriptase) into cDNA, and then quantify gene expression using RT-qPCR. 


The main biological question is:

**How does the coral host change the expression of stress-related genes after exposure to heat stress?**

---

## Target gene 1: HSP70

### Why I chose this gene

I chose HSP70 because it is one of the classic genes used to study cellular stress. Heat stress can cause proteins to lose their normal shape, and this can be very damaging for the cell. HSP70 is part of the cell's protection system, so it is a very logical gene to test when asking how corals respond to high temperature.

### Biological function

HSP70 is a heat shock protein and a molecular chaperone. Its role is to help proteins fold correctly, prevent damaged proteins from aggregating, and support cell survival during stressful conditions.

### Expected change in expression

I expect HSP70 expression to increase in the heat-stressed coral samples compared with the control samples.

My reasoning is that at 32°C, the coral cells are expected to experience protein stress. If more proteins are being damaged by heat, the coral should activate genes like HSP70 to help stabilize and repair the cell.

### Why this gene is relevant to thermal stress

Thermal stress directly affects protein stability. Because HSP70 is connected to protein protection during stress, it is a good marker for checking whether the coral host is responding to heat at the cellular level.

---

## Target gene 2: Mn-SOD / SOD2



### Why I chose this gene

I chose Mn-SOD because heat stress is not only a protein-stability problem. It can also create oxidative stress. In corals, elevated temperature can disturb the normal balance between the coral host and its symbiotic algae, and this can increase the production of reactive oxygen species.

### Biological function

Mn-SOD stands for manganese superoxide dismutase. It is an antioxidant enzyme found mainly in the mitochondria. Its job is to convert superoxide radicals into less reactive molecules, so the cell can reduce oxidative damage.

### Expected change in expression

I expect Mn-SOD expression to increase under heat stress, especially if the treatment causes higher oxidative stress.

My reasoning is that if heat stress increases reactive oxygen species, the coral should increase antioxidant protection. Mn-SOD is relevant because it is part of the first line of defense against superoxide radicals.

### Why this gene is relevant to thermal stress

Thermal stress can affect mitochondria and photosynthetic symbionts, both of which are related to reactive oxygen species production. Because Mn-SOD is connected to mitochondrial antioxidant defense, it can help show whether the coral is activating protection against oxidative damage.

---

## Additional target gene: COX1

### Why I included this gene

I also included COX1 as an additional target gene because it connects to my previous bioinformatics assignment. In that assignment, I worked with COX1 in *Stylophora pistillata* for primer design and phylogenetic analysis. Because I already worked with this gene, I wanted to think about how it could also be used in a RT-qPCR context.

I wouldn't use COX1 as my strongest heat-stress marker. HSP70 and Mn-SOD are more directly connected to stress. I included COX1 as an additional gene because it can give information about mitochondrial function and energy metabolism.

### Biological function

COX1 stands for cytochrome c oxidase subunit I. It is a mitochondrial gene involved in the electron transport chain and ATP production. Because mitochondria are important for cellular energy, COX1 can give information about the energetic state of the coral cell.

### Expected change in expression

I would not expect COX1 to behave exactly like HSP70. HSP70 is a direct stress-response gene, while COX1 is more connected to mitochondrial metabolism.

Under short heat stress, COX1 might show a mild decrease, no major change, or a context-dependent response. If heat stress damages mitochondrial function, COX1 expression may decrease. If the coral is still trying to compensate energetically, the response may be weaker or temporary.

### Why this gene is relevant to thermal stress

Heat stress can change the energy demand of the cell and can also affect mitochondrial function. Since COX1 is part of mitochondrial respiration, it can help connect thermal stress with changes in cellular metabolism.

I would interpret COX1 carefully because it is not a classic heat-stress marker. It is better used as an additional gene that gives metabolic context, not as the main evidence for heat stress.

---

## Reference gene: Beta-actin

### Why I chose this reference gene

For normalization in my proposed *Stylophora pistillata* experiment, I would use Beta-actin as a candidate reference gene.

Beta-actin is a structural gene that is involved in the cytoskeleton. It is commonly used as a housekeeping gene because it is needed for basic cell structure and maintenance.

### Why I expect it to stay stable

I expect Beta-actin to remain relatively stable between the control and heat-stress groups because it is not directly part of the heat shock response or antioxidant stress response.

Since RT-qPCR results can be affected by differences in RNA amount, cDNA synthesis, and sample loading. A stable reference gene helps correct for these technical differences.

However, I would still validate Beta-actin before trusting the final results. A reference gene shouldn't be assumed to be stable only because it is called a housekeeping gene. It must be checked under the specific experimental conditions. In a real experiment, I would also consider comparing it with other possible reference genes, such as Tubulin or 18S rRNA.

---

## Summary of selected genes

| Gene | Type | Main function | Expected response under heat stress |
|---|---|---|---|
| HSP70 | Target gene | Protein folding and cellular stress protection | Increase |
| Mn-SOD / SOD2 | Target gene | Mitochondrial antioxidant defense | Increase |
| COX1 | Additional target gene | Mitochondrial respiration and ATP production | Mild decrease, no major change, or context-dependent response |
| Beta-actin | Reference gene | Cytoskeleton and basic cell structure | Stable |

---
<br>
<br>
<br>


# Part 2: Interpreting RT-qPCR data using the ΔΔCt method

## What Ct means

Ct represents the PCR cycle number where the fluorescence signal crosses the threshold.

A lower Ct →  more starting template in the sample.

A higher Ct →  less starting template in the sample.

So in RT-qPCR, the gene with the lower Ct is usually more highly expressed, assuming the reaction worked well.

---

## Why normalization is needed

Raw Ct values can't be compared alone because different samples can have slightly different RNA/cDNA amounts.

In order to correct this, the target gene is normalized to a reference gene.

In the class dataset, the reference gene was **Tubulin**.

---

## Step 1: Calculate ΔCt

The formula is:

`ΔCt = Ct(target gene) - Ct(reference gene)`

ΔCt → represent's the expression of the target gene after correcting for the reference gene.

---

## Step 2: Calculate ΔΔCt

The formula is:

`ΔΔCt = ΔCt(treatment) - ΔCt(control)`

In this class dataset, the comparison is:

**Inhibitor treatment vs. DMSO control**

The DMSO control is the calibrator group.

---

## Step 3: Calculate fold change

The formula is:

`Fold Change = 2^(-ΔΔCt)`

This converts the Ct difference into relative expression.

If fold change = 1 → there is no change compared with the control.

If fold change > 1 → the gene is upregulated in the treatment.

If fold change < 1 → the gene is downregulated in the treatment.

---

## Example calculation: NGN

For NGN:

| Step | Value |
|---|---:|
| Ct NGN control | 28.351 |
| Ct Tubulin control | 23.296 |
| Delta Ct control | 5.056 |
| Ct NGN treatment | 27.353 |
| Ct Tubulin treatment | 23.296 |
| Delta Ct treatment | 4.057 |
| Delta Delta Ct | -0.998 |
| Fold change | 2.00 |
<br>

Because the fold change is about 2.00, NGN expression was approximately doubled in the inhibitor treatment compared with the DMSO control.
<br>
<br>

---
## Class dataset results

| Gene | ΔCt(Control) | ΔCt(Treatment) |   ΔΔCt   | Fold Change |
|---|---:|---:|---:|---:|
| ascs | 5.798 | 5.213 | -0.585 | 1.50 |
| Delta | 2.668 | 2.242 | -0.426 | 1.34 |
| ets | 1.421 | 1.142 | -0.279 | 1.21 |
| foxA | 1.070 | 0.427 | -0.643 | 1.56 |
| gcm | 5.059 | 4.883 | -0.176 | 1.13 |
| NGN | 5.056 | 4.057 | -0.998 | 2.00 |
| opt | 7.725 | 8.413 | 0.688 | 0.62 |
| pak3 | 2.110 | 1.999 | -0.111 | 1.08 |
| pak4 | 2.276 | 1.957 | -0.319 | 1.25 |
| pitx | 6.383 | 8.429 | 2.046 | 0.24 |
| SM30 | -2.327 | -1.529 | 0.798 | 0.58 |
| sm50 | 0.405 | 1.515 | 1.111 | 0.46 |
| soxC | 1.777 | 1.032 | -0.744 | 1.68 |
| synB | 0.831 | 0.764 | -0.067 | 1.05 |

---
<br>

## Final graph

<div align="center">
  <img src="https://github.com/cori933/Corals-Lab-notebook/blob/main/images/qPCR_fold_change_class_data.png?raw=true" alt="Fold Change Graph" width="600">
</div>

<br>

## Final graph interpretation

The final graph shows the fold change values for each gene in the inhibitor treatment compared with the DMSO control.
The control is always set to 1 because it is the calibrator.

The strongest increase was seen in NGN, with a fold change of about 2.00. This means NGN expression was approximately twice as high in the inhibitor treatment compared with the DMSO control.

Other genes that increased were soxC, foxA, ascs, and Delta.

The strongest decrease was seen in pitx, with a fold change of about 0.24. This means pitx expression was much lower in the inhibitor treatment compared with the control.

Other downregulated genes were sm50, SM30, and opt.

Genes like synB, pak3, and gcm were close to 1, so they did not show a strong change in this dataset.

<br>

---

## Main conclusion

The ΔΔCt method allowed me to compare gene expression between inhibitor treatment and DMSO control after normalization to Tubulin.

Overall, the inhibitor treatment seems to increase the expression of some developmental/regulatory genes, especially NGN, while decreasing others such as pitx and sm50.

For a real biological experiment, I would need biological replicates, technical replicates, primer efficiency testing, melt curve checking, and validation that the reference gene is stable.

---

## References

Humanes A et al. 2024. Selective breeding enhances coral heat tolerance to marine heatwaves. *Nature Communications*.

Livak KJ and Schmittgen TD. 2001. Analysis of relative gene expression data using real-time quantitative PCR and the 2^-Delta Delta Ct method. *Methods* 25:402–408.

Bustin SA et al. 2009. The MIQE Guidelines: Minimum Information for Publication of Quantitative Real-Time PCR Experiments. *Clinical Chemistry*.

Kvitt H et al. 2016. The regulation of thermal stress induced apoptosis in corals. *Scientific Reports*.

Montalbetti E et al. 2021. Manganese Benefits Heat-Stressed Corals at the Cellular Level. *Frontiers in Marine Science*.

My previous post: Bioinformatics Project: Primer Design and Phylogeny of *Stylophora pistillata*, COX1 gene.
