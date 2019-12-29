<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.mixed_precision.experimental.LossScaleOptimizer" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="iterations"/>
<meta itemprop="property" content="learning_rate"/>
<meta itemprop="property" content="loss_scale"/>
<meta itemprop="property" content="lr"/>
<meta itemprop="property" content="weights"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="add_slot"/>
<meta itemprop="property" content="add_weight"/>
<meta itemprop="property" content="apply_gradients"/>
<meta itemprop="property" content="from_config"/>
<meta itemprop="property" content="get_config"/>
<meta itemprop="property" content="get_gradients"/>
<meta itemprop="property" content="get_scaled_loss"/>
<meta itemprop="property" content="get_slot"/>
<meta itemprop="property" content="get_slot_names"/>
<meta itemprop="property" content="get_unscaled_gradients"/>
<meta itemprop="property" content="get_updates"/>
<meta itemprop="property" content="get_weights"/>
<meta itemprop="property" content="minimize"/>
<meta itemprop="property" content="set_weights"/>
<meta itemprop="property" content="variables"/>
</div>

# tf.keras.mixed_precision.experimental.LossScaleOptimizer

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/mixed_precision/experimental/loss_scale_optimizer.py">View source</a>



## Class `LossScaleOptimizer`

An optimizer that applies loss scaling.

Inherits From: [`Optimizer`](../../../../tf/keras/optimizers/Optimizer.md)

<!-- Placeholder for "Used in" -->

Loss scaling is a process that multiplies the loss by a multiplier called the
loss scale, and divides each gradient by the same multiplier. The pseudocode
for this process is:

```
loss = ...
loss *= loss_scale
grads = gradients(loss, vars)
grads /= loss_scale
```

Mathematically, loss scaling has no effect, but can help avoid numerical
underflow in intermediate gradients when float16 tensors are used. By
multiplying the loss, each intermediate gradient will have the same multiplier
applied.

The loss scale can either be a fixed constant, chosen by the user, or be
dynamically determined. Dynamically determining the loss scale is convenient
as a loss scale does not have to be explicitly chosen. However it reduces
performance.

This optimizer wraps another optimizer and applies loss scaling to it via a
`LossScale`. Loss scaling is applied whenever gradients are
computed, either through `minimize()` or `get_gradients()`. The loss scale is
updated via <a href="../../../../tf/mixed_precision/experimental/LossScale.md#update"><code>LossScale.update()</code></a> whenever gradients are applied, either
through `minimize()` or `apply_gradients()`. For example:

```python
opt = tf.keras.optimizers.SGD(0.1)
opt = tf.keras.mixed_precision.experimental.LossScaleOptimizer(opt, "dynamic")
# 'minimize' applies loss scaling to the loss and updates the loss sale.
opt.minimize(loss_fn)
```

If a <a href="../../../../tf/GradientTape.md"><code>tf.GradientTape</code></a> is used to compute gradients instead of
<a href="../../../../tf/keras/optimizers/Optimizer.md#minimize"><code>LossScaleOptimizer.minimize</code></a> or <a href="../../../../tf/keras/mixed_precision/experimental/LossScaleOptimizer.md#get_gradients"><code>LossScaleOptimizer.get_gradients</code></a>, the loss
and gradients must be scaled manually. This can be done by calling
<a href="../../../../tf/keras/mixed_precision/experimental/LossScaleOptimizer.md#get_scaled_loss"><code>LossScaleOptimizer.get_scaled_loss</code></a> before passing the loss to
<a href="../../../../tf/GradientTape.md"><code>tf.GradientTape</code></a>, and <a href="../../../../tf/keras/mixed_precision/experimental/LossScaleOptimizer.md#get_unscaled_gradients"><code>LossScaleOptimizer.get_unscaled_gradients</code></a> after
computing the gradients with <a href="../../../../tf/GradientTape.md"><code>tf.GradientTape</code></a>. For example:

```python
opt = tf.keras.mixed_precision.experimental.LossScaleOptimizer(...)
vars = ...
with tf.GradientTape() as tape:
  loss = ...
  scaled_loss = opt.get_scaled_loss(loss)
scaled_grads = tape.gradient(scaled_loss, vars)
grads = opt.get_unscaled_gradients(scaled_grads)
opt.apply_gradients(zip(grads, vars))  # Loss scale will be updated here
```

