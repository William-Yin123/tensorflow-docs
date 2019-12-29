<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.layers.SimpleRNN" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="activation"/>
<meta itemprop="property" content="bias_constraint"/>
<meta itemprop="property" content="bias_initializer"/>
<meta itemprop="property" content="bias_regularizer"/>
<meta itemprop="property" content="dropout"/>
<meta itemprop="property" content="kernel_constraint"/>
<meta itemprop="property" content="kernel_initializer"/>
<meta itemprop="property" content="kernel_regularizer"/>
<meta itemprop="property" content="recurrent_constraint"/>
<meta itemprop="property" content="recurrent_dropout"/>
<meta itemprop="property" content="recurrent_initializer"/>
<meta itemprop="property" content="recurrent_regularizer"/>
<meta itemprop="property" content="states"/>
<meta itemprop="property" content="units"/>
<meta itemprop="property" content="use_bias"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="reset_states"/>
</div>

# tf.keras.layers.SimpleRNN

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/layers/recurrent.py">View source</a>



## Class `SimpleRNN`

Fully-connected RNN where the output is to be fed back to input.

Inherits From: [`RNN`](../../../tf/keras/layers/RNN.md)

<!-- Placeholder for "Used in" -->

See [the Keras RNN API guide](https://www.tensorflow.org/guide/keras/rnn)
for details about the usage of RNN API.

#### Arguments:


* <b>`units`</b>: Positive integer, dimensionality of the output space.
* <b>`activation`</b>: Activation function to use.
  Default: hyperbolic tangent (`tanh`).
  If you pass None, no activation is applied
  (ie. "linear" activation: `a(x) = x`).
* <b>`use_bias`</b>: Boolean, (default `True`), whether the layer uses a bias vector.
* <b>`kernel_initializer`</b>: Initializer for the `kernel` weights matrix,
  used for the linear transformation of the inputs. Default:
  `glorot_uniform`.
* <b>`recurrent_initializer`</b>: Initializer for the `recurrent_kernel`
  weights matrix, used for the linear transformation of the recurrent state.
  Default: `orthogonal`.
* <b>`bias_initializer`</b>: Initializer for the bias vector. Default: `zeros`.
* <b>`kernel_regularizer`</b>: Regularizer function applied to the `kernel` weights
  matrix. Default: `None`.
* <b>`recurrent_regularizer`</b>: Regularizer function applied to the
  `recurrent_kernel` weights matrix. Default: `None`.
* <b>`bias_regularizer`</b>: Regularizer function applied to the bias vector. Default:
  `None`.
* <b>`activity_regularizer`</b>: Regularizer function applied to the output of the
  layer (its "activation"). Default: `None`.
* <b>`kernel_constraint`</b>: Constraint function applied to the `kernel` weights
  matrix. Default: `None`.
* <b>`recurrent_constraint`</b>: Constraint function applied to the `recurrent_kernel`
  weights matrix.  Default: `None`.
* <b>`bias_constraint`</b>: Constraint function applied to the bias vector. Default:
  `None`.
* <b>`dropout`</b>: Float between 0 and 1.
  Fraction of the units to drop for the linear transformation of the inputs.
  Default: 0.
* <b>`recurrent_dropout`</b>: Float between 0 and 1.
  Fraction of the units to drop for the linear transformation of the
  recurrent state. Default: 0.
* <b>`return_sequences`</b>: Boolean. Whether to return the last output
  in the output sequence, or the full sequence. Default: `False`.
* <b>`return_state`</b>: Boolean. Whether to return the last state
  in addition to the output. Default: `False`
* <b>`go_backwards`</b>: Boolean (default False).
  If True, process the input sequence backwards and return the
  reversed sequence.
* <b>`stateful`</b>: Boolean (default False). If True, the last state
  for each sample at index i in a batch will be used as initial
  state for the sample of index i in the following batch.
* <b>`unroll`</b>: Boolean (default False).
  If True, the network will be unrolled,
  else a symbolic loop will be used.
  Unrolling can speed-up a RNN,
  although it tends to be more memory-intensive.
  Unrolling is only suitable for short sequences.


#### Call arguments:


* <b>`inputs`</b>: A 3D tensor, with shape `[batch, timesteps, feature]`.
* <b>`mask`</b>: Binary tensor of shape `[batch, timesteps]` indicating whether
  a given timestep should be masked.
* <b>`training`</b>: Python boolean indicating whether the layer should behave in
  training mode or in inference mode. This argument is passed to the cell
  when calling it. This is only relevant if `dropout` or
  `recurrent_dropout` is used.
* <b>`initial_state`</b>: List of initial state tensors to be passed to the first
  call of the cell.


#### Examples:



```python
inputs = np.random.random([32, 10, 8]).astype(np.float32)
simple_rnn = tf.keras.layers.SimpleRNN(4)

output = simple_rnn(inputs)  # The output has shape `[32, 4]`.

simple_rnn = tf.keras.layers.SimpleRNN(
    4, return_sequences=True, return_state=True)

# whole_sequence_output has shape `[32, 10, 4]`.
# final_state has shape `[32, 4]`.
whole_sequence_output, final_state = simple_rnn(inputs)
```

<h2 id="__init__"><code>__init__</code></h2>

<a target="_blank" href="/code/stable/tensorflow/python/keras/layers/recurrent.py">View source</a>

``` python
__init__(
    units,
    activation='tanh',
    use_bias=True,
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
    dropout=0.0,
    recurrent_dropout=0.0,
    return_sequences=False,
    return_state=False,
    go_backwards=False,
    stateful=False,
    unroll=False,
    **kwargs
)
```






## Properties

<h3 id="activation"><code>activation</code></h3>




<h3 id="bias_constraint"><code>bias_constraint</code></h3>




<h3 id="bias_initializer"><code>bias_initializer</code></h3>




<h3 id="bias_regularizer"><code>bias_regularizer</code></h3>




<h3 id="dropout"><code>dropout</code></h3>




<h3 id="kernel_constraint"><code>kernel_constraint</code></h3>




<h3 id="kernel_initializer"><code>kernel_initializer</code></h3>




<h3 id="kernel_regularizer"><code>kernel_regularizer</code></h3>




<h3 id="recurrent_constraint"><code>recurrent_constraint</code></h3>




<h3 id="recurrent_dropout"><code>recurrent_dropout</code></h3>




<h3 id="recurrent_initializer"><code>recurrent_initializer</code></h3>




<h3 id="recurrent_regularizer"><code>recurrent_regularizer</code></h3>




<h3 id="states"><code>states</code></h3>




<h3 id="units"><code>units</code></h3>




<h3 id="use_bias"><code>use_bias</code></h3>






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





## Compat aliases

* `tf.compat.v1.keras.layers.SimpleRNN`
* `tf.compat.v2.keras.layers.SimpleRNN`

