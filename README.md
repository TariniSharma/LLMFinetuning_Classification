# Overview
---
This repo contains experiments done with respect to [kaggle competition] (https://www.kaggle.com/competitions/llm-classification-finetuning). 
The task is to predict which responses users will prefer in a head-to-head battle between chatbots powered by large language models (LLMs). 

# Experiments performed
## Approach-1
---

Since we have a classification task, with textual inputs - prompt, response1 and response2 and output as softmax scores for each class label \[whether the user prefers response1, response2 or tie\]. For an initial baseline, I considered BertForSequenceClassification and passed fragments of prompt-response1-response2 as a single input to the encoder, where the fragment length depends on analysis done on median, average and maximum encoded length of each input. More details are mentioned in the notebook.

## Approach-2
---
Using a feature based approach, utilized Bert as an embedding model. Since response1 and response2 are conditionally dependent only on the prompt and independent of each other, I create 2 embeddings based on prompt-response1 and prompt-response2 and concatenate them and pass the final concatenated embeddings through a classification head.

## Approach-3
---
Enhancing on approach-2, I added a linear scheduler for updating the learning rate and utilized a smaller batch size due to memory constraints.

## Approach-4
---
Using a finetuning approach, instead of using bert just as an embedding model, I finetune it along with the classification layer.

## Approach-5
---
Enhanced on approach-4 by updating input format to tokenizer to specifically instead Prompt and Response headers. Input to encoder is in the format {Prompt:\<promp\> \n\n Response: \<response\>}


