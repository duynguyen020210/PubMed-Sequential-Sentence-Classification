PubMed Sequential Sentence Classification
This project focuses on sequential sentence classification in medical abstracts using the PubMed 200k RCT dataset. The goal is to classify sentences in medical abstracts into different categories based on their role or function within the abstract.

Dataset:
The dataset used in this project is the PubMed 200k RCT dataset, which consists of approximately 200,000 medical abstracts from PubMed. Each abstract is labeled with sentence-level annotations for categories such as "background," "objective," "methods," "results," and "conclusions." The dataset enables training and evaluating models for sequential sentence classification in the medical domain.

Model Architecture
The model architecture employed in this project is based on the paper "Neural Networks for Joint Sentence Classification in Medical Paper Abstracts" by Franck Dernoncourt, Ji Young Lee, and Peter Szolovits. The proposed architecture combines convolutional neural networks (CNNs) and recurrent neural networks (RNNs) to capture both local and sequential dependencies in the sentences.

The implementation of the model is available in the model.py file. It utilizes popular deep learning frameworks such as TensorFlow or PyTorch (choose the one you used) for building and training the model.

Results
Include a summary of the results achieved by your trained model. This can include metrics such as accuracy, precision, recall, F1 score, or any other relevant evaluation metrics