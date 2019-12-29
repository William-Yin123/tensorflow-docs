<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.debugging.experimental.enable_dump_debug_info" />
<meta itemprop="path" content="Stable" />
</div>

# tf.debugging.experimental.enable_dump_debug_info

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/debug/lib/dumping_callback.py">View source</a>



Enable dumping debugging information from a TensorFlow program.

``` python
tf.debugging.experimental.enable_dump_debug_info(
    dump_root,
    tensor_debug_mode=DEFAULT_TENSOR_DEBUG_MODE,
    circular_buffer_size=1000,
    op_regex=None,
    tensor_dtypes=None
)
```



<!-- Placeholder for "Used in" -->

The debugging information is dumped to a directory on the file system
specified as `dump_root`.

The dumped debugging information can be ingested by debugger UIs.

The files in the dump directory contain the following information:
  - TensorFlow Function construction (e.g., compilation of Python functions
    decorated with @tf.function), the op types, names (if available), context,
    the input and output tensors, and the associated stack traces.
  - Execution of TensorFlow operations (ops) and Functions and their stack
    traces, op types, names (if available) and contexts. In addition,
    depending on the value of the `tensor_debug_mode` argument (see Args
    section below), the value(s) of the output tensors or more concise
    summaries of the tensor values will be dumped.
  - A snapshot of Python source files involved in the execution of the
    TensorFlow program.

Once enabled, the dumping can be disabled with the corresponding
`disable_dump_debug_info()` method under the same Python namespace.
Calling this method more than once with the same `dump_root` is idempotent.
Calling this method more than once with different `tensor_debug_mode`s
leads to a `ValueError`.
Calling this method more than once with different `circular_buffer_size`s
leads to a `ValueError`.
Calling this method with a different `dump_root` abolishes the
previously-enabled `dump_root`.

#### Usage example:



```py
tf.debugging.experimental.enable_dump_debug_info('/tmp/my-tfdbg-dumps')

# Code to build, train and run your TensorFlow model...
```

#### Args:


* <b>`dump_root`</b>: The directory path where the dumping information will be written.
* <b>`tensor_debug_mode`</b>: Debug mode for tensor values, as a string.
  The currently supported options are:
    - "NO_TENSOR": (Default) Only traces the execution of ops' output
      tensors, while not dumping the value of the ops' output tensors
      or any form of concise summary of them.
* <b>`circular_buffer_size`</b>: Size of the circular buffers for execution events.
  These circular buffers are designed to reduce the overhead of debugging
  dumping. They hold the most recent debug events concerning eager execution
  of ops and <a href="../../../tf/function.md"><code>tf.function</code></a>s and traces of tensor values computed inside
  <a href="../../../tf/function.md"><code>tf.function</code></a>s. They are written to the file system only when the proper
  flushing method is called (see description of return values below).
  Expected to be an integer. If <= 0, the circular-buffer behavior will be
  disabled, i.e., the execution debug events will be written to the file
  writers in the same way as non-execution events such as op creations and
  source-file snapshots.
* <b>`op_regex`</b>: Dump data from only the tensors from op types that matches to the
  regular expression (through Python's `re.match()`).
  "Op type" refers to the names of the TensorFlow operations (e.g.,
  "MatMul", "LogSoftmax"), which may repeat in a TensorFlow
  function. It does *not* refer to the names of nodes (e.g.,
  "dense/MatMul", "dense_1/MatMul_1") which are unique within a function.
  - Example 1: Dump tensor data from only MatMul and Relu ops
    `op_regex="^(MatMul|Relu)$"`.
  - Example 2: Dump tensors from all ops *except* Relu:
    `op_regex="(?!^Relu$)"`.
  This filter operates in a logical AND relation with `tensor_dtypes`.
* <b>`tensor_dtypes`</b>: Dump data from only the tensors of which the specified
  dtypes. This optional argument can be in any of the following format:
  - a list or tuple of `DType` objects or strings that can be converted
    to `DType` objects via <a href="../../../tf/dtypes/as_dtype.md"><code>tf.as_dtype()</code></a>. Examples:
    - `tensor_dtype=[tf.float32, tf.float64]`,
    - `tensor_dtype=["float32", "float64"]`,
    - `tensor_dtypes=(tf.int32, tf.bool)`,
    - `tensor_dtypes=("int32", "bool")`
  - a callable that takes a single `DType` argument and returns a Python
    `boolean` indicating whether the dtype is to be included in the data
    dumping. Examples:
    - `tensor_dtype=lambda dtype: dtype.is_integer`.
  This filter operates in a logical AND relation with `op_regex`.

#### Returns:

A DebugEventsWriter instance used by the dumping callback. The caller
may use its flushing methods, including `FlushNonExecutionFiles()` and
`FlushExecutionFiles()`.


## Compat aliases

* `tf.compat.v1.debugging.experimental.enable_dump_debug_info`
* `tf.compat.v2.debugging.experimental.enable_dump_debug_info`

