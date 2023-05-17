# Project Title: Lay Summarisation for BioSentific Journals

This project and the accompanying code represents a joint effort by Zhiheng Wang, Jiarui Liu, Jordy Perry-Greene, and Ahmed Jaafar. Our key aim is to develop a tool that simplifies the understanding of intricate biomedical scientific papers for the broader public, while also ensuring the computational demands remain relatively low.

## Table of Contents

1. [Installation](#installation)
2. [Code](#file_description)
3. [ChatGPT](#AI_Disclosure)
4. [AccessGDrive](#GDrive)


## Installation

The following instructions is required before running the code, those code also exists in ipynb.

```bash
!pip install openai
!pip install sentence-transformers
!pip install tqdm
!pip install scikit-learn
!pip install transformers datasets sentencepiece
!pip install --upgrade accelerate
!pip3 install datasets
!pip3 install rouge_score
!pip install bert_score
!pip install bert-extractive-summarizer
!pip3 install wordfreq
```
## File_description
### Baseline code
#### 1. Extractive method: 
baseline_synonyms_leadK.ipynb, use lead_k synonyms method to generate extractive output
#### 2. Abstractive method: 
baseline_gpt.ipynb, use gpt3 to generate abstractive output

### Our Approach:
#### 1. Extrative method (used): 
topK_sentenceEmbedding_extractive.ipynb.ipynb, get the top k sentences with highest cosine similaries, and use that as the extractive output


#### 2. Abstractive method and fine-tuned Pegasus (the input is the output of Extrative method (used)): 
pegasus_fineturn_and_evaluation_script.ipynb, with the input from topK_sentenceEmbedding_extractive.ipynb.ipynb, fine-tuned pegasus models on the input, and generate the abstractive output

#### 3. Extrative method (discarded because of the cost):  
bertSum_extractive.ipynb

### Human evaluation
making_humaneval_csv.ipynb, this file grabs all the model generated data, ground truth and abstrct and convert it into a csv file for human evaluation <br>
human_evaluation.ipynb, this file blind-folds human evaluator when evaluating so they do not know what model generates the data or if the data is ground-truth or abstract

## AI_Disclosure
From my understanding, a substantial portion of our project was indeed assisted by ChatGPT. However, upon closer inspection, we primarily utilized ChatGPT in a supportive capacity (except the ones clearly stated in the code file). Typical interactions included soliciting help with debugging, such as in instances where the code would not execute under certain conditions. We also sought assistance with enhancing the readability of our comments, converting nested 'for' loops into 'comprehension' loops, or figuring out how to convert a DataFrame into JSON format, among other tasks. 

Importantly, this means that while ChatGPT was a valuable tool in our development process, it did not automatically generate any portion of our code in its entirety. Instead, we leveraged its capabilities as an aid or a supplementary tool, rather than as a standalone code generator.

## GDrive
Here is the google drive link where includes all the model checkpoints, generated data and eLife dataset
https://drive.google.com/drive/u/1/folders/1PTLStbDRehEmie-6HSgnaLfvVrWi9U42
