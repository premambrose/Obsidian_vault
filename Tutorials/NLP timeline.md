
# NLP

## Caveats  
* There are a few parts of this outline that are duplicative. I thought it better to have a start to finish approach to learning NLP, PyTorch, and Foundation Models than to spend additional time eliminating duplication. 

## PyTorch Fundamentals  
You want to make sure that you can do the fundamentals in PyTorch. This will give you a better handle as to how to use this. 

### How to get started  
* https://colab.research.google.com/ offers free GPUs. This is a good of a place to start as any. 

* Run locally with a GPU. For me, I use Windows 11 with virtualization. WSL2. Docker for windows, and then I run anything that uses GPUs in a docker container. For experimentation, I use this [dockerfile](nlp\dockerfile) for the data science environment with something similar to the following on the command line:

```bash


# Build from the docker file
docker build --no-cache --pull -f ./dockerfile -t tdock .

# Run with a GPU
docker run -p 127.0.0.1:8889:8889 \
-p 6018:6018 \
 --gpus=1 --cpus=20  \
   -v /mnt/d/consulting/:/home/scott/consulting \
   -v /mnt/d/python/whiteowl/:/whiteowl/ \
   -v /mnt/d/python/tmp/:/home/scott/tmp/ \
   -v /mnt/d/whiteowlconsultinggroup/:/home/scott/whiteowlconsultinggroup/ \
   --name tdock-container tdock:latest
   
```

The evolution is to start off with colab, run notebooks on the cloud, really understand how to train models, deploy models with Google Kubernetes, and then start to evolve in terms of scale.

* https://www.runpod.io offers cheap GPUs, but the platform is not nearly as stable as Google Cloud or AWS. For reference, Open AI runs entirely on Azure clusters. 

### Linear Regression in PyTorch  

* It is important to have an intution as to why outliers can throw a regression.
* It is also important to build up an intuition for what can be done and what can't be done with PyTorch.
* https://towardsdatascience.com/linear-regression-with-pytorch-eb6dedead817 is an ok blog on linear regression.
  * You want to make sure that you understand every line. Ask ChatGPT questions, and really master the basics.


### Logistic Regression in Pytorch  

* This is a basic algorithm that is useful for binary classification. 
  * It is helpful to go through the basics in PyTorch just so that you learn PyTorch.
* https://machinelearningmastery.com/building-a-logistic-regression-classifier-in-pytorch/ is one approach to Logistic Regression
* I have used the scikit version of logistic regression for [sentence embeddings](nlp\2023-10-13-0811-embeddings.ipynb).


