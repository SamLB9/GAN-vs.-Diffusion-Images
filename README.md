# MSc Dissertation – Comparative Analysis of GAN- and Diffusion-Generated Images for Generalizable Deepfake Detection
This repository hosts my final MSc Dissertation, completed as part of the MSc in Artificial Intelligence at the University of Edinburgh (2024–2025).  

📄 The full dissertation PDF can be found here: [Access Dissertation](./MSc_dissertation_SLB.pdf)

---

## 📖 Abstract

The rise of photorealistic images from GANs and diffusion models challenges deepfake detection, as current methods often fail on images produced by unseen generative architectures. This dissertation examines shared and distinct visual patterns of GAN- and diffusion-generated images to address these limitations and inform the design of more generalizable detectors. We compare images from six leading generative models with real photographs across ImageNet, Faces, and Bedrooms domains using the ArtiFact dataset, focusing on four feature families: **color moments, high-frequency noise, frequency descriptors, and texture embeddings**.  

Across all domains and descriptors, diffusion models more closely match natural image statistics than GANs. GANs tend to boost brightness, compress color variance, concentrate high-frequency noise around edges, produce steeper-than-natural spectral slopes with depleted high-frequency energy, and yield flatter texture embeddings. Diffusion images partially restore color diversity, noise dispersion, spectral regularity, and texture complexity. This **Real > Diffusion > GAN** hierarchy appears consistently across datasets, revealing architecture-specific fingerprints that can guide robust detection strategies.  

In classification experiments with Random Forests, models trained on real and diffusion images generalize more effectively to unseen GAN samples than the reverse (+8%), though the difference is not statistically significant. Frequency features, while also not statistically superior, show the most consistent performance across domains (+7–13% over other modalities). These results suggest that pairing frequency-based cues with real+diffusion training data offers a lightweight, architecture-agnostic path toward more robust deepfake detection.  

---

## 🛠 Methodology Overview

- **Dataset:** ArtiFact benchmark (GANs and Diffusion) + Real images  
- **Feature extraction:**
  - Color distribution (RGB, HSV, YCrCb)  
  - Local noise statistics (windowed estimators, wavelet decomposition)  
  - Frequency analysis (FFT-based descriptors, spectral decay)  
  - Color histograms and structural embeddings  
- **Classifier:** Random Forests  
- **Evaluation:** Cross-architecture setups with G-score metrics  

---

## 📊 Contributions

This dissertation provides a **systematic comparative analysis** of statistical signatures distinguishing GAN- and diffusion-generated images. Using a diverse set of handcrafted features, the following key contributions are made:

- **Statistical Signature Identification**  
  - Uncovered consistent, domain-invariant differences between GAN- and diffusion-generated images across multiple descriptors.  
  - GANs: increased brightness, reduced color diversity, edge-concentrated high-frequency noise, steeper spectral slopes, depleted high-frequency energy, and flattened texture embeddings.  
  - Diffusion: partial recovery of natural characteristics, including intermediate color variance, dispersed noise patterns, smoother spectral decay, and more complex textures.  
  - These patterns establish a robust **Real > Diffusion > GAN** hierarchy, suggesting reliable architecture-specific fingerprints for deepfake detection.  

- **Generalization Strategy**  
  - Demonstrated that training on **Real + Diffusion** improves generalization to unseen GANs by ~8% compared to the reverse setup.  
  - Although not statistically significant (paired *t*-test), this asymmetry highlights diffusion-based training as a promising foundation for universal detectors.  

- **Feature Evaluation**  
  - Showed that **frequency-domain descriptors** provide the most consistent performance across datasets and generators.  
  - Achieved relative gains of **+7–13% in average G-score** compared to other feature types.  
  - Their stability makes them strong candidates for **lightweight, architecture-agnostic detection systems**.  

---

## 📌 Repository Structure

msc-dissertation/

│── images                  # All figures generated

│── model's weight          # The weight of the chapter 6 model

│── notebooks               # All the ipynb notebooks used for the study 

│── dissertation.pdf        # Full MSc Dissertation

│── README.md               # Project summary
