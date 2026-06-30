# Sarcasm Detection

A supervised text-classification project on the **Reddit SARC** (Self-Annotated Reddit Corpus) sarcasm dataset.

> Team project (University of Victoria, SENG 474). Co-authored, four contributors.

## The arc

| Stage | Model | Test accuracy |
|-------|-------|:-------------:|
| Baseline | Logistic Regression | 0.70 |
| Baseline | Linear SVM (tuned `C=0.1`) | 0.70 |
| Baseline | Random Forest | 0.68 |
| Neural net | Feed-forward NN (plain) | 0.66, overfits |
| + dropout | NN + dropout | 0.69 |
| + early stopping | NN + dropout + early stopping | 0.71 |
| + regularization | NN + L2 regularization | 0.73 |
| Beyond bag-of-words | TF-IDF + SBERT embeddings | 0.76 |

## The overfitting thread

The plain neural net actually underperforms the linear baselines because it overfits. The
project then walks through the standard toolkit (dropout, early stopping, L2 regularization),
using validation curves to show each one narrowing the train/validation gap. This is the
empirical companion to my [model-theory report](https://github.com/tstoj623/model-theory),
which asks the same question from the theory side: given the data, when does a model overfit,
and what controls its capacity?

## Files

- [`sarcasm_detection.ipynb`](sarcasm_detection.ipynb): the full project, baselines through
  SBERT (developed in Google Colab, output cells preserved).
- [`report.pdf`](report.pdf): written report.
