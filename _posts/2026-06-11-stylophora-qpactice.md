# qPCR Assignment: Gene Selection and Relative Quantification

## Part 1: qPCR Gene Selection and Justification

### Characterizing Gene Expression in *Stylophora pistillata* Under Thermal Stress

#### Introduction
In this assignment, I analyzed the gene expression changes of the reef-building coral *Stylophora pistillata* under acute thermal stress (32°C compared to a 25°C control). Thermal stress induces cellular toxicity, oxidative stress, and triggers coral bleaching, which causes the coral to expel its symbiotic algae. To monitor these cellular alterations, I selected two target genes representing different cellular compartments and physiological pathways, and one stable housekeeping gene.

---

### Target Gene 1: Heat Shock Protein 70 (HSP70)

* **Why did you choose this gene?**
  I chose HSP70 because it is a classic cellular stress marker. Measuring its expression allows me to look at the immediate cellular rescue mechanism activated by the coral host to protect cells during acute heat anomalies.

* **It's known or suspected biological function.**
  HSP70 is a molecular chaperone involved in protein folding, preventing protein aggregation, and degrading damaged proteins under cellular stress.

* **What changes in gene expression do you expect to observe and why?**
  I expected a major increase in the heat-stressed corals compared to the control group, as the cells had to actively synthesize chaperones to mitigate protein damage caused by the elevated temperature.

* **Which stress, treatment, environmental condition, or experimental manipulation do you plan to test?**
  Acute thermal stress, specifically a constant exposure to 32°C for 24 hours compared to a 25°C baseline control.

* **Why is the selected gene relevant to that condition?**
  High temperatures physically destabilize protein structures in coral host cells. Since protein structural collapse is a direct threat to cell survival during marine heatwaves, tracking HSP70 gives a clear indication of how heavily the host deployed its molecular repair machinery.

---

### Target Gene 2: Cytochrome c Oxidase Subunit I (COX1)

* **Why did you choose this gene?**
  I selected COX1 because it is a mitochondrial-encoded gene that allowed me to evaluate whether the metabolic capacity of the host was shifting, shutting down, or trying to compensate to meet the massive energy demands of stress survival.

* **It's known or suspected biological function.**
  COX1 is essential for making ATP in the mitochondrial respiratory chain during oxidative phosphorylation.

* **What changes in gene expression do you expect to observe and why?**
  I expected a decrease in expression after 24 hours. While minor or brief stress might have induced a temporary metabolic spike, prolonged thermal stress typically damaged mitochondrial membranes and suppressed mitochondrial transcription, leading to reduced COX1 expression.

* **Which stress, treatment, environmental condition, or experimental manipulation do you plan to test?**
  Acute thermal stress, specifically a constant exposure to 32°C for 24 hours compared to a 25°C baseline control.

* **Why is the selected gene relevant to that condition?**
  Thermal stress impairs mitochondrial efficiency in corals, often leading to the overproduction of Reactive Oxygen Species (ROS) and metabolic depression. Monitoring COX1 helps pinpoint the exact bioenergetic state of the host cell under extreme temperature stress.

---

### Reference (Housekeeping) Gene: Beta-actin

* **Biological Function:**
  Beta-actin is a major structural component of the eukaryotic cytoskeleton, essential for cell motility, structure, and intracellular transport.

* **Justification for Stability:**
  Unlike metabolic or stress-response genes, structural proteins like Beta-actin maintain highly stable transcription levels across variable environmental conditions. In *Stylophora pistillata*, Beta-actin has been shown to maintain consistent expression profiles during thermal fluctuations, ensuring that changes in target gene Ct values reflect true biological responses rather than fluctuations in template concentration or loading errors.

---

## Part 2: Data Interpretation using the ΔΔCₜ Method

### Theoretical Background of Relative Quantification

Relative quantification determines the changes in steady-state mRNA levels of a target gene relative to a reference gene and a calibrator sample (typically the untreated or control group). 

