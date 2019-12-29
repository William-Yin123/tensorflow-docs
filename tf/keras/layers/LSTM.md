<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.layers.LSTM" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.layers.LSTM

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/layers/recurrent_v2.py">View source</a>



## Class `LSTM`

Long Short-Term Memory layer - Hochreiter 1997.

Inherits From: [`LSTM`](../../../tf/compat/v1/keras/layers/LSTM.md)

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
6. Inputs are not masked or strictly right padded.

#### For example:



```
>>> inputs = tf.random.normal([32, 10, 8])
>>> lstm = tf.keras.layers.LSTM(4)
>>> output = lstm(inputs)
>>> print(output.shape)
(32, 4)
>>> lstm = tf.keras.layers.LSTM(4, return_sequences=True, return_state=True)
>>> whole_seq_output, final_memory_state, final_carry_state = lstm(inputs)
>>> print(whole_seq_output.shape)
(32, 10, 4)
>>> print(final_memory_state.shape)
(32, 4)
>>> print(final_carry_state.shape)
(32, 4)
```

#### Arguments:


* <b>`units`</b>: Positive integer, dimensionality of the output space.
* <b>`activation`</b>: Activation function to use.
  Default: hyperbolic tangent (`tanh`). If you pass `None`, no activation
  is applied (ie. "linear" activation: `a(x) = x`).
* <b>`recurrent_activation`</b>: Activation function to use for the recurrent step.
  Default: sigmoid (`sigmoid`). If you pass `None`, no activation is
  applied (ie. "linear" activation: `a(x) = x`).
* <b>`use_bias`</b>: Boolean (default `True`), whether the layer uses a bias vector.
* <b>`kernel_initializer`</b>: Initializer for the `kernel` weights matrix, used for
  the linear transformation of the inputs. Default: `glorot_uniform`.
* <b>`recurrent_initializer`</b>: Initializer for the `recurrent_kernel` weights
  matrix, used for the linear transformation of the recurrent state.
  Default: `orthogonal`.
* <b>`bias_initializer`</b>: Initializer for the bias vector. Default: `zeros`.
* <b>`unit_forget_bias`</b>: Boolean (default `True`). If True, add 1 to the bias of
  the forget gate at initialization. Setting it to true will also force
  `bias_initializer="zeros"`. This is recommended in [Jozefowicz et
      al.](http://www.jmlr.org/proceedings/papers/v37/jozefowicz15.pdf).
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
* <b>`implementation`</b>: Implementation mode, either 1 or 2. Mode 1 will structure
  its operations as a larger number of smaller dot products and additions,
  whereas mode 2 will batch them into fewer, larger operations. These modes
  will have different performance profiles on different hardware and for
  different applications. Default: 2.
* <b>`return_sequences`</b>: Boolean. Whether to return the last output. in the output
  sequence, or the full sequence. Default: `False`.
* <b>`return_state`</b>: Boolean. Whether to return the last state in addition to the
  output. Default: `False`.
* <b>`go_backwards`</b>: Boolean (default `False`). If True, process the input sequence
  backwards and return the reversed sequence.
* <b>`stateful`</b>: Boolean (default `False`). If True, the last state for each sample
  at index i in a batch will be used as initial state for the sample of
  index i in the following batch.
* <b>`time_major`</b>: The shape format of the `inputs` and `outputs` tensors.
  If True, the inputs and outputs will be in shape
  `[timesteps, batch, feature]`, whereas in the False case, it will be
  `[batch, timesteps, feature]`. Using `time_major = True` is a bit more
  efficient because it avoids transposes at the beginning and end of the
  RNN calculation. However, most TensorFlow data is batch-major, so by
  default this function accepts input and emits output in batch-major
  form.
* <b>`unroll`</b>: Boolean (default `False`). If True, the network will be unrolled,
  else a symbolic loop will be used. Unrolling can speed-up a RNN, although
  it tends to be more memory-intensive. Unrolling is only suitable for short
  sequences.


#### Call arguments:


* <b>`inputs`</b>: A 3D tensor with shape `[batch, timesteps, feature]`.
* <b>`mask`</b>: Binary tensor of shape `[batch, timesteps]` indicating whether
  a given timestep should be masked (optional, defaults to `None`).
* <b>`training`</b>: Python boolean indicating whether the layer should behave in
  training mode or in inference mode. This argument is passed to the cell
  when calling it. This is only relevant if `dropout` or
  `recurrent_dropout` is used (optional, defaults to `None`).
* <b>`initial_state`</b>: List of initial state tensors to be passed to the first
  call of the cell (optional, defaults to `None` which causes creation
  of zero-filled initial state tensors).



## Compat aliases

* `tf.compat.v2.keras.layers.LSTM`

