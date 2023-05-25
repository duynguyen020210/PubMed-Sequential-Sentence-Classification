
# PubMed Sequential Sentence Classification

This project focuses on sequential sentence classification in medical abstracts using the PubMed 200k RCT dataset. The goal is to classify sentences in medical abstracts into different categories  such as "background," "objective," "methods," "results," and "conclusions" based on their role or function within the abstract.

## Dataset:
The dataset used in this project is the PubMed 200k RCT dataset, which consists of approximately 200,000 medical abstracts from PubMed. [Download Dataset](https://github.com/Franck-Dernoncourt/pubmed-rct)

- PubMed 20k is a subset of PubMed 200k. Any abstract present in PubMed 20k is also present in PubMed 200k.
- PubMed_200k_RCT is the same as PubMed_200k_RCT_numbers_replaced_with_at_sign, except that in the latter all numbers had been replaced by @. (same for PubMed_20k_RCT vs. PubMed_20k_RCT_numbers_replaced_with_at_sign).

Each abstract is labeled with sentence-level annotations for categories such as "background," "objective," "methods," "results," and "conclusions." The dataset enables training and evaluating models for sequential sentence classification in the medical domain.

## Model Architecture
The model architecture employed in this project is based on the paper "Neural Networks for Joint Sentence Classification in Medical Paper Abstracts" by Franck Dernoncourt, Ji Young Lee, and Peter Szolovits.

The model architecture consists of several components and input branches that are combined to make predictions. Here's an overview of the architecture:

- Token Model: Utilizes the Universal Sentence Encoder model from TensorFlow Hub for token embeddings. The token inputs are passed through the embedding layer and then through a Dense layer with 128 units and ReLU activation.

- Character Model: Accepts character inputs as strings. Converts characters to vectors using a character vectorizer.Embeds the character vectors using an embedding layer. Applies a bidirectional LSTM layer with 8 units to capture contextual information from characters.

- Line Number Model: Accepts numeric inputs representing line numbers. Passes the inputs through a Dense layer with 64 units and ReLU activation.

- Total Lines Model: Accepts numeric inputs representing total lines. Passes the inputs through a Dense layer with 64 units and ReLU activation.

- Concatenation and Dense Layers: The outputs of the token and character models are concatenated using the Concatenate layer.
The concatenated embeddings are passed through a Dense layer with 256 units and ReLU activation. A dropout layer with a dropout rate of 0.5 is applied to prevent overfitting.

- Concatenation with Positional Embeddings: The outputs of the line number model, total lines model, and dropout layer are concatenated using the Concatenate layer.

- Output Layer: The final concatenated embeddings are passed through a Dense layer with the number of units equal to the output shape (5 in this case). The activation function used is softmax, which provides probabilities for each class in the output layer.

**Overall Model**: The model takes inputs from the line number model, total lines model, token model, and character model.
The outputs are generated through the output layer.
This model architecture allows for combining different types of inputs (token, character, line numbers, and total lines) and learning their representations to make predictions on the output classes.



## Results
The model achieved an accuracy of 88.4% on the evaluation dataset, indicating its ability to classify instances correctly. With a precision of 88.6% and recall of 88.4%, the model shows a balanced performance in correctly predicting positive instances. The F1-score of 0.883 further demonstrates the model's overall effectiveness in classification tasks.
This is my actually performmence:

`{'accuracy': 0.8840402807445834,
 'precision': 0.8855787236314059,
 'recall': 0.8840402807445834,
 'f1-score': 0.882550567428959}`

## References:
[Neural Networks for Joint Sentence Classification in Medical Paper Abstracts](https://arxiv.org/abs/1612.05251)
[PubMed 200k RCT: a Dataset for Sequential Sentence Classification in Medical Abstracts](https://arxiv.org/abs/1710.06071)

