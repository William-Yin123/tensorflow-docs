<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.optimizers.Adamax" />
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

# tf.keras.optimizers.Adamax

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/optimizer_v2/adamax.py">View source</a>



## Class `Adamax`

Optimizer that implements the Adamax algorithm.

Inherits From: [`Optimizer`](../../../tf/keras/optimizers/Optimizer.md)

**Aliases**: `tf.optimizers.Adamax`

<!-- Placeholder for "Used in" -->

It is a variant of Adam based on the infinity norm.
Default parameters follow those provided in the paper.
Adamax is sometimes superior to adam, specially in models with embeddings.

References
  see Section 7 of [Kingma et al., 2014](http://arxiv.org/abs/1412.6980)
    ([pdf](http://arxiv.org/pdf/1412.6980.pdf)).

<h2 id="__init__"><code>__init__</code></h2>

<a target="_blank" href="/code/stable/tensorflow/python/keras/optimizer_v2/adamax.py">View source</a>

``` python
__init__(
    learning_rate=0.001,
    beta_1=0.9,
    beta_2=0.999,
    epsilon=1e-07,
    name='Adamax',
    **kwargs
)
```

Construct a new Adamax optimizer.


#### Initialization:



```
m_0 <- 0 (Initialize initial 1st moment vector)
v_0 <- 0 (Initialize the exponentially weighted infinity norm)
t <- 0 (Initialize timestep)
```

The update rule for `variable` with gradient `g` uses an optimization
described at the end of section 7.1 of the paper:

```
t <- t + 1

m_t <- beta1 * m_{t-1} + (1 - beta1) * g
v_t <- max(beta2 * v_{t-1}, abs(g))
variable <- variable - learning_rate / (1 - beta1^t) * m_t / (v_t + epsilon)
```

Similar to AdamOptimizer, the epsilon is added for numerical stability
(especially to get rid of division by zero when v_t = 0).

Contrast to AdamOptimizer, the sparse implementation of this algorithm
(used when the gradient is an IndexedSlices object, typically because of
<a href="../../../tf/gather.md"><code>tf.gather</code></a> or an embedding lookup in the forward pass) only updates
variable slices and corresponding `m_t`, `v_t` terms when that part of
the variable was used in the forward pass. This means that the sparse
behavior is contrast to the dense behavior (similar to some momentum
implementations which ignore momentum unless a variable slice was actually
used).

#### Args:


* <b>`learning_rate`</b>: A `Tensor`, floating point value, or a schedule that is a
  <a href="../../../tf/keras/optimizers/schedules/LearningRateSchedule.md"><code>tf.keras.optimizers.schedules.LearningRateSchedule</code></a>. The learning rate.
* <b>`beta_1`</b>: A float value or a constant float tensor. The exponential decay
  rate for the 1st moment estimates.
* <b>`beta_2`</b>: A float value or a constant float tensor. The exponential decay
  rate for the exponentially weighted infinity norm.
* <b>`epsilon`</b>: A small constant for numerical stability.
* <b>`name`</b>: Optional name for the operations created when applying gradients.
  Defaults to "Adamax".
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

<a target="_blank" href="/code/stable/tensorflow/python/keras/optimizer_v2/adamax.py">View source</a>

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

<a target="_blank" href="/code/stable/tensorflow/python/keras/optimizer_v2/optimizer_v2.py">View source</a>

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

* `tf.compat.v1.keras.optimizers.Adamax`
* `tf.compat.v2.keras.optimizers.Adamax`
* `tf.compat.v2.optimizers.Adamax`

