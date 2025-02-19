Source Drawing: [[Excalidraw/Deep dive into LLMs|Deep dive into LLMs]]

## 1. FineWeb dataset from huggingface
- 44TB
- Data from CommonCrawl
- 2.7 webpages

## 2. Tokenization
- For custom set of context and data, we can build a tokenizer with only limited number of token. for example 8x8 TOF sensor gesture.
	- [Building a tokenizer, block by block - Hugging Face NLP Course](https://huggingface.co/learn/nlp-course/en/chapter6/8)

## 3. Train your neural network
- GPT-2: Generative pretrained transformer NN
	- Unsupervised Multitask Learners
	- 1.6B
	- 1024 context 
	- 100B train tokens
- 