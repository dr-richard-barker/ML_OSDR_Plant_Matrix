---
description: 'Impact of Spaceflight on Plant Biology: A Transcriptome Profiling Approach'
---

# Introduction

Space travel subjects biological systems to unique environmental conditions that diverge significantly from Earth's. For instance, the absence of gravity in space profoundly affects the conventional gravitational signals that organisms rely on. Furthermore, the lack of buoyancy-induced convection in microgravity environments compromises gas exchange and thermoregulation, complicating the situation. These challenges are compounded by an enhanced level of ionizing radiation exposure, which is difficult to accurately simulate in Earth-based models.

To comprehensively understand these multifaceted responses, transcriptome profiling has emerged as a potent method. This technique has shown exceptional utility in studying plant biology under spaceflight conditions. Numerous studies, employing both microarray and RNA sequencing technologies, have been conducted on plants cultivated in space. These studies have predominantly focused on _Arabidopsis thaliana_, a model organism, resulting in a wealth of comparative data.

Through individual and meta-analyses of these experimental outcomes, researchers have begun to illuminate the common responses of plants to the rigors of spaceflight. This insight promises to enhance our understanding of plant biology in extraterrestrial environments and may inform the development of life support and bioregenerative systems for long-duration space missions.&#x20;

In their 2019 study, Choi et al. uncovered that alterations in heat shock and cold-inducible pathways, arising from modifications to oxidative phosphorylation, are part of the plant response to spaceflight. These changes were akin to those observed under high light conditions. In addition, subsequent research, including meta-analyses by Barker et al. (2023), Meyers and Wyatt (2023), and Hughes and Kiss (2022), has elaborated on how unique spaceflight conditions such as anoxic zones around plant tissues, altered cooling patterns, and heightened radiation exposure can impact plant biology.

Despite these significant advancements in comprehending plant responses to spaceflight, the analysis of transcriptome data remains a formidable challenge. This difficulty is primarily due to the heterogeneity in experimental designs across different studies, the complexity of spaceflight environments with undefined stressors, and the limitations in applying terrestrial transcriptional analyses to space environments. It is posited that the relevant transcriptional signatures exist within the data; however, they are often obfuscated by these complicating factors.

#### Background on spaceflight and its effects on plants <a href="#stu98sgs9072" id="stu98sgs9072"></a>

Understanding _Arabidopsis thaliana_ and its responses to spaceflight requires incorporation of transcriptomes, proteomes, metabolomes, genomes, and epigenetic modifications. The GeneLab data repository from NASA has compiled a vast collection of omics datasets in space biology omics data related to spaceflight (Berros et al., 2021). These datasets are crucial to helping us understand how plants might respond during long-duration missions and are particularly important when considering colonization plans that rely on plants as a component of bioregenerative life support for the crew. These analyses are focused on modeling using the model plant Arabidopsis and are accompanied by comprehensive metadata that cover various aspects of each experiment's design.

#### The GeneLab AWG transcriptional matrix and metadata <a href="#id-9bza7s2xmtm3" id="id-9bza7s2xmtm3"></a>

<figure><img src=".gitbook/assets/Slide3.png" alt=""><figcaption></figcaption></figure>

To facilitate comparisons between studies with similar experimental designs, we imported 15 plant transcriptome datasets related to spaceflight from the GeneLab repository using the GeneLab API (Berrios et al., 2021) into an Arabidopsis transcriptional data frame. We then attached the GeneLab Plant Analysis Working Groups manually curated metadata Matrix (referred to as “The Matrix” from Barker et al., 2023). This data frame and metadata matrix only contains a fraction of the GeneLab metadata but allows for more robust comparisons between studies sharing commonalities in the primary treatment experimental design. Previous meta-analyses using the Matrix, Barker et al ., (2023) used DESeq2 linear differential expression models to identify spaceflight-related changes in cell wall processes and oxidative stress. Furthermore, their analysis revealed new response elements such as conserved changes in the expression of genes and shifts in mono and divalent cation transport that are triggered by spaceflight-related treatments. Barker et al., (2023) discuss how their statistical analysis of the Matrix was unable to deconvolute the tissue and hardware factors due to small sample sizes. It also identified factors within the experimental design, such as flight hardware choice, preservation method and assay technique, that may introduce greater variation between datasets than the actual spaceflight treatment itself. The Matrix provides researchers with a powerful tool to explore transcriptomic data generated during spaceflight-related studies in plant biology and highlights new opportunities for additional experiments, controls and analysis methods such as machine learning (ML).

#### Machine learning and its applications in biology <a href="#id-6z4qk69hfddu" id="id-6z4qk69hfddu"></a>

Machine learning (ML) is an emergent field that has the potential to provide powerful new insights into modern and legacy archived data. Wang et al., (2018) showed that the use of ML increased accuracy and sensitivity of identifying differentially expressed genes (DEGs) in RNA-seq data. They assessed the performance of various feature selection algorithms and classification methods to predict DEGs involved in ethylene signaling in Arabidopsis (Want et al., 2018). The top 23 most informative features were identified using ‘InfoGain feature’ selection combined with Logistic Regression classification, demonstrating a powerful prediction capability for the identification of important transcripts from RNAseq. Another study by Holloway _et al.,_ (2007) also used a combination of machine learning combined with traditional RNA-seq analysis methods to greatly improve the sensitivity of differentially expressed genes identification. Their integration of data about known association of TFs and their DNA binding site sequences, allowed them to make new predictions about potential TF target sites in the yeast genome. Eslami, _et al.,_ (2023) showed that both their ML algorithms were able to predict Autism spectrum disorder (ASD) “when all datasets are combined” potentially providing new tools to diagnose both child and adult patients. Taken together Machine learning techniques combined with detailed metadata about the environmental factors and additional genotypic details from subject matters can be used to identify new genetic response operons at a range of developmental stages and species.

### &#x20;<a href="#id-7t6bwfdcno1r" id="id-7t6bwfdcno1r"></a>

#### Results: Machine learning analysis of spaceflight and related stressors <a href="#ckv2tbyl183j" id="ckv2tbyl183j"></a>

[Results from JADBIO](https://app.jadbio.com/share/0eec95b8-95c3-481a-bee7-e742b96c61ab)

[Supplementary table](https://docs.google.com/spreadsheets/d/1f\_0TuJROgpQNYvMKF2Kr69cQbWZGzSNypwZlvdiX5AY/edit?usp=sharing)