<h2 id="__init__"><code>__init__</code></h2>

<a target="_blank" href="/code/stable/tensorflow/python/keras/mixed_precision/experimental/loss_scale_optimizer.py">View source</a>

``` python
__init__(
    optimizer,
    loss_scale
)
```

Initializes this loss scale optimizer.


#### Args:


* <b>`optimizer`</b>: The Optimizer instance to wrap.
* <b>`loss_scale`</b>: The loss scale to scale the loss and gradients. This can
  either be an int/float to use a fixed loss scale, the string "dynamic"
  to use dynamic loss scaling, or an instance of a LossScale. The string
  "dynamic" equivalent to passing `DynamicLossScale()`, and passing an
  int/float is equivalent to passing a FixedLossScale with the given loss
  scale.



## Properties

<h3 id="iterations"><code>iterations</code></h3>

Variable. The number of training steps this Optimizer has run.


<h3 id="learning_rate"><code>learning_rate</code></h3>




<h3 id="loss_scale"><code>loss_scale</code></h3>

The `LossScale` instance associated with this optimizer.


<h3 id="lr"><code>lr</code></h3>




<h3 id="weights"><code>weights</code></h3>

Returns variables of this Optimizer based on the order created.




## Methods

<h3 id="add_slot"><code>add_slot</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/keras/mixed_precision/experimental/loss_scale_optimizer.py">View source</a>

``` python
add_slot(
    var,
    slot_name,
    initializer='zeros'
)
```

Add a new slot variable for `var`.


<h3 id="add_weight"><code>add_weight</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/keras/optimizer_v2/optimizer_v2.py">View source</a>

``` python
add_weight(
    name,
    shape,
    dtype=None,
    initializer='zeros',
    trainable=None,
    synchronization=tf.VariableSynchronization.AUTO,
    aggregation=tf.compat.v1.VariableAggregation.NONE
)
```




<h3 id="apply_gradients"><code>apply_gradients</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/keras/mixed_precision/experimental/loss_scale_optimizer.py">View source</a>

``` python
apply_gradients(
    grads_and_vars,
    name=None
)
```

Apply gradients to variables.

This is the second part of `minimize()`. It returns an `Operation` that
applies gradients.

#### Args:


* <b>`grads_and_vars`</b>: List of (gradient, variable) pairs.
* <b>`name`</b>: Optional name for the returned operation.  Default to the name
  passed to the `Optimizer` constructor.


#### Returns:

An `Operation` that applies the specified gradients. The `iterations`
will be automatically increased by 1.



#### Raises:


* <b>`TypeError`</b>: If `grads_and_vars` is malformed.
* <b>`ValueError`</b>: If none of the variables have gradients.

<h3 id="from_config"><code>from_config</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/keras/mixed_precision/experimental/loss_scale_optimizer.py">View source</a>

``` python
@classmethod
from_config(
    cls,
    config,
    custom_objects=None
)
```

Creates an optimizer from its config.

This method is the reverse of `get_config`,
capable of instantiating the same optimizer from the config
dictionary.

#### Arguments:


* <b>`config`</b>: A Python dictionary, typically the output of get_config.
* <b>`custom_objects`</b>: A Python dictionary mapping names to additional Python
  objects used to create this optimizer, such as a function used for a
  hyperparameter.


#### Returns:

An optimizer instance.


<h3 id="get_config"><code>get_config</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/keras/mixed_precision/experimental/loss_scale_optimizer.py">View source</a>

``` python
get_config()
```

Returns the config of the optimimizer.

An optimizer config is a Python dictionary (serializable)
containing the configuration of an optimizer.
The same optimizer can be reinstantiated later
(without any saved state) from this configuration.

#### Returns:

Python dictionary.


<h3 id="get_gradients"><code>get_gradients</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/keras/mixed_precision/experimental/loss_scale_optimizer.py">View source</a>

``` python
get_gradients(
    loss,
    params
)
```

