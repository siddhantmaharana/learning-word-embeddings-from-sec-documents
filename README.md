Domestic US companies submit annual reports on Forms 10-K,8-K etc.These forms provide firms with a unique opportunity to inform investors on an ongoing basis, and for firm's executives to express their expectations for the future, as well as their interpretations of the past. 

### Data extraction and preparation

1. SEC Documents from 2013 -2014 -SEC Documents are a set of financial documents provided as a html file. Due  to  computational  complexities  documents  from  2013 -2014  amounting  to  a  total  of  220k documents (50Gb) were considered.
2. Ticker and Employee ID Dataset -Used to match the CIK from the SEC documents to get the ticker information of a company 
3. Sentiment Labels Dataset -Dataset contains the Stock Sentiment labels for various companies and dates. 

### Methodology

The project has two objectives.
1. Sentiment Analysis -Building a classifier to predict the sentiments of the stocks.
2. Comparing  word Embeddings -Compare  Word  Embeddings  from  the  classification  models  and  Word2Vec model

### Sentiment Analysis

The aim of the sectionis to introduce all the models used for predicting Stock Sentiments.

#### 1. LSTM model

The architecture using LSTM layers was modeled. The  embedding  layer is  trained  for  10,000  words  and  each  word  is  a  200dimensionalvector. 20,000 words from the dictionary are used for training. The LSTM layer consists of 256 layers. The LSTM layer is finally connected to 2 dense layers. The final layer is a softmax layer to classify the sentiment.

#### 2. CNN model

The   second   architecture   is based   on   Convolution. Convolutions   are   typically   associated   with   image classifications. The convolution filters are as wide as the word vectors i.e. 200 in this case. When the convolution filters are generated they create high level features from the text corpus which were then used for sentiment analysis.

### Comparing Word Embeddings

The second part of this project compares the embeddings produced from the classifiers trained above with the word2vec models trained from these corpus.

#### Learning embeddings with the embedded layer

The simplest way to associate a dense vector to a word would be to pick the vector at random. Following which the weights learnt from the model can be used as the vector representation of the vocabulary.The earlier task of building a network for analyzing sentiment used a feed forward network and used a vocabulary of 20000 words as an input layer. The successive embedding layer with a low dimension space of 200 was then saved along with the vocabulary dictionary for comparison purposes.

Using Word2vecIn  their  first  paper,  Mikolov  et  al.  proposed  two  architectures  for  learning  word  embeddings  that  are computationally  less  expensive  than  previous  models.  In  this  paper,  they  improved  upon  these  models  by employing additional strategies to enhance speed and accuracy. This architecture was successfull because of the training strategies used. 
Word2vec expects a sequence of sentences as its input and the input files worth 17,000 documents were passed after cleaning and preprocessing to the model. Using a window size of 10 words, skipgram method was used  to  train  the  model  with  a  similar  vocabulary  of  20,000  words  such  that  the  final  dimension  of  the  dense vector is 200. Negative sampling is used as the objective function to compute the weights and biases.

## Results of the analysis

1. For the Sentiment Analysis, the neural networks were trained for 10 epoch till a satisfactory accuracy is reached
2. An  intrinsic evaluation was being carried out to evaluate both the embeddings. To achieve this, cosine similarity was computed against a bunch of sample words and manually evaluated to determine the performance of the word embeddings. But the embeddings produced out of training via word2vec produced superior results in comparison to the ones trained in the network earlier.




