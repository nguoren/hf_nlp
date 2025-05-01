![image](https://github.com/user-attachments/assets/19266367-4074-4104-a293-eaec6bdf7c24)
# [LLM Course](https://huggingface.co/learn/nlp-course)

## Chapter 1: from transformers import pipeline
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
  - summarization
  - text-generation
  - translation
  - zero-shot-classification

 #### Chapter 1 Takeaways
 - Not all models can be used directly from Hugging Face Model Hub
 - Some models require GPUs while others require access
 - There are also limitations to the available models that can be used due to `model_size`
 - Memory space provided for free-tier Google Colab is limited as the models need to be downloaded before use

## Chapter 2: Tokenziers to Models to Labels
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
