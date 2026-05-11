---
layout: post
title: "Primer Design and Phylogenetic Analysis of Stylophora pistillata Using the COX1 Gene"
date: 2026-05-11
categories: bioinformatics
---

## Project Objective
The objective of this workflow is to design specific primers for the identification of *Stylophora pistillata* and to construct a phylogenetic tree to analyze its evolutionary relationship with other Scleractinian corals.

## 1. Background
* **Target Species:** *Stylophora pistillata* (Family: Pocilloporidae).
* **Gene Marker:** Mitochondrial Cytochrome Oxidase Subunit I (COX1).
* **Significance:** COX1 is a widely used DNA barcode in marine invertebrates due to its moderate evolution rate, which allows for species-level differentiation while maintaining conserved regions for universal/group-specific primers.

## 2. Sequence Collection & Alignment
**Methodology:**
* Sequences were retrieved from NCBI GenBank. 
* **Accession Numbers used:** AB441231.1 (*S. pistillata*), AB441233.1 (*Seriatopora sp.*), AB441235.1 (*T. coccinea*), AB441238.1 (*Tubastraea sp.*), and AB441243.1 (*P. lutea*).
* **Software:** MEGA12.
* **Alignment Algorithm:** ClustalW.

**Observation:**
We identified conserved regions across all species (ideal for primer binding) and variable regions (SNPs) that distinguish *S. pistillata* from the other genera.

> **[Insert your alignment screenshot here: images/alignment_1.jpg]**

## 3. Primer Design
Primers were designed using **NCBI Primer-BLAST** based on the AB441231.1 reference sequence.

| Feature | Forward Primer (5' -> 3') | Reverse Primer (5' -> 3') |
| :--- | :--- | :--- |
| **Sequence** | GATATGGCGTTTCCCCGACT | CGAACCTCCAGAGTGTGCTT |
| **Length** | 20 bp | 20 bp |
| **Tm** | 59.89°C | 59.97°C |
| **GC Content** | 55.0% | 55.0% |
| **Product Size** | **156 bp** | |

**Verification:** Primer-BLAST results confirmed high specificity for *Stylophora pistillata* with no significant off-target binding in the selected database.

## 4. Phylogenetic Tree Construction
**Parameters:**
* **Software:** MEGA12.
* **Method:** Neighbor-Joining (NJ).
* **Substitution Model:** Kimura 2-parameter.
* **Bootstrap:** 1000 replicates.

**Interpretation:**
The phylogenetic tree confirms that *Stylophora pistillata* clusters with *Seriatopora sp.* with high bootstrap support, reflecting their shared family (Pocilloporidae). The *Tubastraea* species form a distinct sister clade, as expected.

> **[Insert your tree screenshot here: images/tree_final.png.jpg]**

## References
* [NCBI GenBank](https://www.ncbi.nlm.nih.gov/genbank/)
* [MEGA Software](https://www.megasoftware.net/)
