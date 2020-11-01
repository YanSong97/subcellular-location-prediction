# subcellular-location-prediction

## coursework description: [LINK](http://www0.cs.ucl.ac.uk/staff/D.Jones/coursework/)
The task is to develop a simple method for classifying eukaryotic protein sequences into the 4 categories:
* Cytosolic - i.e. within the cell itself, but not inside any organelles

* Secreted - proteins which are transported out of a cell

* Nuclear - proteins found/used within the cell's nucleus

* Mitochondrial - proteins transported to the cell's mitochondria

## Methods:

In the report, we implement four different deep learning models (determinsitic version):

* Long Short-Term Memory (LSTM)
* Bi-direction LSTM
* LSTM with attention network
* CNN + LSTM

Evaluation has been made on the given dataset as well as the prediction on unlabelled sequences. Particularly, the implementation of attention network enable the visualisation of featured segmentation (signal peptide) in a protein sequence.


## Some thoughts:
The prediction on testing sequences tends to be over-confident, which might not be trust-worthy. One very promising direction to provide better model interpretation and robustness is by injecting noise into the model. Previously the predictive uncertainty relies only on the softmax layer generating probability score. *Bayesian neural network* is a valid example to take a first step in the field.



