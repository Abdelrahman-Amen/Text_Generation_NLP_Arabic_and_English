# Text Generation in Arabic and English using SimpleRNN
This project demonstrates how to build a text generation model using Wikipedia content in both Arabic and English. We utilize Recurrent Neural Networks (RNNs) for sequence prediction, specifically the SimpleRNN layer, to generate text based on input sequences of words.

# Overview
The goal of this project is to build a text generation model that predicts the next word in a sequence of text. We demonstrate this for both English and Arabic languages, using content retrieved from Wikipedia. The model is trained using an RNN-based architecture and generates text based on a seed text provided by the user.

# Model Architecture
The model is built using the following layers:
1. Embedding Layer: Transforms words into dense vectors of fixed size (100 dimensions).
2. SimpleRNN Layer: A basic recurrent layer with 100 units, capturing sequential dependencies in the input text.
3. Dense Layer: The output layer with a softmax activation function that outputs probabilities across the vocabulary size, predicting the next word in the sequence.

#summary:
• Embedding Layer: total_words -> 100
• SimpleRNN Layer: 100 units
• Dense Layer: total_words -> Softmax activation

The model is compiled using the Adam optimizer and uses sparse categorical cross-entropy as the loss function, which is ideal for multi-class classification problems.

# Data

We retrieve data from Wikipedia using the wikipedia Python package. The content of the Wikipedia pages is used to train the model. For the English version, we used the page on "Python (programming language)", and for the Arabic version, we used the page on "صلاح الدين" (Saladin).

English Wikipedia Page: Python (programming language)
Arabic Wikipedia Page: صلاح الدين




# Preprocessing
The text is tokenized into sequences of words using the Tokenizer from Keras. We fit the tokenizer on the text data and convert the text into sequences of integers, where each integer represents a word. We then generate n-gram sequences from the tokenized text.

1. Tokenization: Each word is converted to a unique integer.
2. Sequence Generation: We create input sequences where each sequence contains an increasing number of words from the sentence (n-grams).
3. Padding: The sequences are padded to ensure uniform length across all sequences.


# Training
The model is trained on the tokenized sequences. The input to the model is a sequence of words, and the output is the next word in the sequence. The training process uses the following configurations:

• Loss Function: Sparse Categorical Cross-Entropy
• Optimizer: Adam
• Metrics: Accuracy
• Epochs: 50


# Prediction
Once the model is trained, it can be used to generate new text. A seed text is provided, and the model predicts the next word based on the previous sequence of words. This process is repeated iteratively to generate a sequence of words.

Example:

• English seed text: "Python is"
• Arabic seed text: "صلاح الدين هو"


