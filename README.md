# widis-lstm-tools v0.1
Various Tools for working with Long Short-Term Memory (LSTM) networks and sequences in [Pytorch](https://pytorch.org/),
aimed at getting your LSTM networks under control and providing a flexible template for your LSTM-needs.

LSTM paper (not earliest): https://www.mitpressjournals.org/doi/abs/10.1162/neco.1997.9.8.1735

## Quickstart
Include the path to the widis_lstm_tools folder in you PYTHONPATH variable.

Run the simple example via

```python3 widis_lstm_tools/examples/basic/main.py config.json```

Run the more advanced example via

```python3 widis_lstm_tools/examples/model_selection/main.py config.json```

## Includes
- Flexible [LSTM implementation](widis_lstm_tools/nn.py/LSTMLayer) including
  - Easy access to individual forward and recurrent LSTM inlets and biases, with option to cut/modify individual inlets (see e.g. https://arxiv.org/abs/1503.04069 for useful modifications)
  - Plotting function for LSTM internal states
  - Support for Ticker/Tinker-Steps at the end of the sequence (https://arxiv.org/abs/1603.08983)
- Preprocessing tools
  - [Padding of different sequence lengths](widis_lstm_tools/preprocessing.py/PadToEqualLengths)
  - [Encoding for nicely feeding float or integer numbers as inputs to the LSTM](widis_lstm_tools/preprocessing.py/TriangularValueEncoding)
- Other utilities
  - [Printing to log-file and console](widis_lstm_tools/utils/collection.py/TeePrint)
  - [Splitting PyTorch datasets](widis_lstm_tools/preprocessing.py/random_dataset_split), e.g. into training-, validation-, testset
  - [One-Hot encoding of n-dimensional arrays](widis_lstm_tools/preprocessing.py/inds_to_one_hot)
  - [SaverLoader](widis_lstm_tools/collection.py/SaverLoader) class for saving/loading the most recent models to files or RAM objects
- Documented examples
  - [Basic LSTM example](widis_lstm_tools/examples/basic/main.py) with variable sequence lenghts
  - [Advanced LSTM example](widis_lstm_tools/examples/model_selection/main.py) with input encoding and model selection
 

## Requirements
- [Python3.6](https://www.python.org/) or higher
- Python packages:
   - [Pytorch](https://pytorch.org/) (tested with version 1.0.1)
   - [numpy](https://www.numpy.org/) (tested with version 1.16.2)
   - [matplotlib](https://matplotlib.org/) (tested with version 3.0.3)

