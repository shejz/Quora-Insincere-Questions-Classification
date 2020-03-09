![Quora Insincere Questions Classification](https://github.com/shejz/Quora-Insincere-Questions-Classification/blob/master/images/QIQC.jpg)

### **Metric**
The metric was the **F1-Score**, as the problem was an unbalanced binary classification. 


### Text Preprocessing

### Statistical features for sentences
- the number of characters
- the number of upper characters
- the rate of upper characters
- the number of words
- the number of unique words


### Embeddings
I used glove and paragram pretrained word embeddings. The mean of the two is used as the final embedding matrix.
- [glove.840B.300d](https://nlp.stanford.edu/projects/glove/)
- [paragram_300_sl999](https://cogcomp.org/page/resource_view/106)

### Stratified K Fold 
- Use Stratified K Fold to improve results.

### Model Architecture
- Binary LSTM with an attention layer and an additional fully connected layer. 
- Added extra features taken from a winning kernel of the toxic comments competition. 
- Also using CLR and a capsule Layer. Blended together in concatentation.

