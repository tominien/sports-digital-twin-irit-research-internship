# Sports Motion Digital Twin (NLF & SAM2)

Research notebook by **Tom Le Ber** and **Tony Perottino**, both in their **final year in the Math & CS double degree of University of Toulouse**.
This repository is part of a **senior year academic research internship** (TER) at **IRIT** (Institute of Research in Computer Science of Toulouse).

This repository contains an exploratory Colab pipeline for a "digital twin" of sports motion: starting from a real video of a dancer/athlete, we estimate body pose, segment the person, and re-render them on new backgrounds.

---

## General Overview

The core of the project lives in a single notebook (CPU-compatible Colab):
- `Rapport d'étude de NLF, Segment Anything & Stable Diffusion - Tom LE BER (22308482) & Tony PEROTTINO (22303877).ipynb`

Conceptually, the project explores the following pipeline:
1. **Pose estimation with NLF**
   - Compare the NLF method with classic 2D pose estimation from **MMPose** on sports / dance footage.
   - Analyse how robust each approach is to occlusions, fast motion and unusual poses.
2. **Segmentation with SAM2**
   - Use of **Segment Anything 2 (SAM2)** to segment the athlete on each frame.
   - Track and refine the mask over time so that the dancer can be cleanly extracted from the background.
3. **Dancer re-projection on new backgrounds**
   - Align the segmented person with simple geometric references (for example, a vertical pole).
   - Re-compose the dancer onto a different background video or image to simulate a *digital twin* performing in a new environment.
4. **Link with diffusion models**
   - The broader internship also studies how this pipeline could be combined with **Stable Diffusion XL** to generate more complex or stylised environments around the athlete.
   - In this repository, the notebook mainly focuses on the *"pose + segmentation + compositing"* parts.

---

## General Overview

- **Notebook**
  - Full end-to-end pipeline in a single Colab-style notebook.
  - Contains:
    - Environment setup (for CPU calculation),
    - Download / loading of small example videos,
    - NLF and MMPose pose-estimation experiments,
    - SAM2 segmentation and visualisation,
    - Background replacement and geometric alignment.

There is a 45 seconds video, sliced frame by frame in this repository.  
We are using this clip for examples but you can replace it by your own video if wanted.

---

## How to Run (Google Colab)
1. Upload the notebook to **Google Colab**.
2. Make sure the runtime is set to **CPU** (GPU is not strictly required for the current version).
3. Run the environment/setup cells:
   - Install the required Python packages,
   - Clone the needed repositories (MMPose, SAM2, etc.).
4. Upload a short **sports / dance video** (top or side view).
5. Follow the sections in the notebook:
   - Pose estimation experiments (NLF vs MMPose),
   - SAM2 segmentation on your frames,
   - Dancer re-projection on a new background.
6. Inspect the generated visualisations and intermediate outputs to evaluate the quality of the digital twin.

---

## Status

This repository is **research-oriented** and meant as a support for a L3 (third & final year undergraduate) internship report.  
The focus is on **experiments and failure analysis**, not on a polished production library (for now at least).

Contributions, issues or questions are welcome if you want to discuss pose estimation, SAM2 or any other point in the project in general.  
Your can contact us at: [tom.leber.toulouse@gmail.com](mailto:tom.leber.toulouse@gmail.com) or [tom.le-ber@utoulouse.fr](mailto:tom.le-ber@utoulouse.fr).
