# GammaFiltersHearingAid
Gamma filter bank for audio analysis and synthesis

Todo: Gamma filter bank. Components:

makeParameterStructures:
 Construct the C++ classes needed to define the filter bank
 from a few configuration parameters, such as: smampling rate,
 number of channels, number of filterbanks, parameters that
 describe the bandwidths as function of frequency.

signalFilters: Forward and backwards filters that convert
a sampled audio signal to filter bank output signals, and
an inverse filter that synthesizes an audio signal from
band-limited signals. 

 forward filter for analysis:
  C++ code that receives as input float (or double) array
  representing a sample audio signal and generates
  the samples of the filter bank output as a matrix. 

 backward filter for synthesis:
  C++ code that receives as input a matrix of bandlimited
  signals and synthesizes an audio signal using the inverted
  transfer functions used for analysis.

The analysis and synthesis filters are build as a dynamic library
to be called by C++ and later from Python.

Interface with Python. To be build: I want the main processing
be done with Python, leaving number crunching to calls to
the C++ library.

Further outlook.

Build recurrent networks for processing the filterbank outputs.
These are trained to predict the next sample of filterbank outputs
from the previous ones, using a recurrent network with memory,
most likely a gated recurrent unit (GRU). The system is trained
with clean speech signals first so it learns mainly the dynamics
of speech signals. Later the system is improved by learning
to reconstruct speech signals from corrupted speech signals, both
with noise and reverberation.




