# Activation Functions

## Linear vs. Non-Linerity
Add non-linear transformation layer
Usually, neural networks have all layers non-linear for the first n-1 layers, then have the final layer transformation, bilinear for regression or sigmoid or softmax for classification

## Activiation functions: Pitfalls to avoid in Backpropagation
### Gradients can vanish

1. Insight: 

    Each additional layer can successively reduce signal vs. noise
Gradients get smaller and smaller, weights no longer updated, training halt

2. Solution:

    Using ReLu instead of sigmoid/tanh can help

### Gradients can explode

1. Insight

Learning rates are important here. For sequence models with long sequence models, the graidents get very large.

Solutions

Weight regularization, smaller batch sizes, batch normalization (useful knob) can help; 

Gradient clipping



3. ReLu layers can die Dead layers

Insight

Monitor fraction of zero weights in TensorBoard

Solution

Lower your learning rate; use leaky or parametic ReLus