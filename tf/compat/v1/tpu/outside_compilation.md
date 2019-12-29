<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.tpu.outside_compilation" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.tpu.outside_compilation

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/tpu/tpu.py">View source</a>



Builds part of a computation outside any current TPU replicate scope.

``` python
tf.compat.v1.tpu.outside_compilation(
    computation,
    *args,
    **kwargs
)
```



<!-- Placeholder for "Used in" -->

`tf.tpu.outside_compilation()` is used to run ops in `computation` on CPU
instead of running on TPU. For example, users can run ops that are not
supported on TPU's (e.g. tf.summary.write()) by explicitly placing those
ops on CPU's. Below usage of outside compilation will place ops in
`computation_with_string_ops` on CPU.

def computation_with_string_ops(x):
  # strings types are not supported on TPU's and below ops must
  # run on CPU instead.
  output = tf.strings.format('1{}', x)
  return tf.strings.to_number(output)

def tpu_computation():
  # Expected output is 11.
  output = tf.tpu.outside_compilation(computation_with_string_ops, 1)

Outside compilation should be called inside TPUReplicateContext. That is,
`tf.tpu.outside_compilation()` should be called inside a function that is
passed to `tpu.split_compile_and_replicate()` -- this is implied when
outside compilation is invoked inside a function passed to TPUStrategy
`experimental_run_v2()`. If invoked outside of TPUReplicateContext,
then this simply returns the result of `computation`, and therefore,
would be a no-op. Note that outside compilation is different from
`tf.distribute.experimental.TPUStrategy.merge_call()` as logic in
outside compilation is replicated and executed separately for each
replica. On the other hand, `merge_call()` requires a `merge_fn`
to aggregate the inputs from different replicas and is executed only
once.

For variables placed in TPU device, which includes variables created inside
TPUStrategy scope, outside compilation logic must not include variable
read/write. For variables placed on host, which is the case when variables
created via TPUEstimator, variable read/write is only allowed if the variable
is not accessed by any other ops in the TPU computation. Variable read/write
from outside compilation cluster is not visible from TPU computation and
vice versa. Therefore, if outside compilation logic contains such host
variables read/write ops and if the variables are accessed by TPU
computation as well, then this may lead to deadlock.

Internally, `tf.tpu.outside_compilation()` adds outside compilation
attributes to all ops in `computation`. During later graph pass, these
ops with outside compilation attribute is extracted out and replicated
into a host-side graph. Inputs to this extract host-side graph is sent
from TPU computation graph to host graph via a pair of XlaSendToHost and
XlaRecvFromHost ops. Note that using `tf.tpu.outside_compilation()`
may result in tensor transfer between TPU and CPU, leading to non-trivial
performance impact.

#### Args:


* <b>`computation`</b>: A Python function that builds the computation to
  place on the host.
* <b>`*args`</b>: the positional arguments for the computation.
* <b>`**kwargs`</b>: the keyword arguments for the computation.


#### Returns:

The Tensors returned by computation.


