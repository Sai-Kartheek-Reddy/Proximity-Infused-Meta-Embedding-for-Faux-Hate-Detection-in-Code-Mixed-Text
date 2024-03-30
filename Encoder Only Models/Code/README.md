# 1. Encoder Models:

Encoder models are neural network architectures used for processing sequential data like text, converting it into fixed-dimensional vector representations. They employ layers of processing units such as recurrent neural networks (RNNs), convolutional neural networks (CNNs), or self-attention mechanisms. These models are integral to modern NLP systems, as they transform raw text data into numerical embeddings, capturing both semantic and syntactic information.

## Components of Encoder Models:

## Self-Attention Mechanism:

- Self-attention is a key component of encoder models like BERT, XLM Roberta, Albert, etc. It allows the model to weigh the importance of different words in a sentence when encoding each word's representation. Here's a brief overview:

### Key, Query, and Value:

- Each word in the input sequence generates three vectors - key, query, and value vectors. These vectors are learned during training and represent different aspects of the word.

### Attention Weights:

- The model calculates attention weights by measuring the similarity between the query vector of a word and the key vectors of all other words. These weights determine how much each word should contribute to the representation of the current word.

### Contextual Representation:

- The final representation of each word is a weighted sum of the value vectors of all words, where the weights are determined by the attention weights. This allows the model to capture contextual information effectively.

## Positional Encoding:

- Positional encoding is another crucial aspect of encoder models, ensuring that the model understands the sequential order of words in a sentence. Here's how it works:

### Injecting Positional Information:
  
-Since encoder models like BERT don't inherently understand the order of words in a sentence, positional encoding is added to the input embeddings to convey this information.

### Sinusoidal Functions:

- Positional encoding is typically implemented by adding sinusoidal functions of different frequencies and phases to the input embeddings.

### Learning Positional Relationships:

- By incorporating positional encoding, the model learns to distinguish between words based on their position in the sequence, allowing it to capture sequential relationships effectively.

  Workflow:

# 2. BERT and other Pre-Trained Models Embeddings:

BERT (Bidirectional Encoder Representations from Transformers) is a state-of-the-art pre-trained language model developed by Google, employing bidirectional training and attention mechanisms to understand language contextually. Unlike traditional word embeddings, which consider each word in isolation, BERT takes into account the entire context of a word by using a technique called Bi-Directional training.

- BERT generates embeddings not just for individual words, but for entire sentences or paragraphs.
- These embeddings capture rich contextual information, allowing the model to understand nuances and complexities in language more effectively.
- One key advantage of pre-trained models like BERT is that they have been trained on vast amounts of text data, making them capable of understanding language across a wide range of domains and tasks.
- Instead of training a language model from scratch, we can leverage pre-trained embeddings from models like BERT and fine-tune them for specific downstream tasks, such as sentiment analysis, question answering, or text classification.

## Usage in Project 
In our project, we leverage the "Bert-based-uncased" model to extract embeddings, which are then stored in .pt (PyTorch Tensor format) files for future use. By harnessing pre-trained embeddings from BERT, we improve the performance of natural language processing tasks, facilitating a more precise and nuanced comprehension of textual data.

- The "Bert-based-uncased" model is utilized in our project for extracting embeddings.
- Embeddings extracted from BERT are saved in .pt files, preserving them in PyTorch Tensor format.
- Leveraging pre-trained embeddings from BERT enhances the performance of natural language processing tasks.
- Utilizing BERT embeddings enables a more accurate and nuanced understanding of textual data in our project context.

# 3. Multi-Tasking Model Architecture


