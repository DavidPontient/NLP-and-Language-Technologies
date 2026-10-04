David's Part: Baselines, LSTM, and Transformer

This folder contains my part of the group's Formative 2 assignment (Research-Informed Sequential Models for NLP and Language Technologies), using the Swahili Audio Classification dataset.

What's here
File	Description
Formative2_NLP_LSTM_Swahili_Audio_David.ipynb	Full notebook: data loading, MFCC feature extraction, both baselines, the LSTM, and the Transformer
lstm_learning_curves.png	LSTM accuracy and loss over 30 training epochs
lstm_confusion_matrix.png	LSTM confusion matrix across all 12 classes
transformer_confusion_matrix.png	Transformer confusion matrix across all 12 classes
lstm_misclassified_examples.csv	Sample of LSTM misclassified clips, with true and predicted labels
results_summary.txt	Accuracy numbers for all 4 of my models
My role in the group

The group used 5 approaches total (at least 3 neural, plus 2 baselines) on the Swahili Audio Classification dataset, 4200 training clips across 12 balanced classes (the Swahili words one through ten, plus yes/no).

I built:

2 baselines: Logistic Regression and Random Forest, trained on averaged MFCC features
2 neural sequential models: an LSTM and a Transformer encoder, both trained on full MFCC sequences

My teammate built the group's third neural model (CNN) and handled the Data & Related Work and Error Analysis & Report Assembly sections.

Results
Model	Accuracy
Logistic Regression (baseline)	19.4%
Random Forest (baseline)	13.9%
LSTM (neural, recurrent)	75.2%
Transformer (neural, attention-based)	73.5%
Key finding

Both baselines performed barely above random chance (8.3% for 12 classes), since averaging MFCC features over time destroys the timing information that distinguishes one spoken word from another. Both neural sequential models performed far better and landed close to each other, suggesting that for this task, preserving timing matters more than the specific sequential architecture used.

See results_summary.txt and the notebook for full details, and the confusion matrix images for error patterns (the LSTM tends to over-predict "nne" as a fallback guess, while the Transformer specifically confuses "sita" and "tisa" with each other).

How to reproduce
Open Formative2_NLP_LSTM_Swahili_Audio_David.ipynb in Google Colab
Mount Google Drive and provide the Swahili Audio Classification dataset (Train.csv, Test.csv, and the unzipped audio files)
Run all cells top to bottom
