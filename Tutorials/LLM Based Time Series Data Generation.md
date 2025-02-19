### Overview
Utilized a Large Language Model (LLM) for generating time series data, specifically fine-tuned with the HAR dataset using llama3.1 16-bit resolution.

### Key Details
- **Model*: llama3.1 16-bit resolution model.
- **Fine-Tuning Tool*: Unsloth (Open-source LoRA and QLoRA finetuning).
- **Training Efficiency*: Training in under 45 minutes with a train loss of 0.35.
	- ~7GB of VRAM
- **LLM Dataset*: Generated 1000 samples of alpaca prompt instructions

- ![[Pasted image 20250131151826.png]]

### Dataset Activities
The dataset includes six activities:
- Walking
- Sitting
- Upstairs
- Downstairs
- Jogging
- Standing
# Example
![[Pasted image 20250131155505.png]]
### Custom Window Sizes
Fine-tuned the model with the following custom window sizes: [10, 20, 30, 6, 8, 12, 15, 25, 18, 22].

## Examples of the output with prompt

- **Create a sequence of length 20 for activity Jogging**
	![[Create a sequence of length 20 for activity Jogging.png]]


- **Create a sequence of length 20 for activity Sleeping**
	![[Create a sequence of length 20 for activity Sleeping.png]]

- **Create a sequence of length 50 for activity Walking**
	![[Create a sequence of length 50 for activity Walking.png]]

- **20 samples of Walking**
	![[20 samples of Walking.png]]

- **30 samples of only X-axis data for the Upstairs activity**
	![[30 samples of only X-axis data for the Upstairs activity.png]]

- **20 Walk**
	![[20 Walk.png]]
