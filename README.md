![image](https://github.com/user-attachments/assets/19266367-4074-4104-a293-eaec6bdf7c24)
# [LLM Course](https://huggingface.co/learn/nlp-course)

## Chapter 1: from transformers import pipeline
<details>
<summary>Chapter 1</summary>
- 3 Main Steps of Pipeline()
  - Text Preprocessing
  - Input to Model to perform Prediction
  - Output Post-processed
 
- Types of Pipeline()
  - feature extraction
  - fill-mask
  - named entity recognition
  - question-answering
  - sentiment-analysis
  - summarisation
  - text-generation
  - translation
  - zero-shot-classification

#### Chapter 1 Takeaways
- Not all models can be used directly from Hugging Face Model Hub
- Some models require GPUs while others require access
- There are also limitations to the available models that can be used due to `model_size`
- Memory space provided for free-tier Google Colab is limited as the models need to be downloaded before use
</details>

## Chapter 2: Tokensiers to Models to Labels
<details>
<summary>Chapter 2</summary>

![image](https://github.com/user-attachments/assets/21946915-9bc2-4422-a132-9e95a516ebe8)

- Text Preprocessing
- Split the text input into pieces, and this process is called **Tokenisation**
- There are different types of tokenisation
  - Word-based
  - Character-based
  - Subword
  - Byte-level BPE, WordPiece, SentencePiece or Unigram
- Convert these pieces into numbers
  - Perform `padding` or `truncation` to become Tensor with shape=(2, 2)
- Input to Transformer Network
  - Transformer Network receives Tensor as input
  - Transformer Network outputs a high-dimensional vector with shape=(2, 16, 768)
    - 2 represents `batch_size`
    - 16 represents `sequence_length`
    - 768 represents `hidden_size`
  - This high-dimensional vector is called `hidden_states` or `features` which is the contextual understanding of the Tensor
- Different Model Heads are used for different tasks eg.
  - Casual/ Masked Language Model
  - Sequence/ Token Classification etc.
  - Model head processes the high-dimensional vector into logits with shape=(2, 2)
- Post-Processing
  - The logits are raw and unnormalised scores and have to be converted to probabilities through a SoftMax layer
  - The probability scores will correspond to the labels
</details>

## Chapter 3: Fine-Tuning a Pretrained Model
<details>
<summary>Chapter 3</summary>

#### Tokeniser
- Input = Text ---> Output =
  - 'input_ids': unique identifiers of the tokens in each sentence
  - 'token_type_ids': indicates words belong to the first and subsequent sentences
  - 'attention_mask': indicates whether the corresponding tokens should be attended to by the attention layers of the model

#### Chapter 3 Takeaways
- Fine-tuning basically is discarding the head of the pretrained model and adding a new head suitable for the new task
- The weights of the pretrained head is discarded while randomly initialising new weights for the new head to be trained
- Fine-tuning is made easy with HuggingFace Trainer API

</details>

## Chapter 6: Tokenisers
<details>
<summary>Chapter 6</summary>

#### Tokenisation Process
1. Normalisation
2. Pre-tokenisation
3. Tokenisation Alogrithm
4. Post-processing

#### Tokenisation Algorithms
- Byte-Pair Encoding:
  - starts with a small vocabulary and learns the merge rules
  - by merging the pair of tokens that is the most frequent
  - tokenises words into subwords by splitting them into characters and then applying the merge rules
- WordPiece:
  - starts with a small vocabulary and learns merge rules
  - learns a merge rules by merging the pair of tokens that maximises a score that privileges frequent pairs with less frequent individual parts
  - tokenises words into subwords by finding the longest subword starting from the beginning that is in the vocabulary, then repeating the process for the rest of the text
- Unigram:
  - starts with a big vocabulary and progressively removes tokens from it
  - adapts its vocabulary by minimising a loss computed over the whole corpus
  - tokenises words into subwords by finding the most likely segmentation into tokens, according to the model

#### Chapter 6 Takeaways

</details>

## Chapter 7: Classical NLP Tasks
<details>
<summary>Chapter 7</summary>

#### Token Classification
1. Named Entity Recognition (NER)
2. Part-of-Speech (POS) Tagging
3. Chunking

#### Tokenisation Algorithms
- Byte-Pair Encoding:
  - starts with a small vocabulary and learns the merge rules
  - by merging the pair of tokens that is the most frequent
  - tokenises words into subwords by splitting them into characters and then applying the merge rules
- WordPiece:
  - starts with a small vocabulary and learns merge rules
  - learns a merge rules by merging the pair of tokens that maximises a score that privileges frequent pairs with less frequent individual parts
  - tokenises words into subwords by finding the longest subword starting from the beginning that is in the vocabulary, then repeating the process for the rest of the text
- Unigram:
  - starts with a big vocabulary and progressively removes tokens from it
  - adapts its vocabulary by minimising a loss computed over the whole corpus
  - tokenises words into subwords by finding the most likely segmentation into tokens, according to the model

#### Chapter 7 Takeaways

</details>

