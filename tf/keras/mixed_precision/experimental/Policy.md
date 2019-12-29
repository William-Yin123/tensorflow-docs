<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.mixed_precision.experimental.Policy" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="compute_dtype"/>
<meta itemprop="property" content="loss_scale"/>
<meta itemprop="property" content="name"/>
<meta itemprop="property" content="should_cast_variables"/>
<meta itemprop="property" content="variable_dtype"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="from_config"/>
<meta itemprop="property" content="get_config"/>
</div>

# tf.keras.mixed_precision.experimental.Policy

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/mixed_precision/experimental/policy.py">View source</a>



## Class `Policy`

A dtype policy for a Keras layer.



<!-- Placeholder for "Used in" -->

A dtype policy determines dtype-related aspects of a layer, such as its
computation and variable dtypes. Each layer has a policy. Policies can be
passed to the `dtype` argument of layer constructors, or a global policy can
be set with <a href="../../../../tf/keras/mixed_precision/experimental/set_policy.md"><code>tf.keras.mixed_precision.experimental.set_policy</code></a>. A layer will
default to the global policy if no policy is passed to it's constructor.

For many models, each layer's policy will have the same compute dtype and
variable dtype, which will typically be float32. In this case, we refer to the
singular dtype as the layer's dtype, which can be queried by the property
<a href="../../../../tf/keras/layers/Layer.md#dtype"><code>tf.keras.layers.Layer.dtype</code></a>.

