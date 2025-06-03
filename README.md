# ESCI_Ranking

## Dataset
ESCI Dataset: a large dataset of difficult search queries, released with the aim of fostering research in the area of semantic matching of queries and products. For each query, the dataset provides a list of up to 40 potentially relevant results, together with ESCI relevance judgements (Exact, Substitute, Complement, Irrelevant) indicating the relevance of the product to the query. This repository focuses on the english sample points of the dataset.

Note: For comparison of the models on the NDCG@10 Criterion - 
- ```Exact - 1.0```
- ```Substitute - 0.1```
- ```Complimentary - 0.01```
- ```Irrelevant - 0.0```

For compute: Took a subset of the ESCI Dataset of 50,000 sample points for training and 10,000 sample points for for evaluating. 

## Introduction
The purpose of this task is to explore more on the topic of multitask learning in the scope of E-Commerce. Product recommendation and Relevance calculation were the task set for evaluation. 
For each query, there are a number of product recommendations along with their labels. 

### Model Architecture
Explored bi-encoders and cross-encoders for this task. Bi-Encoders, are fast and less computationally intensive but Cross-Enocders are more accurate. 

### Loss Function
Loss function for this project was chosen to be a weighted average of RCR Loss and BCE Loss. RCR Loss itself is a weighted average of MSE Loss and ListCE Loss.

```Loss = (1 - x) * RCR + x * BCE```

```Loss = (1 - x) * alpha * MSE Loss + (1 - x) * (1 - alpha) ListCELoss + x * BCE Loss```

### Evaluation
The initial dataset achieved a ```NDCG@10 = 0.9196```.

The Refined Approach achieved a ```NDCG@10 = 0.9006```
