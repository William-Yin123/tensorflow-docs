<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.keras.layers.LSTMCell" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.keras.layers.LSTMCell

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/layers/recurrent.py">View source</a>



## Class `LSTMCell`

Cell class for the LSTM layer.

Inherits From: [`Layer`](../../../../../tf/keras/layers/Layer.md)

<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`units`</b>: Positive integer, dimensionality of the output space.
* <b>`activation`</b>: Activation function to use.
  Default: hyperbolic tangent (`tanh`).
  If you pass `None`, no activation is applied
  (ie. "linear" activation: `a(x) = x`).
* <b>`recurrent_activation`</b>: Activation function to use
  for the recurrent step.
  Default: hard sigmoid (`hard_sigmoid`).
  If you pass `None`, no activation is applied
  (ie. "linear" activation: `a(x) = x`).
* <b>`use_bias`</b>: Boolean, whether the layer uses a bias vector.
* <b>`kernel_initializer`</b>: Initializer for the `kernel` weights matrix,
  used for the linear transformation of the inputs.
* <b>`recurrent_initializer`</b>: Initializer for the `recurrent_kernel`
  weights matrix,
  used for the linear transformation of the recurrent state.
* <b>`bias_initializer`</b>: Initializer for the bias vector.
* <b>`unit_forget_bias`</b>: Boolean.
  If True, add 1 to the bias of the forget gate at initialization.
  Setting it to true will also force `bias_initializer="zeros"`.
  This is recommended in [Jozefowicz et
    al.](http://www.jmlr.org/proceedings/papers/v37/jozefowicz15.pdf)
* <b>`kernel_regularizer`</b>: Regularizer function applied to
  the `kernel` weights matrix.
* <b>`recurrent_regularizer`</b>: Regularizer function applied to
  the `recurrent_kernel` weights matrix.
* <b>`bias_regularizer`</b>: Regularizer function applied to the bias vector.
* <b>`kernel_constraint`</b>: Constraint function applied to
  the `kernel` weights matrix.
* <b>`recurrent_constraint`</b>: Constraint function applied to
  the `recurrent_kernel` weights matrix.
* <b>`bias_constraint`</b>: Constraint function applied to the bias vector.
* <b>`dropout`</b>: Float between 0 and 1.
  Fraction of the units to drop for
  the linear transformation of the inputs.
* <b>`recurrent_dropout`</b>: Float between 0 and 1.
  Fraction of the units to drop for
  the linear transformation of the recurrent state.
* <b>`implementation`</b>: Implementation mode, either 1 or 2.
  Mode 1 will structure its operations as a larger number of
  smaller dot products and additions, whereas mode 2 will
  batch them into fewer, larger operations. These modes will
  have different performance profiles on different hardware and
  for different applications.


#### Call arguments:


* <b>`inputs`</b>: A 2D tensor.
* <b>`states`</b>: List of state tensors corresponding to the previous timestep.
* <b>`training`</b>: Python boolean indicating whether the layer should behave in
  training mode or in inference mode. Only relevant when `dropout` or
  `recurrent_dropout` is used.



