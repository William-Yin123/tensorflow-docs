<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.layers.GRUCell" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.layers.GRUCell

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/layers/recurrent_v2.py">View source</a>



## Class `GRUCell`

Cell class for the GRU layer.

Inherits From: [`GRUCell`](../../../tf/compat/v1/keras/layers/GRUCell.md)

<!-- Placeholder for "Used in" -->

See [the Keras RNN API guide](https://www.tensorflow.org/guide/keras/rnn)
for details about the usage of RNN API.

This class processes one step within the whole time sequence input, whereas
`tf.keras.layer.GRU` processes the whole sequence.

#### For example:



```
>>> inputs = tf.random.normal([32, 10, 8])
>>> rnn = tf.keras.layers.RNN(tf.keras.layers.GRUCell(4))
>>> output = rnn(inputs)
>>> print(output.shape)
(32, 4)
>>> rnn = tf.keras.layers.RNN(
...    tf.keras.layers.GRUCell(4),
...    return_sequences=True,
...    return_state=True)
>>> whole_sequence_output, final_state = rnn(inputs)
>>> print(whole_sequence_output.shape)
(32, 10, 4)
>>> print(final_state.shape)
(32, 4)
```

#### Arguments:


* <b>`units`</b>: Positive integer, dimensionality of the output space.
* <b>`activation`</b>: Activation function to use. Default: hyperbolic tangent
  (`tanh`). If you pass None, no activation is applied
  (ie. "linear" activation: `a(x) = x`).
* <b>`recurrent_activation`</b>: Activation function to use for the recurrent step.
  Default: sigmoid (`sigmoid`). If you pass `None`, no activation is
  applied (ie. "linear" activation: `a(x) = x`).
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
* <b>`kernel_constraint`</b>: Constraint function applied to the `kernel` weights
  matrix. Default: `None`.
* <b>`recurrent_constraint`</b>: Constraint function applied to the `recurrent_kernel`
  weights matrix. Default: `None`.
* <b>`bias_constraint`</b>: Constraint function applied to the bias vector. Default:
  `None`.
* <b>`dropout`</b>: Float between 0 and 1. Fraction of the units to drop for the
  linear transformation of the inputs. Default: 0.
* <b>`recurrent_dropout`</b>: Float between 0 and 1. Fraction of the units to drop for
  the linear transformation of the recurrent state. Default: 0.
* <b>`implementation`</b>: Implementation mode, either 1 or 2.
  Mode 1 will structure its operations as a larger number of
  smaller dot products and additions, whereas mode 2 (default) will
  batch them into fewer, larger operations. These modes will
  have different performance profiles on different hardware and
  for different applications. Default: 2.
* <b>`reset_after`</b>: GRU convention (whether to apply reset gate after or
  before matrix multiplication). False = "before",
  True = "after" (default and CuDNN compatible).


#### Call arguments:


* <b>`inputs`</b>: A 2D tensor, with shape of `[batch, feature]`.
* <b>`states`</b>: A 2D tensor with shape of `[batch, units]`, which is the state from
  the previous time step. For timestep 0, the initial state provided by user
  will be feed to cell.
* <b>`training`</b>: Python boolean indicating whether the layer should behave in
  training mode or in inference mode. Only relevant when `dropout` or
  `recurrent_dropout` is used.



## Compat aliases

* `tf.compat.v2.keras.layers.GRUCell`

