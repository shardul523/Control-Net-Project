# Applying ControlNet to Custom Structural and Contextual Conditioning Tasks

**Course:** AID–847 – Applying ControlNet to a Custom Task  
**Team ID:** 14  
**Authors:**  
- Akash Gorakh Chaudhari (MT2024012)  
- Shardul Sisodiya (MT2024140)

---

## 📌 Project Overview

Diffusion-based generative models such as Stable Diffusion produce high-quality images but lack fine-grained controllability over structure and semantic focus. **ControlNet** addresses this limitation by introducing external conditioning signals that guide the diffusion process while preserving the expressive power of pretrained models.

In this project, we explore ControlNet across **two complementary conditioning paradigms**:

1. **Anime Sketch Coloring (Structure-Based Control)**  
   Line-art sketches are used as a *hard structural constraint* to guide colorization while preserving spatial fidelity.
   [Final Model Link](https://huggingface.co/akash00chaudhari/Anime-70)

2. **Saliency-Guided Image Generation (Novel Task)**  
   Contextual saliency masks are used as a *soft spatial prior* to guide semantic attention in conjunction with text prompts.
   [Final Model Link](https://huggingface.co/Shardul-IIITB/salience_mask_control_net)

The project includes dataset preparation, ControlNet training using Hugging Face Diffusers, extensive ablation studies, quantitative and qualitative evaluation, and an interactive demo.

---

## 🧠 Tasks Implemented

### Task 1: Anime Sketch Coloring
- **Control Signal:** Anime-style line-art sketches
- **Target:** Fully colored anime images
- **Control Type:** Hard structural control
- **Key Insight:** ControlNet enforces strict adherence to sketch boundaries while allowing color and texture diversity.

### Task 2: Saliency-Guided Generation
- **Control Signal:** Contextual saliency masks
- **Target:** Natural RGB images
- **Control Type:** Soft contextual control
- **Key Insight:** Saliency acts as an attention prior, guiding *where* content appears rather than enforcing exact geometry.

---

## 🗂 Repository Structure

```text
.
├── anime_sketch_coloring
    ├── P1_Anime_ART.ipynb              # Dataset preparation (both tasks)
    ├── P2_Anime_Art.ipynb              # Anime sketch coloring training & inference
    ├── P3_Anime_Art.ipynb              # Evaluation (SSIM, LPIPS) for anime task
│
├── salience_mask_guided_generation
    ├── Control_Net.ipynb               # Saliency ControlNet training
    ├── Control_Net_Experiments.ipynb   # Ablations (conditioning scale, training duration)
    ├── Control_Net_Evaluation.ipynb    # Saliency task evaluation
    ├── Control_Net_Demo.ipynb          # Interactive demo notebook
    ├── samples_for_demo
        ├── images                      # Contains original ground truth images
        ├── conditioning_images         # Contains the corresponding saliency masks for the ground truth images
        ├── metadata.jsonl              # Contains the mapping between images and conditioning_images as well as the prompt / caption for the original
│
├── Project_Report.pdf         # Final project report
├── README.md                       # This file
