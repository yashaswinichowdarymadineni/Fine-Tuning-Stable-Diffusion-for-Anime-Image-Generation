# Fine-Tuning-Stable-Diffusion-for-Anime-Image-Generation


This project fine-tunes the **Stable Diffusion v1.5** model on a custom anime image dataset using **LoRA (Low-Rank Adaptation)**. The goal is to generate high-quality anime-style images based on text prompts, and evaluate them using Inception Score (IS) and CLIP Similarity Score.

---

## Features

- Fine-tuning with LoRA (via PEFT)
-  Mixed-precision training using 🤗 `Accelerate`
-  Dataset of anime images + prompts (https://www.kaggle.com/datasets/splcher/animefacedataset?resource=download)
- Image generation from custom text prompts
-  Evaluation using:
  - **Inception Score (IS)** for quality and diversity
  - **CLIP Similarity** for prompt-image alignment

---

##  Steps Included

1. **Dataset Preparation**  
   - Images resized to 512x512  
   - Captions collected and aligned with images

2. **Model Fine-Tuning**  
   - LoRA applied to UNet of SD 1.5  
   - Trained for 3 epochs with `AdamW` optimizer  
   - LoRA weights and full model saved

3. **Image Generation**  
   - Used fine-tuned model to generate images from prompts

4. **Evaluation**  
   - Computed Inception Score (IS)  
   - Measured CLIP similarity between prompts and generated images

---

##  Example Prompts

- "a portrait of an anime girl with blue hair"  
- "an anime boy in a futuristic cyberpunk setting"  
- "a fantasy landscape in anime style with dragons and castles"

---

## Output

- Fine-tuned LoRA weights: `fine_tuned_lora_weights/`
- Full model checkpoint: `fine_tuned_stable_diffusion/`
- Sample generated images: `sample_outputs/`

---

##  Requirements

```bash
pip install diffusers transformers accelerate peft datasets ftfy
pip install git+https://github.com/openai/CLIP.git