Returns gradients of `loss` with respect to `params`.


#### Arguments:


* <b>`loss`</b>: Loss tensor.
* <b>`params`</b>: List of variables.


#### Returns:

List of gradient tensors.



#### Raises:


* <b>`ValueError`</b>: In case any gradient cannot be computed (e.g. if gradient
  function not implemented).

<h3 id="get_scaled_loss"><code>get_scaled_loss</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/keras/mixed_precision/experimental/loss_scale_optimizer.py">View source</a>

``` python
get_scaled_loss(loss)
```

Scales the loss by the loss scale.

This method is only needed if you compute gradients manually, e.g. with
<a href="../../../../tf/GradientTape.md"><code>tf.GradientTape</code></a>. In that case, call this method to scale the loss before
passing the loss to <a href="../../../../tf/GradientTape.md"><code>tf.GradientTape</code></a>. If you use
<a href="../../../../tf/keras/optimizers/Optimizer.md#minimize"><code>LossScaleOptimizer.minimize</code></a> or <a href="../../../../tf/keras/mixed_precision/experimental/LossScaleOptimizer.md#get_gradients"><code>LossScaleOptimizer.get_gradients</code></a>, loss
scaling is automatically applied and this method is unneeded.

If this method is called, `get_unscaled_gradients` should also be called.
See the <a href="../../../../tf/keras/mixed_precision/experimental/LossScaleOptimizer.md"><code>tf.keras.mixed_precision.experimental.LossScaleOptimizer</code></a> doc for
an example.

#### Args:


* <b>`loss`</b>: The loss, which will be multiplied by the loss scale. Can either be
  a tensor or a callable returning a tensor.


#### Returns:

`loss` multiplied by <a href="../../../../tf/keras/mixed_precision/experimental/LossScaleOptimizer.md#loss_scale"><code>LossScaleOptimizer.loss_scale()</code></a>.


<h3 id="get_slot"><code>get_slot</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/keras/mixed_precision/experimental/loss_scale_optimizer.py">View source</a>

``` python
get_slot(
    var,
    slot_name
)
```




<h3 id="get_slot_names"><code>get_slot_names</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/keras/mixed_precision/experimental/loss_scale_optimizer.py">View source</a>

``` python
get_slot_names()
```

A list of names for this optimizer's slots.


<h3 id="get_unscaled_gradients"><code>get_unscaled_gradients</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/keras/mixed_precision/experimental/loss_scale_optimizer.py">View source</a>

``` python
get_unscaled_gradients(grads)
```

Unscales the gradients by the loss scale.

This method is only needed if you compute gradients manually, e.g. with
<a href="../../../../tf/GradientTape.md"><code>tf.GradientTape</code></a>. In that case, call this method to unscale the gradients
after computing them with <a href="../../../../tf/GradientTape.md"><code>tf.GradientTape</code></a>. If you use
<a href="../../../../tf/keras/optimizers/Optimizer.md#minimize"><code>LossScaleOptimizer.minimize</code></a> or <a href="../../../../tf/keras/mixed_precision/experimental/LossScaleOptimizer.md#get_gradients"><code>LossScaleOptimizer.get_gradients</code></a>, loss
scaling is automatically applied and this method is unneeded.

If this method is called, `get_scaled_loss` should also be called. See
the <a href="../../../../tf/keras/mixed_precision/experimental/LossScaleOptimizer.md"><code>tf.keras.mixed_precision.experimental.LossScaleOptimizer</code></a> doc for an
example.

#### Args:


* <b>`grads`</b>: A list of tensors, each which will be divided by the loss scale.
  Can have None values, which are ignored.


#### Returns:

A new list the same size as `grads`, where every non-None value in `grads`
is divided by <a href="../../../../tf/keras/mixed_precision/experimental/LossScaleOptimizer.md#loss_scale"><code>LossScaleOptimizer.loss_scale()</code></a>.


<h3 id="get_updates"><code>get_updates</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/keras/optimizer_v2/optimizer_v2.py">View source</a>

``` python
get_updates(
    loss,
    params
)
```




<h3 id="get_weights"><code>get_weights</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/keras/mixed_precision/experimental/loss_scale_optimizer.py">View source</a>