The mathematical framework is based on the ΔΔCₜ Method (Livak & Schmittgen, 2001), which assumes that the amplification efficiencies of both the target and reference genes are approximately equal and close to 100% (Efficiency = 2).

#### The Mathematical Pipeline

1. **First Normalization (ΔCₜ):** Corrects for variations in RNA input and cDNA synthesis quality within each sample.
   * **Formula:** ΔCₜ = Cₜ(Target) - Cₜ(Reference)

2. **Second Normalization (ΔΔCₜ):** Compares the experimental (treated) sample to the calibrator (control) sample.
   * **Formula:** ΔΔCₜ = ΔCₜ(Treated) - ΔCₜ(Control)

3. **Calculating Relative Expression (Fold Change):** Converts the logarithmic values into a linear biological value.
   * **Formula:** Fold Change = 2^(-ΔΔCₜ)

---

### Step-by-Step Calculation Example

Below is the experimental dataset generated from the *Stylophora pistillata* cDNA samples (Control vs. Heat Stress) and the step-by-step pipeline execution.

#### 1. Raw Data Analysis

| Experimental Group | Replicate | Cₜ Target (HSP70) | Cₜ Reference (Beta-actin) | ΔCₜ [Cₜ(Target) - Cₜ(Ref)] | Mean ΔCₜ |
| :--- | :--- | :---: | :---: | :---: | :---: |
| **Control (25°C)** | Rep 1 | 24.2 | 18.1 | 6.1 | |
| **Control (25°C)** | Rep 2 | 24.4 | 18.3 | 6.1 | **6.1** |
| **Heat Stress (32°C)** | Rep 1 | 20.1 | 18.2 | 1.9 | |
| **Heat Stress (32°C)** | Rep 2 | 19.9 | 18.0 | 1.9 | **1.9** |

#### 2. Computing ΔΔCₜ and Fold Change

Using the mean values calculated in the dataset above:

* ΔΔCₜ = ΔCₜ(Treated) - ΔCₜ(Control)
* ΔΔCₜ = 1.9 - 6.1 = -4.2

* Fold Change = 2^(-ΔΔCₜ)
* Fold Change = 2^(-(-4.2)) = 2^4.2 = 18.38

---

### Summary of Expected qPCR Outcomes

| Gene Symbol | Functional Category | Expected Response (25°C → 32°C) | Primary Cellular Rationale |
| :--- | :--- | :--- | :--- |
| **Beta-actin** | Housekeeping Reference | Stable Baseline (No Change) | Structural actin maintains constitutive expression under brief environmental anomalies. |
| **HSP70** | Molecular Chaperone | Significant Upregulation | Transcriptional activation is triggered to fold denaturing proteins and combat heat damage. |
| **COX1** | Mitochondrial Respiration | Downregulation / Suppression | Severe prolonged heat damages mitochondrial integrity, suppressing target metabolic transcription. |

---

### Data Visualization and Interpretation

#### Final Graph Description
The results should be plotted as a bar chart where the Y-axis represents the Relative Expression Level (Fold Change) and the X-axis presents the experimental groups (Control vs. Heat Stress). 
* The Control bar is set exactly at 1.0 (since 2^0 = 1).
* The Heat Stress bar reaches 18.38, accompanied by standard error bars calculated from the biological replicates.

#### Biological Interpretation
I analyzed the qPCR data, which demonstrates a profound 18.38-fold increase of HSP70 expression in *Stylophora pistillata* following a 24-hour exposure to elevated temperatures (32°C). 

This sharp increase supports my initial biological hypothesis: the hyperthermal conditions induced severe stress within the coral coenosarc. The host cells responded by heavily transcribing molecular chaperones to counter protein damage. 

Because the internal reference gene (Beta-actin) remained highly stable across both treatments (hovering at Cₜ ~ 18.1), I can confidently conclude that the observed shift represents a genuine, targeted physiological response to the environmental manipulation rather than an experimental artifact.