### Linear Algebra 
* This [video](https://www.youtube.com/watch?v=J0lLeaWSBWM) (which is part of the PyTorch Lightning videos) starts to explain the uses of linear algebra to build neural networks. 
* My advice is to watch the entire set of [PyTorch Lightning videos](https://www.youtube.com/@PyTorchLightning) before jumping into the remainder of this outline.

### Additional PyTorch Resources and notes  

* [Fast.ai](https://www.fast.ai/posts/2017-09-08-introducing-pytorch-for-fastai.html) is great. It is a good start on how to build AI, and Jeremy Howard really explains things well. 
* It is critical to build out a very basic model in a notebook. Visualize the different steps as you build out because PyTorch is very difficult to debug.
* The whole goal of PyTorch is building a loss function and feeding data into a model so that the model improves on the loss function. As you start to get better at PyTorch, you will focus more and more on data. This blog on [training loss patterns is really good](https://github.com/stas00/ml-engineering/blob/master/instabilities/training-loss-patterns.md) and it gives you a sense as to different patterns that will require you to change data. 
* When you are building out a model, one thing that worked for me is setting up a small training set of data and running it until the data is completely memorized. If your model can't memorize a small set of data over a number of epochs, then you are not going to do well when you start to make your data more diverse. 


## Web Scraping  

* A good approach for web scraping typically involves using Python, [BeautifulSoup4](https://www.crummy.com/software/BeautifulSoup/), and [bright data](https://brightdata.com)
* bright data (or similar providers) are used because some websites have active measures to prevent scraping. Providers that have rotating ip addresses or pools of ip addresses can help to get around this problem. 
* The structure of the data is going to depend on what you are trying to accomplish. For example, take a look at [16:22 of this video by Trellis Research as one possible structure for data](https://youtu.be/E5kzAbD8D0w?si=cLBJZUkHXnR_FBzh&t=982) as one format for extraction. 




## Text Preprocessing 

 Learn about techniques to clean and prepare text data for analysis.

### HISTORY LESSON: Learn Word2Vec (2013) and GloVe (2014) to understand embeddings  

It is important to understand some of the key developments in embeddings before jumping into ideas of converting words to numbers (tokenization).  

Jay Alammar has a series of blogs and YouTubes that give illustrations of various ML topics. Here is a [blog that he has on word2vec](https://jalammar.github.io/illustrated-word2vec/). 
 * Jay's blog is good, but it mixes concepts. Word2vec looked at the probabilites that one word was next to another word. 
 * GloVe was the first time where embeddings showed semantic relationships (e.g. king - man + woman ~= queen).
 * Jay's blog covers the idea of converting words to numbers, and cosine similarity. 


### Tokenization  

In order to use sentences with Open AI models or with other [foundation models ](https://www.adalovelaceinstitute.org/resource/foundation-models-explainer/), you need to convert words into tokens (a sequence of numbers). 

Different open AI models have different lengths of input and different ways of encoding tokens. 

#### Convert a sentence with tiktoken 

If you need to precisely get the number of tokens, tiktoken can help

* https://github.com/openai/tiktoken
* This [tokenizer code](nlp\tokenizer.py) shows how tiktoken can be used to determine how many tokens are generated. 

* Different models are going to require different token lengths (https://www.databricks.com/blog/llm-inference-performance-engineering-best-practices). Some models take more tokens to process. 


#### Tokenization with Ada 

* Modern Language models often have [a transformer](https://jalammar.github.io/illustrated-transformer/) that encodes text into some representation of the training data (a "representation of the world") and a decoder that predicts the next word. 

* If you want a [Retrieval Augemented Generation](https://cookbook.openai.com/examples/fine-tuned_qa/ft_retrieval_augmented_generation_qdrant), you really want to convert a question into an embedding and compare that embedding (via Cosine similarity) against extracts of text.

* You can encode the question and the source text with "cheap" embeddings such as Open AI's Ada.
  * here is [one blog](https://www.datacamp.com/tutorial/introduction-to-text-embeddings-with-the-open-ai-api) on this approach. 



#### Difference between tokenization and embeddings 

* Tokenization is a conversion. It is like a lookup table. It carries no semantic meaning.
* Embeddings are fast to generate. I believe it is just a forward pass through the transformer and it gives a "world view" of the sentence. 
* This makes the use of embeddings great for lookup and sentence classification.



#### Problems with tokenization (too many tokens) 

* Sometimes text might represent a part number or some other word that isn't found in a dictionary. Tokenizers will take part numbers or non-dictionary words and break them up into a series of tokens. As a result, it isn't always ideal to send non-dictionary words as input into a foundation model. 
    * There has to be a judgement call as to whether non-dictionary words are essential in order to answer the question asked from the language model.



### Stemming, Lemmatization, stop word removal 

* These approaches are ok if you are doing something quick and dirty in spacy, but you are losing information with this kind of preprocessing. It is not recommended to use this approach if you are feeding in information into a [Large Language Model](#large-language-model-section).

* Lemmatization is reducing a word like walking or walks to a base word like "walk."
  * [This blog](https://medium.com/mlearning-ai/nlp-03-lemmatization-and-stemming-using-spacy-b2829becceca) goes through lemmatization and stemming. 
  * [This other blog](https://www.educative.io/answers/how-to-remove-stop-words-using-spacy-in-python) gives a quick example of how to do stop word removal. 


## Resume Keyword Extractor Example 

It is best to think about traditional NLP tasks by looking at a specific use case. Here, we are going to look at a resume keyword extractor. It is very common and it is seen on pretty much every job application form.

### Part of Speech tagging 

* One very basic approach to get keywords is to assume that you only want the nouns in a document. spaCy has [capabilities to do this](https://spacy.io/usage/linguistic-features).

### Named Entity Recognition 

* A basic resume extractor may want to pull out the names of companies where a person worked. spaCy has a [EntityRecognizer](https://spacy.io/api/entityrecognizer) that can help with this NamedEntityRecognition


### Sentiment Analysis 

It may be marginally helpful to understand the impact of results in a resume. Sentiment analysis is an extremely marginal approach to this (because most resumes are "highlight reels" and not "critical evaluations"), but it is something. 

Sentiment analysis is something better handled by foundation models, but if you are only using CPUs, and if you aren't using some approach that allows you to use foundation models on CPUs, then you need another approach.

spaCy has a CPU based approach that somewhat works which is discussed in [this blog](https://spacy.io/universe/project/spacy-textblob).

Later in the document, I talk about sentence embedding classification. Personally, if I had to do a quick approach to sentiment, it would be a logistic regression classification with embeddings. The upside here is the sentence embedding classification can be done with just a CPU.




### Where do traditional approaches fail? 

* Traditional approaches are relatively fast and work on CPUs but they are hardly accurate. If you are looking at a resume, you may want the top 5 skills for an applicant and this may or may not match up to the keywords that are listed on a resume. Foundation models solve this. 
* Part of the goal of a resume extractor is to extract out information in STRUCTURED way (e.g. JSON). Tools such as spaCY or [NLTK](https://www.nltk.org/) are simply not going to do a good job of "translating" text into JSON. 



# Large Language Models (LLMs or Foundational Models) 
<a id="large-language-model-section"></a>

After doing entity extraction and basic sentiment analysis, it will be easy to see that techniques such as word2Vec or Glove are only going to get you so far. Large tech companies such as Meta produce large models that do word prection against terbytes of language. This foundation model then can be used to do more powerful NLP approaches. 

Potential uses cases include
* Summarization of emails or automatic evaluation of emails to see if action needs to be taken.
* Automated agents that can run code as part of a response. 

Karpathy gives [a good overview](https://www.youtube.com/watch?v=zjkBMFhNj_g&t=61s) on Large Language Models. It is a hour long video. If you only have 5 minutes, here are the [notes from that video](https://x.com/SarahChieng/status/1729569057475879103?s=20) . 

## Sentence Embeddings 

Use math representations of sentences to do sentence classifications. The leaderboards section of this outline has a link to the MTEB leaderboard, and this leaderboard can be used to fine effective ways to create embeddings.


### Embedding Visualization 

* T-SNE 
  * Here is [a tutorial](https://medium.com/@violante.andre/an-introduction-to-t-sne-with-python-example-47e6ae7dc58f) on t-SNE
  * Useful for making sure that an input embedding is close to embeddings that are held in a vector database (such as Weaviate). Visualizations can be done in [3D](https://stackoverflow.com/questions/52159617/tsne-3d-graph) 
  * Retains max variance and preserves the spatial structure
  * t-SNE is subjective. It depends on the [perplexity](https://www.reddit.com/r/datascience/comments/jzfhwa/tsne_usefulness/) that the user chooses

### Why is vector search fast? 

* Vector search is fast because you can compare your sentence (a series of numbers or a "vector") against the centers of localized cells (Voronoi cells)

![Voronoi diagram](nlp/voronoi.png)

This approach is called Approximate Nearest Neighbors. It has sublinear time on very-large scale data sets.


### HISTORY LESSON: FAISS 

Facebook AI Similarity Search (FAISS) was one of the [first approaches of searching through embeddings in an effective manner](https://github.com/facebookresearch/faiss).

Features of FAISS:
* Handles high dimensional data (e.g. embeddings)

Faiss uses an Approximate Nearest Neighbors approach.


### Cosine Similarity 

Embeddings are a series of numbers (vectors). Cosine similarity is a way to find sentences that are similar to each other. 

Here is an example from the Open AI Cookbook that does [semantic text search using cosine similarity](https://github.com/openai/openai-cookbook/blob/main/examples/Semantic_text_search_using_embeddings.ipynb).

### Sentence Classification 

Here is a CODE EXERCISE that uses embeddings for sentence classification

* [2023-10-13-0811-embeddings.ipynb](nlp\2023-10-13-0811-embeddings.ipynb)
  * Approach uses a logistic regression in order to classify sentences


### Improving Embedding Performance 

Current literature is stating that if there is a problem with sentence embeddings, then [one approach](https://arxiv.org/abs/2307.03104) to improve is to fine tune the model and use the embeddings from the revised model.

A post on [dev.to](https://dev.to/meetkern/how-to-fine-tune-your-embeddings-for-better-similarity-search-445e) with corresponding [github code](https://github.com/qdrant/quaterion) seems to confirm this approach.


## Running an open-source model with Hugging Face  

In general, the more parameters that a model has, the slower the results will be. On the other hand more parameters, sometimes means better performance. 

It is key to look at Huggingface Leaderboards (end of this outline) or other benchmarks to see how well the model is actually going to perform.

### What is Hugging Face? 

Hugging Face (HF) makes it easy to use code in order to download models. It provides a consistent interface, and it has some tools that help with how to run the models. Hugging Face has a lot of leaderboards which show what is state of the art. It also allows researchers to "host" their model online; this is helpful because you can look at the code on how the model was hosted when you are stuck and you are trying to find code that runs a model.

In this outline, HF code is used in some of the code examples.

### Running Zephyr-7b (as opposed to llama-2-13B which has worse performance) 

#### Do math to figure out how much VRAM you need 

The formula that we need to use is: $$M = \frac{(P * 4B)}{(32 / Q)} * 1.2 $$<br>



| Symbol | Description | 
|--------|-------------|
| M | This is GPU memory expressed in GB |
| P | The parameters for this model. In this case 13 | 
| 4B | The number of bytes used for each parameter | 
| 32 | There are 32 bits in a byte | 
| Q | The amount of bits that should be used for loading the model. E.g. 16 bits, 8 bits or 4 bits. |
|1.2 | Represents a 20% overhead of loading additional things in GPU memory. |

Full precision would be fp16. That calculation is 

$$\frac{(13 * 4bytes)}{(32 / 16)} * 1.2 = 31.2GB$$

In comparison, on my NVIDIA RTX 3090, I use 2 GB of GPU to run video, and that leaves me with about 22GB of dedicated GPU memory that is free. This means that full precision is not going to work. 

The general understanding is that [8 bit quantization](https://www.substratus.ai/blog/calculating-gpu-memory-for-llm/) achieves similar performance to using 16 bit. 

With 8 bit quantization, the calculation is:

$$\frac{(13 * 4bytes)}{(32 / 8)} * 1.2 = 15.6GB$$

Ok 15.6 is lower than 22GB of free memory so this should work. 

#### Using Zephyr instead of Llama 2-13b for better performance. 

Zephyr-7B-beta  is a fine tune of Mistral 7B and it is reported to perform MUCH better than llama2-13b (https://www.reddit.com/r/LocalLLM/comments/17beyfs/looking_for_an_intelligent_713b_model/). Mistral is also well known to outperform llama2-13b on all benchmarks.

It them seems appropriate to apply the same formula we have been using to Zephyr. 

$$\frac{(7 * 4bytes)}{(32 / 16)} * 1.2 = 16.8GB$$

It seems that going with Zephyr - 7B out of the box is going to be the way to go. 

#### Quantization 

This is the process of reducing the precision of foundational models. 8 bit quantization seems to give similar performance to 16 bit [source](https://www.substratus.ai/blog/calculating-gpu-memory-for-llm/)

Deeper dive into quantization and how to maximize the utility recieved from a NVIDIA A100 (https://www.databricks.com/blog/llm-inference-performance-engineering-best-practices)

HuggingFace transformers has out of the box support for int8. The former approach for doing this was through [llama-int8](https://github.com/tloen/llama-int8)

For our example, I have an approach that is going to run at 16 bit, and as a result, quantization is not needed. 

#### Code to run Zephyr-7B 

If you upload [this notebook](nlp\Zephyr_7B_colab.ipynb), then you can use it in colab if you change runtime type to TPU. 



### Cloud Options 

* [Runpod](https://www.runpod.io/) (cheap but unstable). Trellis research uses runpod in releated videos. Here is [one video](https://www.youtube.com/watch?v=JJ5mcdEIbj8) that discusses how to set up runpod. 

* Google Kubernetes Engine (GKE more expensive than runpod but more stable)
* AWS EKS (I think this is more expensive than GKE. You would only use it if required by your company)




## Deployment to production 


### Kubernetes with prebuilt docker containers 

Here is [an approach](https://github.com/GoogleCloudPlatform/ai-on-gke/tree/main/tutorials/serving-llama2-70b-on-l4-gpus) from Sam Stoelinga at Google on how to serve Llama 2 70B on just 2 x L4 GPUs. This recipe is relatively straightforward. 

### Docker - Kubernetes - FastAPI 

Approach is to create an API first. The API is going to call the model, and then model returns tokens.

 * Here is [one guide that I found on the topic](https://sumanta9090.medium.com/deploying-a-fastapi-application-on-kubernetes-a-step-by-step-guide-for-production-d74faac4ca36). 
 * The approach should be to learn docker, learn how to deploy an api through docker locally, learn a little about Google Kubernetes Engine (GKE), set up a cluster on GKE, and then deploy to GKE. 



### Use Open AI APIs as needed 

* There is always a balance between building out your own NLP infrastructure or using Open AI. Open AI has [decent documentation](https://platform.openai.com/docs/quickstart?context=python) that for mthe most part is self-explanatory.

* The cost of using Open AI APIs can add up over time. These APIs have fees. The APIs also tend to depreate over a 6 month cycle (so you need to plan for maintenance if you use this approach).

* Open AI has a cookbook that shows the most [common approaches on how to effectively use the APIs ](https://cookbook.openai.com/). It is worth spending some time at a minimum going through the featured section of this cookbook to understand best practicles.

## Development of RAG 

Retrieval Augmented Generation is really just turning base documents into vectors (embeddings), storing those vectors in a database (such as [Weaviate](https://weaviate.io/developers/weaviate/quickstart) ).

There are a ton of examples of how to build a RAG. Open AI has a [blog on it](https://github.com/openai/openai-cookbook/blob/main/examples/fine-tuned_qa/ft_retrieval_augmented_generation_qdrant.ipynb). 

### How is LangChain used to develop RAG? 

LangChain is a "software engineering approach" to LLMs. To me this is extremely counterintuitive, LLMS are built with fine tuning and data. Software engineering only works to a limited extent.

People "like" LangChain though because it is quick to build out. For example, here is a post which has the [LangChain approach to RAG](https://python.langchain.com/docs/expression_language/cookbook/retrieval). Weaviate has [a guide](https://weaviate.io/developers/weaviate/starter-guides/generative) on it as well.

### Alternate approaches

Open AI has [custom GPTs](https://openai.com/blog/introducing-gpts) that can do the majority of what RAGs do. You would build your own RAG if security was a main issue. 


## Keeping up with new breakthroughs 

### X.com 
* Follow me at [@ralphbrooks](https://twitter.com/ralphbrooks) at X.com - Take a look at the ML people I follow. That is a good starting point.

### How to read academic papers 

If you are implementing data science, you probably are not going to have a ton of time to read through a lot of papers. Here is the approach that I use.

* The main guy who talks about papers on Twitter is @_akhaliq. He is a "must follow."

* People on X.com are going to talk about different things. If you have Twitter Premium then you will find a section called "Top Articles." So the approach is to find interesting people on X that I follow, follow them, use Twitter Premium and look at "Top Articles" to see that they thing is interesting.

* If you are trying to implment something quick, you want to first look at [https://paperswithcode.com/](https://paperswithcode.com/) or take a look at model implementations on HuggingFace. Trying to implment papers without code is only something worth doing if the idea in the paper is critical to your use case. 

* There is an art to reading papers. This [blog](https://brianhhu.github.io/2019-09-28-reading-papers/) gives some advice. Jeremy Howard (in his [fast.ai](https://www.fast.ai/) free online course ). Gives other advice. 
  * My advice is that if you see something on twitter getting traction. First check if there is code. If not, make sure you can copy and paste relevant parts of a paper to generate the code that you need. Beyond that, you look at the abstract top part of the paper, and then you look at the conculsion to see if the paper is going to be relevant. Only after doing all of this would you read the paper in full. 

* https://arxiv-sanity-lite.com/ is another resource in order to find interesting papers. 

### Frameworks to use 

* PyTorch seems to be very common for machine learning tasks. 
* I have personally used [PyTorch Lightning](https://lightning.ai/pytorch-lightning/). It builds on PyTorch and has the potential to help as training spans multiple GPUs. There is also a decent series of videos that look at PyTorch and PyTorch Lightning (https://www.youtube.com/playlist?list=PLaMu-SDt_RB55zaDxbuX4DGLC3hIVOGv_) that are worth viewing.  


## Leaderboards 

Leaderboards are useful in order to understand current state-of-the-art based on different metrics.

Language Models - https://huggingface.co/spaces/HuggingFaceH4/open_llm_leaderboard 

HuggingFace Embedding Leaderboard - https://huggingface.co/spaces/mteb/leaderboard 

### Weaknesses of Leaderboards

Some models are designed to score well on leaderboards, but they might do so at the expense of generalizing to other use cases. 


## General References  
### Terminology  
Byte Pair Encoding - This is a way of converting text into tokens. It is reversible and lossless. This means you can turn [the tokens back into the original text](https://github.com/openai/tiktoken).

L4 GPU - This talks about a particular type of NVIDA GPU. 

ML - This is a common abbreviation for Machine Learning.

### Internet  
* subreddit that gives good updates about the latest foundation models: https://www.reddit.com/r/LocalLLaMA/ 
* Weights and Biases puts together a good blog on various Machine Learning topics
* Huggingface puts together a good blog on ML topics (e.g. https://huggingface.co/blog )

* Blog from Google Engineer on calculating VRAM needed to run open source model  - https://www.substratus.ai/blog/calculating-gpu-memory-for-llm/


### YouTube  
* Trelis Research - https://www.youtube.com/watch?v=cmf1lzbyxY8&t=6s 
* Code Your Own AI - https://www.youtube.com/watch?v=aI8cyr-gH6M
* Andrej Karpathy - https://www.youtube.com/watch?v=zjkBMFhNj_g&t=61s 

