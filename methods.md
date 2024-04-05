---
description: Data collection and processing
---

# Methods

#### Open Science Data Repository and the GeneLab processed data <a href="#k2ev2cqknvu1" id="k2ev2cqknvu1"></a>

Data collection and preprocessing curation was performed by the NASA GeneLab ([https://genelab.nasa.gov](https://genelab.nasa.gov/)/) as described by Overbey _et al_., (2021) and the NASA Gene Lab plant metadata was curated by the Plant Analysis Working (AWG) group as described previously by Barker _et al._, (2023). In this analysis, the goal was to predict the outcome based on the treatment type using a classification approach. The metric used to optimize the performance of the models was AUC (Area Under Curve). There was no specific grouping feature considered in this analysis. Feature selection was performed, interpretable models were included, but not exclusively used. Extensive tuning efforts were made during the analysis, using a performance protocol involving repeated 3-fold cross-validation without dropping instances, with a maximum of 20 repeats. A total of 3017 configurations were tested, resulting in training 9051 models. The execution utilized two CPU cores and took approximately 5 hours to complete. The JADBio version used for this analysis was 1.4.117. JADBio ML (Tsamardinos, et al., 2022) test configuration from these models (Supplementary table XX1) identified genetic features within the matrix that are associated with the treatment.

#### &#x20;<a href="#m7laxglfo2oe" id="m7laxglfo2oe"></a>

#### Model metrics <a href="#ycdo6g8scqym" id="ycdo6g8scqym"></a>

There are many model evaluation metrics provided by the JADBio ML platform (Tsamardinos et al., 2022); Accuracy allows us to measure the overall correctness of a model. It calculates the proportion of correctly predicted instances (both true positives and true negatives) out of the total number of instances in the dataset. A higher accuracy indicates better performance. Precision: Precision focuses on the correct positive predictions made by the model. It is calculated as the ratio of true positives to the sum of true positives and false positives. Precision tells us how well our model performs in terms of minimizing false-positive predictions. Recall Sensitivity: Recall, also known as Sensitivity or True Positive Rate (TPR), measures how well our model captures all actual positive instances. It is calculated as the ratio of true positives to the sum of true positives and false negatives. Recall provides insights into how effectively our model identifies positive cases from all available positive examples. F1-Score: The F1-Score combines precision and recall into a single metric that balances both aspects. It considers both false-positive and false-negative errors while evaluating a classifier's performance by calculating their harmonic mean. The F1-score ranges from 0 to 1, where 1 represents perfect precision and recall trade-off.

#### AUC and ROC curves. <a href="#qqyt93cj2qoh" id="qqyt93cj2qoh"></a>

The JADBio ML platform provides both AUC and receiver operating characteristic (ROC) curves as QC metrics (Tsamardinos et al., 2022). The AUC curves are a measure of the overall performance of a binary classification model in machine learning. The AUC ranges from 0 to 1, with higher values indicating better performance in distinguishing positive and negative classes. An excellent model typically has an AUC near 1, while an AUC of 0.5 suggests random guessing ability. The AUC curve is scale-invariant and classification-threshold-invariant, meaning it evaluates prediction rankings rather than absolute values and measures prediction quality regardless of the chosen classification threshold. A ROC curve is a graph showing how a classification model performs at different thresholds. This value describes the probability that measures how well a model can distinguish between classes. It plots TPR (True Positive Rate) against FPR (False Positive Rate). This probability-based tool separates "signal" from "noise" and helps predict binary outcomes. The area under the ROC curve serves as a metric for measuring binary classification algorithm performance.



Metadata for 15 OSDR / GeneLab studies were used as described by Barker et al., (2023).





[GLDS-7](https://genelab-data.ndc.nasa.gov/genelab/accession/GLDS-7); [GLDS-17](https://genelab-data.ndc.nasa.gov/genelab/accession/GLDS-17); [GLDS-37](https://genelab-data.ndc.nasa.gov/genelab/accession/GLDS-37); [GLDS-38](https://genelab-data.ndc.nasa.gov/genelab/accession/GLDS-38); [GLDS-44](https://genelab-data.ndc.nasa.gov/genelab/accession/GLDS-44); [GLDS-46](https://genelab-data.ndc.nasa.gov/genelab/accession/GLDS-46); [GLDS-120](https://genelab-data.ndc.nasa.gov/genelab/accession/GLDS-120); [GLDS-121](https://genelab-data.ndc.nasa.gov/genelab/accession/GLDS-121); [GLDS-136](https://genelab-data.ndc.nasa.gov/genelab/accession/GLDS-136); [GLDS-147](https://genelab-data.ndc.nasa.gov/genelab/accession/GLDS-147); [GLDS-205](https://genelab-data.ndc.nasa.gov/genelab/accession/GLDS-205); [GLDS-208](https://genelab-data.ndc.nasa.gov/genelab/accession/GLDS-208); [GLDS-213](https://genelab-data.ndc.nasa.gov/genelab/accession/GLDS-213); [GLDS-218](https://genelab-data.ndc.nasa.gov/genelab/accession/GLDS-218); [GLDS-251](https://genelab-data.ndc.nasa.gov/genelab/accession/GLDS-251).

A normalized counts matrix was made and bound to the GeneLab factors defined by Barker et al., (2023).



Example code used to download and merge the normalized counts data from the OSDR.&#x20;

` R code ``` `

**`#Load libraries`**&#x20;

`library(tidyverse)`&#x20;

`library(data.table)`

**`#Set working directory setwd("Plant_Matrix")`**

`URLs<-c(`

`"https://genelab-data.ndc.nasa.gov/genelab/static/media/dataset/GLDS-120_rna_seq_Normalized_Counts.csv?version17",` &#x20;

`"https://genelab-data.ndc.nasa.gov/genelab/static/media/dataset/GLDS-38_rna_seq_Normalized_Counts.csv?version12",`  &#x20;

`"https://genelab-data.ndc.nasa.gov/genelab/static/media/dataset/GLDS-37_rna_seq_Normalized_Counts.csv?version11",`&#x20;

`"https://genelab-data.ndc.nasa.gov/genelab/static/media/dataset/GLDS-321_rna_seq_Normalized_Counts.csv?version4",`&#x20;

`"https://genelab-data.ndc.nasa.gov/genelab/static/media/dataset/GLDS-218_rna_seq_Normalized_Counts.csv?version10",`   &#x20;

`"https://genelab-data.ndc.nasa.gov/genelab/static/media/dataset/`GLDS-7`_rna_seq_Normalized_Counts.csv",`

`"https://genelab-data.ndc.nasa.gov/genelab/static/media/dataset/`GLDS-17`_rna_seq_Normalized_Counts.csv",`

`"https://genelab-data.ndc.nasa.gov/genelab/static/media/dataset/`GLDS-44`_rna_seq_Normalized_Counts.csv",`

`"https://genelab-data.ndc.nasa.gov/genelab/static/media/dataset/`GLDS-136`_rna_seq_Normalized_Counts.csv",`

`"https://genelab-data.ndc.nasa.gov/genelab/static/media/dataset/`GLDS-147`_rna_seq_Normalized_Counts.csv",`

`"https://genelab-data.ndc.nasa.gov/genelab/static/media/dataset/`GLDS-205`_rna_seq_Normalized_Counts.csv",`

`"https://genelab-data.ndc.nasa.gov/genelab/static/media/dataset/`GLDS-213`_rna_seq_Normalized_Counts.csv",`

`https://genelab-data.ndc.nasa.gov/genelab/static/media/dataset/`GLDS-251`_rna_seq_Normalized_Counts.csv)`



`destFiles<-c(`

`"https://genelab-data.ndc.nasa.gov/genelab/static/media/dataset/GLDS-120_rna_seq_Normalized_Counts.csv?version17",`&#x20;

`"https://genelab-data.ndc.nasa.gov/genelab/static/media/dataset/GLDS-38_rna_seq_Normalized_Counts.csv?version12",`&#x20;

`"https://genelab-data.ndc.nasa.gov/genelab/static/media/dataset/GLDS-37_rna_seq_Normalized_Counts.csv?version11",`&#x20;

`"https://genelab-data.ndc.nasa.gov/genelab/static/media/dataset/GLDS-321_rna_seq_Normalized_Counts.csv?version4",` &#x20;

`"https://genelab-data.ndc.nasa.gov/genelab/static/media/dataset/GLDS-218_rna_seq_Normalized_Counts.csv?version10",`

`"https://genelab-data.ndc.nasa.gov/genelab/static/media/dataset/`GLDS-7`_rna_seq_Normalized_Counts.csv",`

`"https://genelab-data.ndc.nasa.gov/genelab/static/media/dataset/`GLDS-17`_rna_seq_Normalized_Counts.csv",`

`"https://genelab-data.ndc.nasa.gov/genelab/static/media/dataset/`GLDS-44`_rna_seq_Normalized_Counts.csv",`

`"https://genelab-data.ndc.nasa.gov/genelab/static/media/dataset/`GLDS-136`_rna_seq_Normalized_Counts.csv",`

`"https://genelab-data.ndc.nasa.gov/genelab/static/media/dataset/`GLDS-147`_rna_seq_Normalized_Counts.csv",`

`"https://genelab-data.ndc.nasa.gov/genelab/static/media/dataset/`GLDS-205`_rna_seq_Normalized_Counts.csv",`

`"https://genelab-data.ndc.nasa.gov/genelab/static/media/dataset/`GLDS-213`_rna_seq_Normalized_Counts.csv",`

`https://genelab-data.ndc.nasa.gov/genelab/static/media/dataset/`GLDS-251`_rna_seq_Normalized_Counts.csv)`



**`#Download files from URLs and save them to destination files`**

`for (i in 1:length(URLs)){ download.file(URLs[i], destFiles[i]) }`

` PlantMetaMatrix <- read_csv("destFiles") ``` `



