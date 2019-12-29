<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.train.experimental.enable_mixed_precision_graph_rewrite" />
<meta itemprop="path" content="Stable" />
</div>

# tf.train.experimental.enable_mixed_precision_graph_rewrite

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/training/experimental/mixed_precision.py">View source</a>



Enable mixed precision via a graph rewrite.

``` python
tf.train.experimental.enable_mixed_precision_graph_rewrite(
    opt,
    loss_scale='dynamic'
)
```



<!-- Placeholder for "Used in" -->

Mixed precision is the use of both float32 and float16 data types when
training a model to improve performance. This is achieved via a graph rewrite
operation and a loss-scale optimizer.

Performing arithmetic operations in float16 takes advantage of specialized
processing units, such as NVIDIA Tensor Cores for much higher arithmetic
throughput. However, due to the smaller representable range, performing the
entire training with float16 can result in gradient underflow, that is, small
gradient values becoming zeroes. Instead, performing only select arithmetic
operations in float16 results in higher throughput and decreased training
time when using compatible hardware accelerators while also reducing memory
usage, typically without sacrificing model accuracy.

Note: While the mixed precision rewrite changes the datatype of various
layers throughout the model, the same accuracy reached in float32 is
expected. If a `NaN` gradient occurs with dynamic loss scaling, the model
update for that batch is skipped. In this case, the global step count is not
incremented, and the `LossScaleOptimizer` attempts to decrease the loss
scaling value to avoid `NaN` values in subsequent iterations. This approach
has been shown to achieve the same accuracy as float32 and, in most cases,
better training throughput.

#### Example:



```python
model = tf.keras.models.Sequential([
  ...
])

opt = tf.keras.optimizers.SGD()
opt = tf.train.experimental.enable_mixed_precision_graph_rewrite(opt)

model.compile(loss="categorical_crossentropy",
            optimizer=opt,
            metrics=["accuracy"])

model.fit(x_train, y_train,
        batch_size=batch_size,
        epochs=epochs)
```

For a complete example showing the speed-up on training an image
classification task on CIFAR10, check out this
<a href="https://colab.research.google.com/github/NVIDIA/
DeepLearningExamples/blob/master/TensorFlow/docs/amp/notebook_v1.14/
auto_mixed_precision_demo_cifar10.ipynb">Colab notebook</a>.

Calling `enable_mixed_precision_graph_rewrite(opt)` enables the graph rewrite
operation before computing gradients. The function additionally returns an
`Optimizer`(`opt`) wrapped with a `LossScaleOptimizer`. This prevents
underflow in the float16 tensors during the backward pass. An optimizer of
type `tf.train.Optimizer` or <a href="../../../tf/keras/optimizers/Optimizer.md"><code>tf.keras.optimizers.Optimizer</code></a> must be passed
to this function, which will then be wrapped to use loss scaling.

<img src="
http://developer.download.nvidia.com/compute/machine-learning/frameworks/
TF_mixed_precision_training.png" width="500px">

The graph rewrite operation changes the `dtype` of certain operations in the
graph from float32 to float16. There are several categories of operations
that are either included or excluded by this rewrite operation. The following
categories of Ops are defined inside corresponding functions under the class
`AutoMixedPrecisionLists` in
<a href="https://github.com/tensorflow/tensorflow/blob/master/tensorflow/
core/grappler/optimizers/auto_mixed_precision_lists.h">
auto_mixed_precision_lists.h</a>:

* `ClearList`: Ops that do not have numerically significant adverse effects.
E.g. `ArgMax` and `Floor`.
* `WhiteList`: Ops that are considered numerically safe for execution in
float16, and thus are always converted. E.g. `Conv2D`.
* `BlackList`: Ops that are numerically unsafe to execute in float16 and
can negatively affect downstream nodes. E.g. `Softmax`.
* `GrayList`: Ops that are considered numerically safe for execution in
float16 unless downstream from a BlackList Op. E.g. `Add` and `AvgPool`.

When this function is used, gradients should only be computed and applied
with the returned optimizer, either by calling `opt.minimize()` or
`opt.compute_gradients()` followed by `opt.apply_gradients()`.
Gradients should not be computed with <a href="../../../tf/gradients.md"><code>tf.gradients</code></a> or <a href="../../../tf/GradientTape.md"><code>tf.GradientTape</code></a>.
This is because the returned optimizer will apply loss scaling, and
<a href="../../../tf/gradients.md"><code>tf.gradients</code></a> or <a href="../../../tf/GradientTape.md"><code>tf.GradientTape</code></a> will not. If you do directly use
<a href="../../../tf/gradients.md"><code>tf.gradients</code></a> or <a href="../../../tf/GradientTape.md"><code>tf.GradientTape</code></a>, your model may not converge due to
float16 underflow problems.

When eager execution is enabled, the mixed precision graph rewrite is only
enabled within <a href="../../../tf/function.md"><code>tf.function</code></a>, as outside <a href="../../../tf/function.md"><code>tf.function</code></a>, there is no graph.

For NVIDIA GPUs with Tensor cores, as a general performance guide, dimensions
(such as batch size, input size, output size, and channel counts)
should be powers of two if under 256, or  otherwise divisible by 8 if above
256. For more information, check out the
[NVIDIA Deep Learning Performance Guide](
https://docs.nvidia.com/deeplearning/sdk/dl-performance-guide/index.html).

Currently, mixed precision is only enabled on NVIDIA Tensor Core GPUs with
Compute Capability 7.0 and above (Volta, Turing, or newer architectures). The
parts of the graph on CPUs and TPUs are untouched by the graph rewrite. TPU
support is coming soon. CPUs are not supported, as CPUs do not run float16
operations faster than float32 operations.

#### Raises:

`ValueError` when
`mixed_precision_global_state.using_default_mixed_precision_policy`
is set to `False` before
<a href="../../../tf/train/experimental/enable_mixed_precision_graph_rewrite.md"><code>tf.train.experimental.enable_mixed_precision_graph_rewrite()</code></a>
is called.



#### Args:


* <b>`opt`</b>: An instance of a <a href="../../../tf/keras/optimizers/Optimizer.md"><code>tf.keras.optimizers.Optimizer</code></a>.
* <b>`loss_scale`</b>: Either an int/float, the string `"dynamic"`, or an instance of a
  <a href="../../../tf/mixed_precision/experimental/LossScale.md"><code>tf.mixed_precision.experimental.LossScale</code></a>. The loss scale to use. It is
  recommended to keep this as its default value of `"dynamic"`, which will
  adjust the scaling automatically to prevent `Inf` or `NaN` values.


#### Returns:

A version of `opt` that will use loss scaling to prevent underflow.


## Compat aliases

* `tf.compat.v2.train.experimental.enable_mixed_precision_graph_rewrite`

