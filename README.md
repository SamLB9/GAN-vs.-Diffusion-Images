# MSc Dissertation – Comparative Analysis of GAN- and Diffusion-Generated Images for Generalizable Deepfake Detection
This repository hosts my final MSc Dissertation, completed as part of the MSc in Artificial Intelligence at the University of Edinburgh (2024–2025).  

📄 The full dissertation PDF can be found here: [Access Dissertation](./MSc_dissertation_SLB.pdf)

---

## 📖 Abstract

Generative models such as **GANs (Generative Adversarial Networks)** and **diffusion models** are capable of producing images that are increasingly indistinguishable from authentic photographs. This progress raises concerns regarding **digital authenticity, misinformation, and deepfake detection**.  

In this work, we perform a **comparative analysis of GAN- and diffusion-generated images** using handcrafted statistical features. Four feature categories are extracted:  
- **Color distributions**  
- **Noise patterns**  
- **Frequency statistics**  
- **Texture & structure embeddings**  

Random Forest classifiers are trained on different training regimes to assess **cross-architecture generalization** (e.g., training on GANs and testing on Diffusion, and vice versa).  

Key findings:  
- **Noise and frequency-domain features** consistently outperform color and texture for distinguishing real from synthetic images.  
- Training with **Real + Diffusion** provides stronger generalization to unseen GANs compared to the opposite.  
- Diffusion models appear to partially recover mid-frequency structures absent in GANs, but still fail to replicate authentic sensor noise.  

These results highlight the importance of handcrafted, lightweight descriptors as **robust, model-agnostic tools for deepfake detection**.  

---

## 🛠 Methodology Overview

- **Dataset:** ArtiFact benchmark (GANs, Diffusion, and Real images)  
- **Feature extraction:**  
  - Local noise statistics (windowed estimators, wavelet decomposition)  
  - Frequency analysis (FFT-based descriptors, spectral decay)  
  - Color histograms and structural embeddings  
- **Classifier:** Random Forests  
- **Evaluation:** Cross-architecture setups with G-score metrics  

---

## 📊 Contributions

1. Systematic comparison of handcrafted features for deepfake detection.  
2. Evaluation of **cross-architecture generalization** strategies.  
3. Evidence supporting **diffusion-based training** as a stronger foundation for universal fake image detectors.  

---

## 📌 Repository Structure
msc-dissertation/
│── images                  # All figures generated
│── model's weight          # The weight of the chapter 6 model
│── notebooks               # All the ipynb notebooks used for the study 
│── dissertation.pdf        # Full MSc Dissertation
│── README.md               # Project summary
