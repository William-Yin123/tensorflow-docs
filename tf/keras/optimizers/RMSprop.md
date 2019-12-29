<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.optimizers.RMSprop" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="iterations"/>
<meta itemprop="property" content="weights"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="add_slot"/>
<meta itemprop="property" content="add_weight"/>
<meta itemprop="property" content="apply_gradients"/>
<meta itemprop="property" content="from_config"/>
<meta itemprop="property" content="get_config"/>
<meta itemprop="property" content="get_gradients"/>
<meta itemprop="property" content="get_slot"/>
<meta itemprop="property" content="get_slot_names"/>
<meta itemprop="property" content="get_updates"/>
<meta itemprop="property" content="get_weights"/>
<meta itemprop="property" content="minimize"/>
<meta itemprop="property" content="set_weights"/>
<meta itemprop="property" content="variables"/>
</div>

# tf.keras.optimizers.RMSprop

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/optimizer_v2/rmsprop.py">View source</a>



## Class `RMSprop`

Optimizer that implements the RMSprop algorithm.

Inherits From: [`Optimizer`](../../../tf/keras/optimizers/Optimizer.md)

**Aliases**: `tf.optimizers.RMSprop`

<!-- Placeholder for "Used in" -->

A detailed description of rmsprop.

  - maintain a moving (discounted) average of the square of gradients
  - divide gradient by the root of this average

$$mean_square_t = rho * mean_square{t-1} + (1-rho) * gradient ** 2$$
$$mom_t = momentum * mom_{t-1} + learning_rate * gradient / \sqrt{ /
    mean_square_t + \epsilon}$$
$$variable_t := variable_{t-1} - mom_t$$

This implementation of RMSprop uses plain momentum, not Nesterov momentum.

The centered version additionally maintains a moving average of the
gradients, and uses that average to estimate the variance:

$$mean_grad_t = rho * mean_grad_{t-1} + (1-rho) * gradient$$
$$mean_square_t = rho * mean_square_{t-1} + (1-rho) * gradient ** 2$$
$$mom_t = momentum * mom_{t-1} + learning_rate * gradient /
    sqrt(mean_square_t - mean_grad_t**2 + epsilon)$$
$$variable_t := variable_{t-1} - mom_t$$

References
  See ([pdf]
    http://www.cs.toronto.edu/~tijmen/csc321/slides/lecture_slides_lec6.pdf).

<h2 id="__init__"><code>__init__</code></h2>

<a target="_blank" href="/code/stable/tensorflow/python/keras/optimizer_v2/rmsprop.py">View source</a>

``` python
__init__(
    learning_rate=0.001,
    rho=0.9,
    momentum=0.0,
    epsilon=1e-07,
    centered=False,
    name='RMSprop',
    **kwargs
)
```

Construct a new RMSprop optimizer.

Note that in the dense implementation of this algorithm, variables and their
corresponding accumulators (momentum, gradient moving average, square
gradient moving average) will be updated even if the gradient is zero
(i.e. accumulators will decay, momentum will be applied). The sparse
implementation (used when the gradient is an `IndexedSlices` object,
typically because of <a href="../../../tf/gather.md"><code>tf.gather</code></a> or an embedding lookup in the forward pass)
will not update variable slices or their accumulators unless those slices
were used in the forward pass (nor is there an "eventual" correction to
account for these omitted updates). This leads to more efficient updates for
large embedding lookup tables (where most of the slices are not accessed in
a particular graph execution), but differs from the published algorithm.

#### Args:


* <b>`learning_rate`</b>: A `Tensor`, floating point value, or a schedule that is a
  <a href="../../../tf/keras/optimizers/schedules/LearningRateSchedule.md"><code>tf.keras.optimizers.schedules.LearningRateSchedule</code></a>. The learning rate.
* <b>`rho`</b>: Discounting factor for the history/coming gradient
* <b>`momentum`</b>: A scalar tensor.
* <b>`epsilon`</b>: Small value to avoid zero denominator.
* <b>`centered`</b>: If True, gradients are normalized by the estimated variance of
  the gradient; if False, by the uncentered second moment. Setting this to
  True may help with training, but is slightly more expensive in terms of
  computation and memory. Defaults to False.
* <b>`name`</b>: Optional name prefix for the operations created when applying
  gradients. Defaults to "RMSprop".  @compatibility(eager) When eager
  execution is enabled, `learning_rate`, `decay`, `momentum`, and
  `epsilon` can each be a callable that takes no arguments and returns the
  actual value to use. This can be useful for changing these values across
  different invocations of optimizer functions. @end_compatibility
* <b>`**kwargs`</b>: keyword arguments. Allowed to be {`clipnorm`, `clipvalue`, `lr`,
  `decay`}. `clipnorm` is clip gradients by norm; `clipvalue` is clip
  gradients by value, `decay` is included for backward compatibility to
  allow time inverse decay of learning rate. `lr` is included for backward
  compatibility, recommended to use `learning_rate` instead.



## Properties

<h3 id="iterations"><code>iterations</code></h3>

Variable. The number of training steps this Optimizer has run.


<h3 id="weights"><code>weights</code></h3>

Returns variables of this Optimizer based on the order created.




## Methods

<h3 id="add_slot"><code>add_slot</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/keras/optimizer_v2/optimizer_v2.py">View source</a>

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

<a target="_blank" href="/code/stable/tensorflow/python/keras/optimizer_v2/optimizer_v2.py">View source</a>

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

<a target="_blank" href="/code/stable/tensorflow/python/keras/optimizer_v2/optimizer_v2.py">View source</a>

``` python
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

<a target="_blank" href="/code/stable/tensorflow/python/keras/optimizer_v2/rmsprop.py">View source</a>

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

<a target="_blank" href="/code/stable/tensorflow/python/keras/optimizer_v2/optimizer_v2.py">View source</a>

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

<h3 id="get_slot"><code>get_slot</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/keras/optimizer_v2/optimizer_v2.py">View source</a>

``` python
get_slot(
    var,
    slot_name
)
```




<h3 id="get_slot_names"><code>get_slot_names</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/keras/optimizer_v2/optimizer_v2.py">View source</a>

``` python
get_slot_names()
```

A list of names for this optimizer's slots.


<h3 id="get_updates"><code>get_updates</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/keras/optimizer_v2/optimizer_v2.py">View source</a>

``` python
get_updates(
    loss,
    params
)
```




<h3 id="get_weights"><code>get_weights</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/keras/optimizer_v2/optimizer_v2.py">View source</a>

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

This method simply computes gradient using <a href="../../../tf/GradientTape.md"><code>tf.GradientTape</code></a> and calls
`apply_gradients()`. If you want to process the gradient before applying
then call <a href="../../../tf/GradientTape.md"><code>tf.GradientTape</code></a> and `apply_gradients()` explicitly instead
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

<a target="_blank" href="/code/stable/tensorflow/python/keras/optimizer_v2/rmsprop.py">View source</a>

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

<a target="_blank" href="/code/stable/tensorflow/python/keras/optimizer_v2/optimizer_v2.py">View source</a>

``` python
variables()
```

Returns variables of this Optimizer based on the order created.






## Compat aliases

* `tf.compat.v1.keras.optimizers.RMSprop`
* `tf.compat.v2.keras.optimizers.RMSprop`
* `tf.compat.v2.optimizers.RMSprop`

