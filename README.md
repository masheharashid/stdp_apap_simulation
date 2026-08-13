# STDP Simulation of Acetaminophen (APAP) Hepatotoxicity Effects on the Brain

This project models the effects of Acetaminophen (APAP) hepatotoxicity on brain plasticity using Spike-Timing Dependent Plasticity (STDP) and spiking neuron models. The objective is to simulate how liver damage caused by APAP overdose, leading to conditions like hepatic encephalopathy (HE), can impair synaptic function in the brain.

## Table  of Contents 
- [Introduction](#introduction)
- [Methodology](#methodology)
- [Results and Discussions](#results-and-discussions)
- [Conclusion](#conclusion)
- [References](#references)

## Introduction

### Metabolic Detoxification
Metabolic detoxification is a crucial process carried out by liver enzymes to break down drugs, foreign molecules, and hormones, reducing their toxicity or biological activity (Ozougwu, 2017). This process protects the body from harmful substances and helps maintain internal homeostasis. It involves two phases: Phase I, where fat-soluble toxins become more water-soluble, and Phase II, where water-soluble groups are attached for excretion. Constant exposure to harmful substances (ex. APAP overdose) can overwhelm the process, leading to the accumulation of byproducts that damage the liver. 

### Acetaminophen (APAP) & Drug-Induced Liver Injury (DILI) 
Acetaminophen (APAP) is the most popular pain-relieving and fever-reducing over-the-counter medication in the United States. It’s taken by more than 60 million Americans every week (Jaeschke & Ramachandran, 2024; Liao et al., 2023), but it is also the leading cause of acute liver failure (ALF) (Agrawal & Khazaeni, 2023). It results in approximately 250 deaths annually in the United States alone. APAP overdose overwhelms detoxification pathways, leading to the accumulation of a toxic metabolite, N-acetyl-p-benzoquinone imine (NAPQI) (Jaeschke & Ramachandran, 2024). This causes liver cell death, impairing the liver's ability to clear toxins like ammonia from the blood. This toxic buildup of ammonia (hyperammonemia) can then cross the blood-brain barrier and lead to hepatic encephalopathy (HE). 

### Hepatic Encephalopathy (HE)
Hepatic encephalopathy (HE) is a brain dysfunction resulting from severe liver disease (Ferenci, 2017; Oja et al., 2017). HE causes mental changes, cognitive impairment, and coma in the worst cases. There are many other causes of HE, but hyperammonemia is the primary factor. It disrupts the blood-brain barrier and can weaken the synaptic transmission between two neurons (Oja et al., 2017). HE is regarded as a secondary factor of ALF and causes brain edema and cerebral herniation in severe cases (Ghanem et al., 2016). HE is reversible if the underlying liver disease is treated (Ferenci, 2017). 

## Methodology

The project uses the Brian2 neural simulator to implement two Spike-Timing Dependent Plasticity (STDP) neuron models:

1.  **Traditional STDP Neuron Model**: Represents healthy synaptic plasticity with standard parameters for potentiation and depression.
2.  **APAP Toxicity STDP Neuron Model**: Simulates the effects of APAP hepatotoxicity by modifying STDP parameters. This includes a reduced amplitude for synaptic potentiation (`A_pre`) and a lowered maximum synaptic weight (`w`). These changes are designed to reflect impaired plasticity and synaptic depression observed in conditions like hepatic encephalopathy.

Both models receive external Poisson input, and their synaptic weight evolution and spiking activity are monitored over time.

## Results and Discussions

### STDP Weight Evolution
The simulation compared the synaptic weight evolution of the traditional and APAP toxicity STDP models:
*  **Traditional STDP**: Showed a steady, staircase-like increase in synaptic weight from an initial 0.50 to 0.64. This indicates healthy synaptic strengthening and potentiation.
*   **APAP Toxicity STDP**: Started at 0.50 but remained largely flat, with occasional dips, failing to achieve significant strengthening. This demonstrates impaired plasticity under APAP toxicity, simulating the cognitive impairment in HE.

### Spike Raster Plot
Spiking activity of the neurons was also monitored:
*   **Input neuron**: Spiked 29 times.
*   **Traditional STDP neuron**: Spiked 11 times.
*   **APAP Toxicity STDP neuron**: Spiked only 9 times.

This difference in firing rate further supports the disruptive effect of APAP toxicity on synaptic transmission. Weaker synaptic weights in the toxic model lead to lower excitability and reduced spiking in the post-synaptic neuron.

## Conclusion

This simulation effectively demonstrates the impact of APAP hepatotoxicity on brain plasticity:
*   **Normal (Traditional) STDP**: Exhibits healthy synaptic potentiation and increased post-synaptic firing frequency.
*   **APAP Toxicity STDP**: Shows disrupted plasticity with minimal changes in synaptic weights and reduced post-synaptic firing, mirroring the cognitive impairment seen in hepatic encephalopathy caused by APAP overdose.

## References

*   Agrawal, S., & Khazaeni, B. (2023). Acetaminophen Toxicity. In StatPearls [Internet]. StatPearls Publishing. https://www.ncbi.nlm.nih.gov/books/NBK441917/
*   Ansari, A. J., Fatima, N., & Monawwar, M. Evaluation of Some of the Antibiotics in the Management of Hepatic Encephalopathy (HE): An Overview.
*   Ferenci, P. (2017). Hepatic encephalopathy. Gastroenterology report, 5(2), 138-147.
*   Ghanem, C. I., Pérez, M. J., Manautou, J. E., & Mottino, A. D. (2016). Acetaminophen from liver to brain: New insights into drug pharmacological action and toxicity. Pharmacological research, 109, 119-131.
*   Jaeschke, H., & Ramachandran, A. (2024). Acetaminophen Hepatotoxicity: Paradigm for Understanding Mechanisms of Drug-Induced Liver Injury | Annual Reviews. https://www.annualreviews.org/content/journals/10.1146/annurev-pathmechdis-051122-094016
*   Liao, J., Lu, Q., Li, Z., Li, J., Zhao, Q., & Li, J. (2023). Acetaminophen-induced liver injury: Molecular mechanism and treatments from natural products. Frontiers in Pharmacology, 14. https://doi.org/10.3389/fphar.2023.1122632
*   Moles, A., Torres, S., Baulies, A., Garcia-Ruiz, C., & Fernandez-Checa, J. C. (2018). Mitochondrial-lysosomal axis in acetaminophen hepatotoxicity. Frontiers in Pharmacology, 9, 453.
*   Ozougwu, J. C. (2017). Physiology of the liver. International Journal of Research in Pharmacy and Biosciences. https://www.academia.edu/38598619/Physiology_of_the_liver
*   PiLeJe Laboratoire. (n.d.). Detoxification: A “How to” guide. PiLeJe. Retrieved May 7, 2025, from https://www.pileje.com/health-information/detoxification-a-how-to-guide

