
#  Bioinformatics Project: Primer Design and Phylogeny of Stylophora pistillata

### 1. Project Objective
**Title:** Designing Primers and Building a Phylogenetic Tree for the Coral *Stylophora pistillata* (COX1 Gene).

**Objective:** For this project, I chose to work on *Stylophora pistillata* because it is the main focus of my M.Sc. research. My goal was to design specific PCR primers for its mitochondrial COX1 gene and see how it relates to other corals using a phylogenetic tree.

### 2. Target Species and Gene
* **The Organism:** *Stylophora pistillata*. It is a very important reef-building coral.
* **The Gene:** Mitochondrial COX1 (Cytochrome c oxidase subunit I).
* **Why I used this gene:** COX1 is the standard "barcode" for identifying animals. It is great for this project because it has enough differences to tell species apart, but also has stable areas where I can design primers.

### 3. Collecting Sequences from NCBI
I went to the NCBI GenBank website and searched for COX1 sequences in FASTA format. I chose the following sequences for my analysis:
* *Stylophora pistillata* (Target): AB441231.1
* *Seriatopora sp.*: AB441233
* *Tubastraea coccinea*: AB441235
* *Tubastraea sp.*: AB441238.1
* *Porites lutea*: AB441243.1

### 4. Sequence Alignment
I aligned the five COX1 sequences to see where the DNA is the same and where it changes between the species.
* **Software:** MEGA12 (using the ClustalW tool).
* **Conserved Regions:** In the alignment image below, I can see long blocks of color that are identical across all 5 corals. These are the conserved regions. For example, the middle and right sections of this alignment are very stable.
* **Variable Regions & SNPs:** I also found a few spots where the colors change in only one or two species. These Single Nucleotide Polymorphisms (SNPs) are important because they show the small genetic differences between my target *Stylophora* and the other corals.
* **Indels:** I looked for any gaps or dashes (indels) in the alignment, but there are none. This is normal for the COX1 gene because it needs to stay intact to function properly.

<br>

**My Alignment Result:**
<img src="../images/alignment_1.jpg" alt="Multiple Sequence Alignment" style="width: 100%; max-width: none; display: block;">
<br>

### 5. Designing the Primers
I used the alignment to find the best flanking regions for my primers, ensuring they are specific to *Stylophora pistillata*.
* **Software:** NCBI Primer-BLAST.
* **Forward Primer (5'->3'):** GATATGGCGTTTCCCCGACT
  * **Position:** 221 - 240
* **Reverse Primer (5'->3'):** CGAACCTCCAGAGTGTGCTT
  * **Position:** 357 - 376
* **Primer Details:**
  * **Length:** 20 bp each.
  * **Melting Temperature (Tm):** 59.89°C (F) | 59.97°C (R).
  * **GC Content:** 55%.
* **Expected Amplicon Size:** 156 bp.

<br>

### 6. Verification
I checked my primers again using NCBI Primer-BLAST. The results showed that these primers are specific to *Stylophora* and should not amplify other organisms by mistake.


### 7. Building the Phylogenetic Tree
To see the evolutionary connections, I made a tree using the aligned COX1 sequences.
* **Software:** MEGA12.
* **Method:** Neighbor-Joining.
* **Model:** Kimura 2-parameter (K2P).
* **Test:** 1000 bootstrap replicates to make sure the tree is strong.

<br>

**Final Phylogenetic Tree:**

![Phylogenetic Tree](../images/tree_final.jpg)


### 8. Interpretation of the Phylogenetic Tree
Looking at the phylogenetic tree, I can draw the following conclusions:
* **Clustering:** As I expected, *Stylophora pistillata* is very close to *Seriatopora sp.* They belong to the same family (Pocilloporidae), and the tree shows this clearly.
* **Other Groups:** The species *Tubastraea coccinea*, *Tubastraea sp.*, and *Porites lutea* are on different branches, which makes sense because they are more distantly related to *Stylophora*.
* **Tree Reliability:** To ensure the results are strong, I used 1000 bootstrap replicates in MEGA12. This confirms that the connections I see in the tree are statistically reliable.