RateTransformer
===============

A tool for performing cyclic ratings of power transformers as per Australian Standard 60076.

## Installation
Run:
```
python setup.py build
python setup.py install
```

## Usage
The following will return the peak load rating:
```
from ratetransformer import Transformer
tx = Transformer(HeatRunData, ThermalChar)
tx.perform_rating(AmbWHS, AmbAgeing, LoadShape, Limits)
print(tx.MaxLoad)
```

## Process Overview
Start the model with initial oil temperature of zero.
![Screenshot](/docs/curve_0.png?raw=true "Transformer Model")

Iterate until oil temperature stabilises for given daily load shape.
![Screenshot](/docs/curve_1.png?raw=true "Transformer Model")

Increment load magnitude until one of the passed limits are breached.
(In this case the winding hotspot temperature has reached 120 degrees)
![Screenshot](/docs/curve_2.png?raw=true "Transformer Model")

