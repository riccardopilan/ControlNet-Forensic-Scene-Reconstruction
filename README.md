# Structural Conditioning in Latent Diffusion Models for Forensic Scene Reconstruction

**Program:** MSc in Data Science, University of Padova (UniPD)  
**Course:** Advanced Topics in Data Science  
**Author:** Riccardo Pilan  

**[Download the Full Essay – PDF](ATDS_essay_RiccardoPilan.pdf)**

---

## Overview

This academic essay analyzes the architecture of Latent Diffusion Models (LDMs) and ControlNet, and proposes an application to forensic scene reconstruction. Text-to-image diffusion models guided by CLIP embeddings are very effective at zero-shot generation, but text prompts alone provide weak spatial control and can produce geometric inconsistencies. By adding explicit spatial conditioning through ControlNet, the proposed workflow combines subjective eyewitness testimonies with objective 3D crime scene scans to generate accurate 2D visual reconstructions.

---

## Main Topics Covered

- **Latent Diffusion Models (LDMs):** Forward and reverse diffusion in a compressed latent space via an autoencoder, U-Net noise prediction, and CLIP text conditioning through cross-attention layers, with a focus on computational efficiency and spatial ambiguity issues.
- **ControlNet Architecture:** How ControlNet locks the weights of a pre-trained LDM and adds a trainable encoder copy connected via 1×1 zero-convolutions, decoupling semantic content (text prompt) from geometric constraints (depth maps, Canny edges, semantic segmentation, human pose, normal maps).
- **Proposed Forensic Pipeline:**
  1. **3D Scene Acquisition:** Capturing crime scene geometry as a dense 3D point cloud via Terrestrial Laser Scanning (TLS).
  2. **Viewpoint Projection:** Placing a virtual camera at the witness's declared position and height to render a 2D depth map.
  3. **Conditioned Synthesis:** Using the depth map to condition ControlNet and the eyewitness description to guide CLIP/LDM, reconstructing a 2D view consistent with the physical environment.
- **Investigative Utility and Ethical Limitations:** Practical applications (exploring investigative hypotheses, verifying line-of-sight constraints, comparing conflicting testimonies, and supporting courtroom visualization rather than serving as forensic evidence) and key limitations, including generative hallucinations (with uncertainty modeling as a possible mitigation) and confirmation bias in juries.
  
---

## Repository Structure

- `ATDS_essay_RiccardoPilan.pdf` – Complete essay formatted in CVPR style (5 pages).
- `latex/` – LaTeX source (`ATDS_essay_RiccardoPilan.tex`), BibTeX references (`ATDS_essay_RiccardoPilan.bib`), architecture figures (`ldm_arch.png`, `controlnet_arch.png`), and required CVPR style files (`cvpr.sty`, `cvpr_eso.sty`, `eso-pic.sty`, `ieee_fullname.bst`).
