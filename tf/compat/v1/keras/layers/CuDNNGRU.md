<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.keras.layers.CuDNNGRU" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="cell"/>
<meta itemprop="property" content="states"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="reset_states"/>
</div>

# tf.compat.v1.keras.layers.CuDNNGRU

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/layers/cudnn_recurrent.py">View source</a>



## Class `CuDNNGRU`

Fast GRU implementation backed by cuDNN.



<!-- Placeholder for "Used in" -->

More information about cuDNN can be found on the [NVIDIA
developer website](https://developer.nvidia.com/cudnn).
Can only be run on GPU.

#### Arguments:


* <b>`units`</b>: Positive integer, dimensionality of the output space.
* <b>`kernel_initializer`</b>: Initializer for the `kernel` weights matrix, used for
  the linear transformation of the inputs.
* <b>`recurrent_initializer`</b>: Initializer for the `recurrent_kernel` weights
  matrix, used for the linear transformation of the recurrent state.
* <b>`bias_initializer`</b>: Initializer for the bias vector.
* <b>`kernel_regularizer`</b>: Regularizer function applied to the `kernel` weights
  matrix.
* <b>`recurrent_regularizer`</b>: Regularizer function applied to the
  `recurrent_kernel` weights matrix.
* <b>`bias_regularizer`</b>: Regularizer function applied to the bias vector.
* <b>`activity_regularizer`</b>: Regularizer function applied to the output of the
  layer (its "activation").
* <b>`kernel_constraint`</b>: Constraint function applied to the `kernel` weights
  matrix.
* <b>`recurrent_constraint`</b>: Constraint function applied to the
  `recurrent_kernel` weights matrix.
* <b>`bias_constraint`</b>: Constraint function applied to the bias vector.
* <b>`return_sequences`</b>: Boolean. Whether to return the last output in the output
  sequence, or the full sequence.
* <b>`return_state`</b>: Boolean. Whether to return the last state in addition to the
  output.
* <b>`go_backwards`</b>: Boolean (default False). If True, process the input sequence
  backwards and return the reversed sequence.
* <b>`stateful`</b>: Boolean (default False). If True, the last state for each sample
  at index i in a batch will be used as initial state for the sample of
  index i in the following batch.

<h2 id="__init__"><code>__init__</code></h2>

<a target="_blank" href="/code/stable/tensorflow/python/keras/layers/cudnn_recurrent.py">View source</a>

``` python
__init__(
    units,
    kernel_initializer='glorot_uniform',
    recurrent_initializer='orthogonal',
    bias_initializer='zeros',
    kernel_regularizer=None,
    recurrent_regularizer=None,
    bias_regularizer=None,
    activity_regularizer=None,
    kernel_constraint=None,
    recurrent_constraint=None,
    bias_constraint=None,
    return_sequences=False,
    return_state=False,
    go_backwards=False,
    stateful=False,
    **kwargs
)
```






## Properties

<h3 id="cell"><code>cell</code></h3>




<h3 id="states"><code>states</code></h3>






## Methods

<h3 id="reset_states"><code>reset_states</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/keras/layers/recurrent.py">View source</a>

``` python
reset_states(states=None)
```

Reset the recorded states for the stateful RNN layer.

Can only be used when RNN layer is constructed with `stateful` = `True`.
Args:
  states: Numpy arrays that contains the value for the initial state, which
    will be feed to cell at the first time step. When the value is None,
    zero filled numpy array will be created based on the cell state size.

#### Raises:


* <b>`AttributeError`</b>: When the RNN layer is not stateful.
* <b>`ValueError`</b>: When the batch size of the RNN layer is unknown.
* <b>`ValueError`</b>: When the input numpy array is not compatible with the RNN
  layer state, either size wise or dtype wise.