When mixed precision training is used, most layers will instead have a float16
or bfloat16 compute dtype and a float32 variable dtype, and so the layer does
not have a single dtype. See [this
link](https://docs.nvidia.com/deeplearning/sdk/mixed-precision-training/index.html)
for more information on mixed precision training. When the variable dtype does
not match the compute dtype, variables will be automatically casted to the
compute dtype to avoid type errors. In this case,
<a href="../../../../tf/keras/layers/Layer.md#dtype"><code>tf.keras.layers.Layer.dtype</code></a> refers to the variable dtype, not the compute
dtype.

Certain policies also have a <a href="../../../../tf/mixed_precision/experimental/LossScale.md"><code>tf.mixed_precision.experimental.LossScale</code></a>
instance, which is used by <a href="../../../../tf/keras/Model.md"><code>tf.keras.Model</code></a>s to performance loss scaling. Loss
scaling is a technique used with mixed precision to avoid numerical underflow
in float16 gradients. Loss scaling is only done by Models in <a href="../../../../tf/keras/Model.md#fit"><code>Model.fit</code></a>,
<a href="../../../../tf/keras/Model.md#train_on_batch"><code>Model.train_on_batch</code></a>, and similar methods. Layers which are not Models
ignore the loss scale.

Policies are constructed by passing a string to the constructor, e.g.
`tf.keras.mixed_precision.experimental.Policy('float32')`. The string
determines the compute and variable dtypes. It can be one of the following:

  * Any dtype name, such as 'float32' or 'float64'. Both the variable and
    compute dtypes will be that dtype. No loss scaling is done by default.
  * 'mixed_float16' or 'mixed_bfloat16': The compute dtype is float16 or
    bfloat16, while the variable dtype is float32. These policies are used for
    mixed precision training. With 'mixed_float16', a dynamic loss scale is
    used by default. 'mixed_bfloat16' does no loss scaling by default, as loss
    scaling is unnecessary with bfloat16.

### How to use mixed precision in a Keras model

To use mixed precision in a Keras model, the `'mixed_float16'` or
`'mixed_bfloat16'` policy can be used.
<a href="../../../../tf/keras/mixed_precision/experimental/set_policy.md"><code>tf.keras.mixed_precision.experimental.set_policy</code></a> can be used to set the
default policy for layers if no policy is passed to them. For example:

```python
tf.keras.mixed_precision.experimental.set_policy('mixed_float16')
model = tf.keras.models.Sequential([
    tf.keras.layers.Input((100,)),
    # Dense layers use global policy of 'mixed_float16', which does
    # computations in float16 while keeping variables in float32.
    tf.keras.layers.Dense(10),
    tf.keras.layers.Dense(10),
    # Softmax should be done in float32 for numeric stability. We pass
    # dtype='float32' to use float32 instead of the global policy.
    tf.keras.layers.Activation('softmax', dtype='float32')
])
model.compile(...)
model.fit(...)  # Train `model`
```

Alternatively, the policy can be passed to individual layers instead of
setting the global policy with `set_policy`:

```python
policy = tf.keras.mixed_precision.experimental.Policy('mixed_float16')
model = tf.keras.models.Sequential([
    tf.keras.layers.Input((100,)),
    tf.keras.layers.Dense(10, dtype=policy),
    tf.keras.layers.Dense(10, dtype=policy),
    # Softmax should be done in float32 for numeric stability.
    tf.keras.layers.Activation('softmax', dtype='float32')
])
model.compile(...)
model.fit(...)  # Train `model`
```

Note the `'mixed_float16'` policy will apply loss scaling by default in
<a href="../../../../tf/keras/Model.md#fit"><code>Model.fit</code></a>, <a href="../../../../tf/keras/Model.md#train_on_batch"><code>Model.train_on_batch</code></a>, and other training methods. If no such
method is used (e.g., a custom training loop is used) and `'mixed_float16'` is
used, the loss scale must be manually applied. See
<a href="../../../../tf/keras/mixed_precision/experimental/LossScaleOptimizer.md"><code>tf.keras.mixed_precision.experimental.LossScaleOptimizer</code></a> for details. For
`'mixed_bfloat16'`, no loss scaling is done and loss scaling never needs to be
manually applied.

### How to use float64 in a Keras model

Using float64 is similar to mixed precision. Either the global policy can be
set to float64, or `dtype='float64'` can be passed to individual layers. For
example, to set the global policy:

```python
tf.keras.mixed_precision.experimental.set_policy('float64')
model = tf.keras.models.Sequential([
    tf.keras.layers.Input((100,)),
    # All layers use global policy of 'float64', which does computations and
    # creates variables in float64.
    tf.keras.layers.Dense(10),
    tf.keras.layers.Dense(10),
    tf.keras.layers.Activation('softmax')
])
model.compile(...)
model.fit(...)  # Train `model`
```

### How a layer uses its policy's compute dtype

A layer will cast its inputs to its compute dtype in TensorFlow 2. For
example:

```python
x = tf.ones((4, 4, 4, 4), dtype='float64')
# `layer`'s policy defaults to float32.
layer = tf.keras.layers.Conv2D(filters=4, kernel_size=2)

# `layer` casts it's inputs to its compute dtype, which is float32, and does
# computations in float32.
y = layer(x)
print(y.dtype)  # float32
```

Currently, only tensors in the first argument to the layer's `call` method are
casted. For example:

```python
class MyLayer(tf.keras.layers.Layer):
  # Bug! `b` will not be casted.
  def call(self, a, b):
    return a + 1., b + 1.

a = tf.constant(1., dtype="float32")
b = tf.constant(1., dtype="float32")

layer = MyLayer(dtype="float64")
x, y = layer(a, b)
print(x.dtype)  # float64
print(y.dtype)  # float32. Not casted since `b` was not passed to first input
```

It is recommended to accept tensors only in the first argument. This way, all
tensors are casted to the layer's compute dtype. `MyLayer` should therefore be
written as:

```python
class MyLayer(tf.keras.layers.Layer):
  # Now, all tensor inputs will be casted.
  def call(self, inputs):
    a, b = inputs
    return a + 1., b + 1.

a = tf.constant(1., dtype="float32")
b = tf.constant(1., dtype="float32")

layer = MyLayer(dtype="float64")
x, y = layer((a, b))
print(x.dtype)  # float64
print(y.dtype)  # float64.
```

Other arguments are not automatically casted for technical reasons, but this
may change in a future minor release.

A layer subclass can prevent its inputs from being autocasted by passing
`autocast=False` to the layer constructor. For example:

```python
class NonAutoCastingLayer(tf.keras.layers.Layer):

  def __init__(self, **kwargs):
    kwargs['autocast'] = False
    super(NonAutoCastingLayer, self).__init__(**kwargs)

  def call(self, inp):
    return inp

x = tf.ones((4, 4, 4, 4), dtype='float32')
layer = NonAutoCastingLayer(dtype='float64')
y = layer(x)  # MyLayer will not cast inputs to it's compute dtype of float32
print(y.dtype)  # float32
```

### The deprecated "infer" policy

In addition to the above mentioned policies, a policy can also be "infer".
This Policy is deprecated, and it is not recommended. When a layer has an
infer policy, it will infer the computation and variable dtype from the first
input the first time the layer is called. Once the layer is called for the
first time, the layer's policy will change to the dtype of the first input.

In TensorFlow 1, only the "infer" policy is available.

<h2 id="__init__"><code>__init__</code></h2>

<a target="_blank" href="/code/stable/tensorflow/python/keras/mixed_precision/experimental/policy.py">View source</a>

``` python
__init__(
    name,
    loss_scale=USE_DEFAULT
)
```

Constructs the policy.

The `name` argument determines the compute and variable dtype, the default
loss scale, and has no additional effect on the Policy. The compute and
variable dtypes can only be specified through `name`, and cannot be
specified directly.

#### Args:


* <b>`name`</b>: A string. Can be one of the following values:
  * Any dtype name, such as 'float32' or 'float64'. Both the variable and
    compute dtypes will be that dtype.
  * 'mixed_float16' or 'mixed_bfloat16': The compute dtype is float16 or
    bfloat16, while the variable dtype is float32. With 'mixed_float16',
    a dynamic loss scale is used. These policies are used for mixed
    precision training.
  * 'infer' (deprecated): Infer the compute and variable dtype from the
    input dtype.
* <b>`loss_scale`</b>: A <a href="../../../../tf/mixed_precision/experimental/LossScale.md"><code>tf.mixed_precision.experimental.LossScale</code></a>, an int (which
uses a `FixedLossScale`), or the string "dynamic" (which uses a
`DynamicLossScale`). Defaults to using no loss scaling unless `name` is
"mixed_float16", in which case this defaults to "dynamic". Only
<a href="../../../../tf/keras/Model.md"><code>tf.keras.Model</code></a>s, not layers, use the loss scale, and it is only used
during <a href="../../../../tf/keras/Model.md#fit"><code>Model.fit</code></a>, <a href="../../../../tf/keras/Model.md#train_on_batch"><code>Model.train_on_batch</code></a>, and other similar methods.



## Properties

<h3 id="compute_dtype"><code>compute_dtype</code></h3>

The compute dtype of this policy.

This is the dtype layers will do their computations in.

Note that even if the compute dtype is float16 or bfloat16, hardware devices
may not do individual adds, multiplies, and other fundamental operations in
[b]float16, but instead may do some of them in float32 for numeric
stability. The compute dtype is the dtype of the inputs and outputs of the
TensorFlow ops that the layer executes. Internally, many TensorFlow ops will
do certain internal calculations in float32, or some other device-internal
intermediate format with higher precision than [b]float16, to increase
numeric stability.

For example, a <a href="../../../../tf/keras/layers/Dense.md"><code>tf.keras.layers.Dense</code></a> layer, when run on a GPU with a
float16 compute dtype, will pass float16 inputs to tf.matmul. But, tf.matmul
will do use float32 intermediate math. The performance benefit of float16 is
still apparent, due to increased memory bandwidth and the fact modern GPUs
have specialized hardware for computing matmuls on float16 while still
keeping intermediate computations in float32.

#### Returns:

The compute dtype of this policy, or None if the compute dtype should be
inferred from the inputs.


<h3 id="loss_scale"><code>loss_scale</code></h3>

Returns the loss scale of this Policy.


#### Returns:

A <a href="../../../../tf/mixed_precision/experimental/LossScale.md"><code>tf.mixed_precision.experimental.LossScale</code></a>, or None.


<h3 id="name"><code>name</code></h3>

Returns the name of this policy.


<h3 id="should_cast_variables"><code>should_cast_variables</code></h3>

Returns True if variables should be casted.

This is true if the variable dtype is not the same as the compute dtype.

#### Returns:

True, if variables should be casted.


<h3 id="variable_dtype"><code>variable_dtype</code></h3>

The variable dtype of this policy.

This is the dtype layers will create their variables in, unless a layer
explicitly chooses a different dtype. If this is different than
<a href="../../../../tf/keras/mixed_precision/experimental/Policy.md#compute_dtype"><code>Policy.compute_dtype</code></a>, Layers will cast variables to the compute dtype to
avoid type errors.

#### Returns:

The variable dtype of this policy, or None if the variable dtype should be
inferred from the inputs.




## Methods

<h3 id="from_config"><code>from_config</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/keras/mixed_precision/experimental/policy.py">View source</a>

``` python
@classmethod
from_config(
    cls,
    config,
    custom_objects=None
)
```




<h3 id="get_config"><code>get_config</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/keras/mixed_precision/experimental/policy.py">View source</a>

``` python
get_config()
```








## Compat aliases

* `tf.compat.v1.keras.mixed_precision.experimental.Policy`
* `tf.compat.v2.keras.mixed_precision.experimental.Policy`

