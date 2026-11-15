# Fine-tuning Stable Diffusion on custom images (DreamBooth)

A Google Colab notebook that fine-tunes **Stable Diffusion v1.5** on a small set of your own photos using **DreamBooth**, then generates new images of that subject from text prompts.

## What it does

1. Starts from `runwayml/stable-diffusion-v1-5`.
2. Trains on a handful of images of one subject, tied to a rare token in the prompt (for example `photo of zwx person`), with a class prompt (`photo of a person`) to keep the model from forgetting the general class.
3. Saves the fine-tuned weights.
4. Generates test images from a prompt, with controls for negative prompt, guidance scale, steps, image size and seed.

## Default generation settings

| Setting | Value |
|---|---|
| Guidance scale | 7.5 |
| Inference steps | 25 |
| Image size | 512 × 512 |
| Samples per prompt | 4 |

## Stack

Python · Hugging Face Diffusers · PyTorch · DreamBooth · Google Colab (T4 GPU)

## Run it

1. Rename `Stable_diffusion_fine_tunee.txt` to `Stable_diffusion_fine_tune.ipynb` and open it in Google Colab.
2. Switch the runtime to a GPU (T4 is enough).
3. Paste your own Hugging Face token in the first cell.
4. Set the instance prompt and class prompt, upload 5 to 20 clear images of your subject, and run the training cell.
5. Use the last cell to generate images with your token in the prompt.

## Tips for good results

- Use images with different backgrounds, angles and lighting.
- Crop to a square and keep the subject centred.
- If results look like the training photos copied exactly, reduce the training steps.

## Author

Hamza Abbas · [LinkedIn](https://www.linkedin.com/in/hamza-abbas-851864229/) · [GitHub](https://github.com/HamzaAbbas0)
