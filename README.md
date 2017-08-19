# anomalous_drawings
Flask app that detects anomalous drawings: https://anomaly-bowtie.herokuapp.com

This app uses a simple autoencoder to perform anomaly detection on bowtie drawings.
You can draw a bowtie (or anything) in the left canvas and the right canvas will
show you the autoencoder's reconstruction (784-32-782 model --> 28x28 image).
If your drawing is not a standard-looking bowtie (anomaly), the reconstruction cost
number will turn red. A good reconstruction (on the right canvas) will give a
low cost (not anomaly) while a bad reconstruction will give a high cost (anomaly).
The anomaly threshold is set at 0.07: error > 0.07 --> anomaly.

The flask app resides in the app _submodule_ and is hosted on heroku.

Data: The bowtie drawings used to train the autoencoder are a subset of
Google's Quick, Draw! [dataset][data].

Notebook that explains how anomaly detection can be performed via an autoencoder:
[Bowtie Drawing Autoencoder]()

Notebooks about the autoencoder's implementation can be found in my
ML algorithms [repository][other repo]. model.py and utils.py are based on this
repository's notebooks.

[data]: https://github.com/googlecreativelab/quickdraw-dataset
[other repo]: https://github.com/chen10an/ml_algos_python/tree/master/autoencoder
