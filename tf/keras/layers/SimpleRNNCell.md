<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.layers.SimpleRNNCell" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.layers.SimpleRNNCell

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/layers/recurrent.py">View source</a>



## Class `SimpleRNNCell`

Cell class for SimpleRNN.

Inherits From: [`Layer`](../../../tf/keras/layers/Layer.md)

<!-- Placeholder for "Used in" -->

See [the Keras RNN API guide](https://www.tensorflow.org/guide/keras/rnn)
for details about the usage of RNN API.

This class processes one step within the whole time sequence input, whereas
`tf.keras.layer.SimpleRNN` processes the whole sequence.

#### Arguments:


* <b>`units`</b>: Positive integer, dimensionality of the output space.
* <b>`activation`</b>: Activation function to use.
  Default: hyperbolic tangent (`tanh`).
  If you pass `None`, no activation is applied
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


#### Call arguments:


* <b>`inputs`</b>: A 2D tensor, with shape of `[batch, feature]`.
* <b>`states`</b>: A 2D tensor with shape of `[batch, units]`, which is the state from
  the previous time step. For timestep 0, the initial state provided by user
  will be feed to cell.
* <b>`training`</b>: Python boolean indicating whether the layer should behave in
  training mode or in inference mode. Only relevant when `dropout` or
  `recurrent_dropout` is used.


#### Examples:



```python
inputs = np.random.random([32, 10, 8]).astype(np.float32)
rnn = tf.keras.layers.RNN(tf.keras.layers.SimpleRNNCell(4))

output = rnn(inputs)  # The output has shape `[32, 4]`.

rnn = tf.keras.layers.RNN(
    tf.keras.layers.SimpleRNNCell(4),
    return_sequences=True,
    return_state=True)

# whole_sequence_output has shape `[32, 10, 4]`.
# final_state has shape `[32, 4]`.
whole_sequence_output, final_state = rnn(inputs)
```



## Compat aliases

* `tf.compat.v1.keras.layers.SimpleRNNCell`
* `tf.compat.v2.keras.layers.SimpleRNNCell`

