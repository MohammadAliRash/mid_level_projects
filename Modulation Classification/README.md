# Modulation-Classification
This project develops and evaluates two neural network models, an Artificial Neural Network (ANN) and a Convolutional Neural Network (CNN), for classifying radio modulation signals using the RML2016.10a dataset. The dataset, containing signals with varying signal-to-noise ratios (SNRs) and modulation types, is preprocessed to extract raw signal features. The data is split into training and test sets (70-30 ratio), with labels binarized for multi-class classification. The ANN consists of fully connected layers with ReLU activations, while the CNN incorporates convolutional layers with dropout for robustness. Both models are trained using the Adam optimizer and CrossEntropyLoss, with early stopping to prevent overfitting. Performance is assessed through accuracy across SNRs, precision, recall, F1-score, and confusion matrices. The CNN generally outperforms the ANN, achieving higher accuracy, especially at lower SNRs, due to its ability to capture spatial patterns in signal data. Visualizations, including normalized and raw confusion matrices and accuracy-vs-SNR plots, highlight model performance across modulation types. The results demonstrate the effectiveness of deep learning in radio signal classification, with the CNN showing superior generalization and robustness, making it suitable for real-world applications like spectrum sensing.

The 10 modulation Signals are : 8PSK, AM-DSC, BPSK, CPFSK, GFSK, PAM4, QAM16, QAM64, QPSK, WBFM

Every sample is presented using two vectors each of them has 128 elements. 

Features used:
1. Raw time series as given
2. First derivative in time
3. Integral in time 
4. Combinations of 1, 2 and 3.

Two Model Architecture:
- Fully Connected Neural Network
- Convolutional Neural Network implmeneted from this paper : https://arxiv.org/pdf/1602.04105.pdf

############

