# Overview
---
This repo contains experiments done with respect to [kaggle competition] (https://www.kaggle.com/competitions/llm-classification-finetuning). 
The task is to predict which responses users will prefer in a head-to-head battle between chatbots powered by large language models (LLMs). 

# Experiments performed
---
## Approach-1
---

Since we have a classification task, with textual inputs - prompt, response1 and response2 and output as softmax scores for each class label \[whether the user prefers response1, response2 or tie\]. For an initial baseline, I considered BertForSequenceClassification and passed fragments of prompt-response1-response2 as a single input to the encoder, where the fragment length depends on analysis done on median, average and maximum encoded length of each input. More details are mentioned in the notebook.

## Approach-2
---



