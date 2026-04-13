# FeedbackGAN-Based Molecular Design for nAChR Drug Discovery

**Independent Research Project**  
Lawrence Livermore National Laboratory — Remote  
Mentor: Dr. Edmond Y. Lau | Aug 2024 – Aug 2025

---

## Overview

This project investigates the application of a Feedback Generative Adversarial Network (FeedbackGAN) framework for de novo molecular design targeting nicotinic acetylcholine receptor (nAChR) subtypes α4β2 and α7, with the goal of identifying selective partial agonist candidates for nicotine cessation therapy.

The framework adapts the multiobjective optimization architecture introduced by Abbasi et al., incorporating an Encoder-Decoder module for latent space molecular representation, a GAN-based generative network, an LSTM Predictor for property evaluation, and NSGA-II for multi-objective candidate refinement, balancing binding affinity and synthetic accessibility.

---

## Scientific Motivation

Nicotine addiction causes over 8 million deaths annually. Current cessation therapies like varenicline are effective but limited by selectivity challenges across nAChR subtypes. The α4β2 subtype drives nicotine's rewarding effects through mesolimbic dopamine pathways, while α7 modulates glutamatergic transmission — making differential selectivity between these subtypes a meaningful therapeutic objective.

Traditional drug discovery for this target space is slow and expensive. This project explores whether GAN-based molecular generation can accelerate exploration of the relevant chemical space.

---

## Dataset

Curated dataset of known nAChR α4β2 and α7 ligands compiled from:
- ChEMBL (allosteric modulators excluded, filtered for orthosteric binding data)
- BindingDB

Molecular preprocessing pipeline:
- SMILES validation and sanitization via RDKit
- Descriptor generation including LogP, molecular weight, polar surface area
- Drug-likeness filtering using Lipinski's Rule of Five
- In-silico ADMET property estimation via SwissADME

---

## Challenges and Learnings

- GAN training instability was a significant challenge — discriminator loss collapsed in early training runs, consistent with known failure modes in molecular GANs
- Conditioning the generator on receptor-specific pharmacophoric features without sufficient target-specific training data introduced distribution mismatch challenges
- Balancing NSGA-II multi-objective optimization across binding affinity proxies and synthetic accessibility required iterative reward function tuning
- Developed understanding of where current GAN-based approaches break down for low-data receptor-specific molecular design tasks

---

## Technical Stack

- Python 3.9.7
- TensorFlow 2.7
- RDKit 2020.6.8
- CUDA 11.6 / NVIDIA GPU
- NumPy 1.21.2, tqdm 4.47.0, seaborn

---

## Acknowledgments

Mentored by Dr. Edmond Y. Lau, Lawrence Livermore National Laboratory.
