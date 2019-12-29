<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.layers.GRU" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.layers.GRU

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/layers/recurrent_v2.py">View source</a>



## Class `GRU`

Gated Recurrent Unit - Cho et al. 2014.

Inherits From: [`GRU`](../../../tf/compat/v1/keras/layers/GRU.md)

<!-- Placeholder for "Used in" -->

See [the Keras RNN API guide](https://www.tensorflow.org/guide/keras/rnn)
for details about the usage of RNN API.

Based on available runtime hardware and constraints, this layer
will choose different implementations (cuDNN-based or pure-TensorFlow)
to maximize the performance. If a GPU is available and all
the arguments to the layer meet the requirement of the CuDNN kernel
(see below for details), the layer will use a fast cuDNN implementation.

The requirements to use the cuDNN implementation are:

1. `activation` == `tanh`
2. `recurrent_activation` == `sigmoid`
3. `recurrent_dropout` == 0
4. `unroll` is `False`
5. `use_bias` is `True`
6. `reset_after` is `True`
7. Inputs are not masked or strictly right padded.

There are two variants of the GRU implementation. The default one is based on
[v3](https://arxiv.org/abs/1406.1078v3) and has reset gate applied to hidden
state before matrix multiplication. The other one is based on
[original](https://arxiv.org/abs/1406.1078v1) and has the order reversed.

The second variant is compatible with CuDNNGRU (GPU-only) and allows
inference on CPU. Thus it has separate biases for `kernel` and
`recurrent_kernel`. To use this variant, set `'reset_after'=True` and
`recurrent_activation='sigmoid'`.

#### For example:



```
>>> inputs = tf.random.normal([32, 10, 8])
>>> gru = tf.keras.layers.GRU(4)
>>> output = gru(inputs)
>>> print(output.shape)
(32, 4)
>>> gru = tf.keras.layers.GRU(4, return_sequences=True, return_state=True)
>>> whole_sequence_output, final_state = gru(inputs)
>>> print(whole_sequence_output.shape)
(32, 10, 4)
>>> print(final_state.shape)
(32, 4)
```

#### Arguments:


* <b>`units`</b>: Positive integer, dimensionality of the output space.
* <b>`activation`</b>: Activation function to use.
  Default: hyperbolic tangent (`tanh`).
  If you pass `None`, no activation is applied
  (ie. "linear" activation: `a(x) = x`).
* <b>`recurrent_activation`</b>: Activation function to use
  for the recurrent step.
  Default: sigmoid (`sigmoid`).
  If you pass `None`, no activation is applied
  (ie. "linear" activation: `a(x) = x`).
* <b>`use_bias`</b>: Boolean, (default `True`), whether the layer uses a bias vector.
* <b>`kernel_initializer`</b>: Initializer for the `kernel` weights matrix,
  used for the linear transformation of the inputs. Default:
  `glorot_uniform`.
* <b>`recurrent_initializer`</b>: Initializer for the `recurrent_kernel`
   weights matrix, used for the linear transformation of the recurrent
   state. Default: `orthogonal`.
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
  weights matrix. Default: `None`.
* <b>`bias_constraint`</b>: Constraint function applied to the bias vector. Default:
  `None`.
* <b>`dropout`</b>: Float between 0 and 1. Fraction of the units to drop for the linear
  transformation of the inputs. Default: 0.
* <b>`recurrent_dropout`</b>: Float between 0 and 1. Fraction of the units to drop for
  the linear transformation of the recurrent state. Default: 0.
* <b>`implementation`</b>: Implementation mode, either 1 or 2.
  Mode 1 will structure its operations as a larger number of
  smaller dot products and additions, whereas mode 2 will
  batch them into fewer, larger operations. These modes will
  have different performance profiles on different hardware and
  for different applications. Default: 2.
* <b>`return_sequences`</b>: Boolean. Whether to return the last output
  in the output sequence, or the full sequence. Default: `False`.
* <b>`return_state`</b>: Boolean. Whether to return the last state in addition to the
  output. Default: `False`.
* <b>`go_backwards`</b>: Boolean (default `False`).
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
* <b>`time_major`</b>: The shape format of the `inputs` and `outputs` tensors.
  If True, the inputs and outputs will be in shape
  `[timesteps, batch, feature]`, whereas in the False case, it will be
  `[batch, timesteps, feature]`. Using `time_major = True` is a bit more
  efficient because it avoids transposes at the beginning and end of the
  RNN calculation. However, most TensorFlow data is batch-major, so by
  default this function accepts input and emits output in batch-major
  form.
* <b>`reset_after`</b>: GRU convention (whether to apply reset gate after or
  before matrix multiplication). False = "before",
  True = "after" (default and CuDNN compatible).


#### Call arguments:


* <b>`inputs`</b>: A 3D tensor, with shape `[batch, timesteps, feature]`.
* <b>`mask`</b>: Binary tensor of shape `[samples, timesteps]` indicating whether
  a given timestep should be masked  (optional, defaults to `None`).
* <b>`training`</b>: Python boolean indicating whether the layer should behave in
  training mode or in inference mode. This argument is passed to the cell
  when calling it. This is only relevant if `dropout` or
  `recurrent_dropout` is used  (optional, defaults to `None`).
* <b>`initial_state`</b>: List of initial state tensors to be passed to the first
  call of the cell  (optional, defaults to `None` which causes creation
  of zero-filled initial state tensors).



## Compat aliases

* `tf.compat.v2.keras.layers.GRU`

