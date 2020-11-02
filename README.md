# subcellular-location-prediction
This is a mini-project of UCL course COMP0082 Bioinformatics.

## report link: [LINK](https://github.com/YanSong97/subcellular-location-prediction/blob/master/report.pdf) , code link: [LINK](https://github.com/YanSong97/subcellular-location-prediction/blob/master/subcellular_location_prediction.ipynb)

## coursework description: [LINK](http://www0.cs.ucl.ac.uk/staff/D.Jones/coursework/)
The task is to develop a simple method for classifying eukaryotic protein sequences in the given dataset into the 4 categories:
* Cytosolic - i.e. within the cell itself, but not inside any organelles

* Secreted - proteins which are transported out of a cell

* Nuclear - proteins found/used within the cell's nucleus

* Mitochondrial - proteins transported to the cell's mitochondria 

## Methods:

In the report, we implement various deep leanring models:

* Long Short-Term Memory (LSTM): LSTM is a powerful and widly-used deep learning architecture for sequence modelling. As for the protein sequence, we also utilised the embedding layer to convert the amino acid labels into numeric representation and a Multi-layer Perceptron (MLP) decoder layer to generate the probability of each category. In the experiment we found that normal LSTM where we use the hidden state at the final time step to generate probability fails to give good results, therefore we try making use of all hidden states by adding a max pooling layer which takes all hidden states into input and outputs a single hidden representation for prediction. The schemetic model plot is shown below:


<img src="https://github.com/YanSong97/subcellular-location-prediction/blob/master/LSTM%20with%20pooling%20.png" width="500" height="350" />

* LSTM with attention: inspired by many of NLP papers, we also implement an attention network. Different from a LSTM with max pooling layer, attention network takes a weighted average of all hidden states which is analogous to a average pooling layer. The schemetic model plot is shown as:


<img src="https://github.com/YanSong97/subcellular-location-prediction/blob/master/LSTM-attention.png" width="250" height="350" />


* CNN-LSTM: Applying convolutional filter has also been explored in NLP field, here we use multiple CNN filter with different size to scan over the embedding representation and feed the results into a RNN for label prediction. The shemetic model plot is shown as:

<img src="https://github.com/YanSong97/subcellular-location-prediction/blob/master/CNN-LSTM.png" width="250" height="350" />


Evaluation has been made on the given dataset as well as the prediction on unlabelled sequences. Particularly, the implementation of attention network enable the visualisation of featured segmentation (signal peptide) in a protein sequence.


## Some thoughts:
The prediction on testing sequences tends to be over-confident, which might not be trust-worthy. One very promising direction to provide better model interpretation and robustness is by injecting noise into the model. Previously the predictive uncertainty relies only on the softmax layer generating probability score. *Bayesian neural network* can be the first step to try in the field.



