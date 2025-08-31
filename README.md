# Phased Spatial-Temporal Targeted Networks Based on Transformer and Data Augmentation for Cellular Traffic Prediction

## Basic Information

This repository contains the PyTorch implementation of RLSASTTE proposed in the paper "Phased Spatial-Temporal Targeted Networks Based on Transformer and Data Augmentation for Cellular Traffic Prediction."

## Environment Setup
The main package versions used in RLSASTTE are as follows:
- argparse==1.4.0
- einops==0.7.0
- matplotlib==3.5.1
- minepy==1.2.6
- networkx==3.2.1
- numpy==1.26.2
- pandas==1.2.4
- python==3.9.17
- scikit-learn==1.3.0
- scipy==1.11.4
- torch==1.12.0
- tqdm==4.66.1

## Running Instructions
```
python run.py
```
or
```
python run.py --data "Call" --in_dim 1 --is_training 1 
```
To run the code on different datasets, the corresponding parameters need to be modified, including ```--data``` and ```--in_dim```. By default, the code is set to use the Call service from the Milan Telecom Dataset. Additionally, the training or testing mode can be switched by modifying the ```--is_training``` parameter.

## Code Structure
```
RLSASTTE
│        data_provider        
│           │data_factory.py
│           │data_loader.py
│
│        exp
│           │exp_basic.py
│           │exp_main.py
│ 
│        layers
│           │STAM.py
│           │Trans_encoder.py
│           │Embed.py
│           │Norm.py
│
│        models
│           │Main.py
│           │PDSTAformer.py
│
│        utils
│           │tools.py
│           │metrics.py
│           │masking.py
│           │timefeatures.py
│
└─ ─ ─ ─ ─ run.py
```

## Main Parameters
The parameters of RLSASTTE and their corresponding meanings are as follows:

```
seq_len             Input length
pred_len            Prediction length
label_len           Start token length
d_model             Feature dimension
n_heads             Number of heads
moving_avg          Window size of moving average
patience            Early stopping patience
loss                Loss function
learning_rate       Learning rate
itr                 Number of experiments
sid_10              Spatial impact degree
data                Dataset type
```

## Dataset Access
We appreciate the availability of these public datasets, which can be accessed through the following sources.

- The Milan Telecom Dataset is available at https://www.nature.com/articles/sdata201555.
- The Hangzhou Base Station Dataset is available at https://www.kaggle.com/code/guiyihan/base-station-traffic-eda-hangzhou.
- The 5G Traffic Dataset is available at https://ieee-dataport.org/documents/5g-traffic-datasets.
