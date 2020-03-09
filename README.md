![Quora Insincere Questions Classification](https://github.com/shejz/Quora-Insincere-Questions-Classification/blob/master/images/QIQC.jpg)

This competition is sponsored by Quora. The objective is to predict whether a question asked on Quora is sincere or not. This is a kernels only competition with contraint of two-hour runtime.

An insincere question is defined as a question intended to make a statement rather than look for helpful answers. Some characteristics that can signify that a question is insincere:

- has a non-neutral tone
- is disparaging or inflammatory
- isn't grounded in reality
- uses sexual content

Submissions are evaluated on `F1 score` between the predicted and the observed targets. As the problem was an unbalanced binary classification. 

### Text Preprocessing
- Cleaning special characters, numbers and misspelling.

### Statistical features for sentences
- the number of characters
- the number of upper characters
- the rate of upper characters
- the number of words
- the number of unique words

### Meta Embeddings
I used glove and paragram pretrained word embeddings. The mean of the two is used as the final embedding matrix.
- [glove.840B.300d](https://nlp.stanford.edu/projects/glove/)
- [paragram_300_sl999](https://cogcomp.org/page/resource_view/106)

### Stratified K Fold 
- Use Stratified K Fold to improve results.

### Model Architecture
- Binary LSTM with an attention layer and an additional fully connected layer. 
- Added extra features taken from a winning kernel of the toxic comments competition. 
- Also using CLR and a capsule Layer. Blended together in concatentation.

### LeaderBoard Ranking
|Model             |Public score|Private score|Final rank| 
|------------------|------------|-------------|----------|
| NN using Pytorch |0.98122     |0.98206      | 586/4037 [Top 15%](https://www.kaggle.com/shielaj/competitions)|

