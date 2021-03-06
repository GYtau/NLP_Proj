# NLP_Proj
**Students**: Irina Aleshin 328814470 Gilad Yekuel 206035222 Yuval Ziv 207900283

In this project, we implemented LSTM model and tested Word2Vec and Fastext embedding models.
The main goal of this project was a classification problem- classify comments as positive or negative.

Before we trained the embedding models we prepared our data to fit as an input for embedding and as an input to the LSTM model.
The data we got was separeted in 2 directories - pos and neg (positive comments and negative accordingly). Each directory had txt files with comments in it.
We cleaned the words in the comments from all the symbols that are not letters, checked that the words are more than one letter, lowercased and are not part of stop words (from nltk library). Then we made a list for each "clean" file (comment). The positive comments labeled as 1, and negative as 0. 
Also, we had to make a padding for the comments (that later on we converted to tensors) so they will be the same dimension for the model.

Our project included 2 embedding models: Word2vec, Fasttext.
We did 30 epochs for each embedding model. 
In addition, we created the LSTM cell and a model with some LSTM cells. 
For the hyperparameters testing we decided to change the learning rate and the architecture
of the model. We chose 2 numbers of layers (10 and 15) and  2 different learning rates for each
model. However, due to low resources, we couldn't run the model on all the data and all the combinations. 
Hence, We decided to run those combinations (for each model):
1. Learning rates- 0.01, 0.05
2. Number of layers- 10,15
Combinations:
1. lr=0.05, 15 layers
2. lr=0.01, 10 layers

because of higher number of weights in the bigger model, we wanted to increase the learning rate, 
so the model could improve faster. In addition, the number of epochs was 30. 
Of course, if we would have more GPU we would run more epochs. 
Total combinations we ran: 4 (2 options for each model)

**Discussion:**
We can see that there is a significant difference between the models with different learning rate and hidden size.
The lower the learning rate the the lower the smaller the number of the layers is, the better.
In addition, It is well clarified in the first loss graph of the train sets.
Furthermore, The models are not stable, and if we would have more time and GPU power, we would have ran that with more epochs and we would check which hyper parameters are the best to adjust: 
the learning rate, the number of layers in the model etc.
Moreover, the auc results are almost the same for the all 4 models:
not stable and there is a minor difference (less than 5%) between each other, but the loss difference is much more significant. 
Due to low computing power and not enough time, we did combination of 2 hyper parameters adjustments and ran it. 
In conclusion, the result are not better than a random model (around 50% auc)
