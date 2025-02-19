### Overview
ComfyUI is a powerful tool for generating synthetic images, offering flexibility and the ability to introduce custom nodes. Despite its steep learning curve, it provides rewarding results.

### Key Features
- **Flexibility*: Enhanced image generation capabilities.
- **Custom Nodes*: Ability to add custom nodes for tailored solutions.
- **Learning Curve*: Steep but beneficial.

### Models Used

| Model              | License                              |
| ------------------ | ------------------------------------ |
| Flux.1-Schnell 12B | Apache 2.0 License                   |
| **Flux.1-Dev**     | **Commercial use with restrictions** |
| OpenAI - CLIP      | MIT License                          |
| ControlNet         | Apache 2.0 License                   |
| Flux text encoder  | Apache 2.0 License                   |

- Generated images following DWPose keypoints and skeleton.
- Explored LoRA to enhance realism in the images.
- Working on automating the LLM part of the workflow.
- Developing a consistent face structure across videos and other pipelines.
	- LoRA
	- Stack of Controlnet
- Implementing an image-to-image (img-to-img) workflow.


## Hardware Requirements for finetuning
### Flux.1 [dev, schnell]
- A100-80G (Full tune with DeepSpeed)
- A100-40G (LoRA, LoKr)
- **3090 24G (LoRA, LoKr)**
- 4060 Ti 16G, 4070 Ti 16G, 3080 16G (int8, LoRA, LoKr)
- 4070 Super 12G, 3080 10G, 3060 12GB (nf4, LoRA, LoKr)

Flux prefers being trained with multiple large GPUs but a single 16G card should be able to do it with quantization of the transformer and text encoders.

### SDXL, 1024px
- A100-80G (EMA, large batches, LoRA @ insane batch sizes)
- A6000-48G (EMA@768px, no EMA@1024px, LoRA @ high batch sizes)
- A100-40G (EMA@1024px, EMA@768px, EMA@512px, LoRA @ high batch sizes)
- **4090-24G (EMA@1024px, batch size 1-4, LoRA @ medium-high batch sizes)**
- 4080-12G (LoRA @ low-medium batch sizes)
### Stable Diffusion 2.x, 768px
- **16G or better**



---