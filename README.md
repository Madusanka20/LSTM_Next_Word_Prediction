# LSTM Next Word Prediction

This project demonstrates a simple LSTM (Long Short-Term Memory) neural network for predicting the next word in a sequence, trained on a text file.

## Overview

The code implements a basic next-word prediction model using TensorFlow and Keras. It reads text data from a file, tokenizes the text, creates sequences of words, trains an LSTM model on these sequences, and then uses the trained model to predict the next word given a seed text.

## Code Description

### 1. Data Loading and Preprocessing

*   Reads text from `RNN.txt`.
*   Removes punctuation and special characters.
*   Tokenizes the text using `tf.keras.preprocessing.text.Tokenizer`.
*   Creates input sequences by sliding a window over the tokenized text.
*   Pads the sequences to a uniform length.
*   Converts the labels (next words) to categorical (one-hot encoded) format.

### 2. Model Definition

*   Defines an LSTM model using `tf.keras.models.Sequential`.
*   The model consists of an embedding layer, an LSTM layer, and a dense output layer with a softmax activation.

### 3. Model Training

*   Compiles the model with `categorical_crossentropy` loss, the Adam optimizer, and accuracy as the metric.
*   Trains the model using `model.fit`.

### 4. Next Word Prediction

*   The `predict_next_word` function takes a seed text as input.
*   Tokenizes the seed text and pads it.
*   Uses the trained model to predict the probabilities of the next word.
*   Returns the word with the highest probability.