``` python
get_weights()
```

Returns the current weights of the optimizer.

The weights of an optimizer are its state (ie, variables).
This function returns the weight values associated with this
optimizer as a list of Numpy arrays. The first value is always the
iterations count of the optimizer, followed by the optimizer's state
variables in the order they were created. The returned list can in turn
be used to load state into similarly parameterized optimizers.

For example, the RMSprop optimizer for this simple model returns a list of
three values-- the iteration count, followed by the root-mean-square value
of the kernel and bias of the single Dense layer:

```
>>> opt = tf.keras.optimizers.RMSprop()
>>> m = tf.keras.models.Sequential([tf.keras.layers.Dense(10)])
>>> m.compile(opt, loss='mse')
>>> data = np.arange(100).reshape(5, 20)
>>> labels = np.zeros(5)
>>> print('Training'); results = m.fit(data, labels)
Training ...
>>> len(opt.get_weights())
3
```

#### Returns:

Weights values as a list of numpy arrays.


<h3 id="minimize"><code>minimize</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/keras/optimizer_v2/optimizer_v2.py">View source</a>

``` python
minimize(
    loss,
    var_list,
    grad_loss=None,
    name=None
)
```

Minimize `loss` by updating `var_list`.

This method simply computes gradient using <a href="../../../../tf/GradientTape.md"><code>tf.GradientTape</code></a> and calls
`apply_gradients()`. If you want to process the gradient before applying
then call <a href="../../../../tf/GradientTape.md"><code>tf.GradientTape</code></a> and `apply_gradients()` explicitly instead
of using this function.

#### Args:


* <b>`loss`</b>: A callable taking no arguments which returns the value to minimize.
* <b>`var_list`</b>: list or tuple of `Variable` objects to update to minimize
  `loss`, or a callable returning the list or tuple of `Variable` objects.
  Use callable when the variable list would otherwise be incomplete before
  `minimize` since the variables are created at the first time `loss` is
  called.
* <b>`grad_loss`</b>: Optional. A `Tensor` holding the gradient computed for `loss`.
* <b>`name`</b>: Optional name for the returned operation.


#### Returns:

An `Operation` that updates the variables in `var_list`. The `iterations`
will be automatically increased by 1.



#### Raises:


* <b>`ValueError`</b>: If some of the variables are not `Variable` objects.

<h3 id="set_weights"><code>set_weights</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/keras/mixed_precision/experimental/loss_scale_optimizer.py">View source</a>

``` python
set_weights(weights)
```

Sett the weights of the optimizer.

The weights of an optimizer are its state (ie, variables).
This function takes the weight values associated with this
optimizer as a list of Numpy arrays. The first value is always the
iterations count of the optimizer, followed by the optimizer's state
variables in the order they are created. The passed values are used to set
the new state of the optimizer.

For example, the RMSprop optimizer for this simple model takes a list of
three values-- the iteration count, followed by the root-mean-square value
of the kernel and bias of the single Dense layer:

```
>>> opt = tf.keras.optimizers.RMSprop()
>>> m = tf.keras.models.Sequential([tf.keras.layers.Dense(10)])
>>> m.compile(opt, loss='mse')
>>> data = np.arange(100).reshape(5, 20)
>>> labels = np.zeros(5)
>>> print('Training'); results = m.fit(data, labels)
Training ...
>>> new_weights = [np.array(10), np.ones([20, 10]), np.zeros([10])]
>>> opt.set_weights(new_weights)
>>> opt.iterations
<tf.Variable 'RMSprop/iter:0' shape=() dtype=int64, numpy=10>
```

#### Arguments:


* <b>`weights`</b>: weight values as a list of numpy arrays.

<h3 id="variables"><code>variables</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/keras/mixed_precision/experimental/loss_scale_optimizer.py">View source</a>

``` python
variables()
```

Returns variables of this Optimizer based on the order created.






## Compat aliases

* `tf.compat.v1.keras.mixed_precision.experimental.LossScaleOptimizer`
* `tf.compat.v2.keras.mixed_precision.experimental.LossScaleOptimizer`

