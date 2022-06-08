# Activation Functions

## Linear vs. Non-Linerity
Add non-linear transformation layer
Usually, neural networks have all layers non-linear for the first n-1 layers, then have the final layer transformation, bilinear for regression or sigmoid or softmax for classification

## Activiation functions: Pitfalls to avoid in Backpropagation
### 1. Gradients can vanish

1. Insight: 

    Each additional layer can successively reduce signal vs. noise
Gradients get smaller and smaller, weights no longer updated, training halt

2. Solution:

    Using ReLu instead of sigmoid/tanh can help

### 2. Gradients can explode

1. Insight

    Learning rates are important here. For sequence models with long sequence models, the graidents get very large.

2. Solutions

    Weight regularization, smaller batch sizes, batch normalization (useful knob) can help; 

    Gradient clipping


### 3. ReLu layers can die Dead layers

1. Insight

    Monitor fraction of zero weights in TensorBoard

2. Solution

    Lower your learning rate; use leaky or parametic ReLus

# Neural Networks with Keras Sequential API

Keras is built-in to TF 2.x

1. Define model object

```python
%tensorflow_version 2.x
import tensorflow as tf
from tensorflow import keras
(x_._train, y_._train), (x_test, y_test) = keras.datasets.mnist.load_date()

# Define your model
model = tf.keras.models.Sequential([
    tf.keras.layers.Flatten(),
    tf.keras.layers.Dense(128, activation = 'relu'),
    tf.keras.layers.Dense(128, activation = 'relu'),
    tf.keras.layers.Dense(128, activation = 'relu'),
    tf.keras.layers.Dense(10, activation = 'softmax')
])

```

2. Compile a Keras model

* addtional parameters are passed to the method
* These paramters define the optimizer that should be used, the loss function, the evalution metrics, the loss weight, the sample weight mode, the weighted metrics

```python
def rmse(y_true, y_pred):
    return tf.sqrt(tf.reduce_mean(tf.square(y_pred - y_true)))

model.compile(optimizer = "adam", loss = "mse", metrics = [rmse, "mse"])
```

3. Training a Keras model by .fit() method
```python
from tensorflow.keras.callbacks import TensorBoard

steps_per_epoch = NUM_TRAIN_EXAMPLES // (TRAIN_BATCH_SIZE * NUM_EVALS)

history = model.fit(
    x = trainds,
    steps_per_epoch = steps_per_epoch,
    epochs = NUM_EVALS,
    validation_data = evalds,
    callbacks = [TensorBoard(LOGDIR)]
)
model.evaluate(x_test, y_test)
```

4. Once trained, model can be used for prediction

predictions = model.predict(input_samples, steps = 1)

5. Save Model
```python
OUTPUT_DIR = "./export/savemodel"
shuil.rmtree(OUTPUT_DIR, ignore_errors = Ture)

EXPORT_PATH = os.path.join(OUTPUT_DIR, datetime.datetime.now().strftime("%Y%m%d%H%M%S"))

tf.saved_model.save(model, EXPORT_PATH)
```

push model to AI platformls


# Keras Functional API

Wide and deep NNs

Jointly training a wide linear model for memorization and alongside a DNN for generalization

## Creating a Wide and Deep Model in Keras
1. Prepare input feature columns
```python
inputs = {colname : layers.Input(name = colname, shape = (), dtype = 'float32') for colname in INPUT_COLS}
```

2. Create Deep columns


3. Create the deep parts of model


4. Create wide columns

5. Combine outputs

6. finalize model

## Strength and weakness of Functional API
1. Strength
* less verbose than using Keras. Model subclasses
* validates your model while defining it
* model is plottable and inspectable
* model can be serialized and cloned


# Regularization
## Basics
Loss curve of training and testing dataset vs. Training iterations

reduce model complexity


Minimize: Loss ( data/model) + complexity(model)


# Regularization

* Early Stopping
*  Parameter Norm Penalties (L1 & L2, Max-norm regularization)
* Dropout layers : dropout randomly dropping out unit activations in a network for a signle gradient step -> Ensemble model
* Dataset augmentation
* Noise Robustness
* Sparse Representations
