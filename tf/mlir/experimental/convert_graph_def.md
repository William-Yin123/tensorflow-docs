<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.mlir.experimental.convert_graph_def" />
<meta itemprop="path" content="Stable" />
</div>

# tf.mlir.experimental.convert_graph_def

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/compiler/mlir/mlir.py">View source</a>



Import a GraphDef and convert it to a textual MLIR module.

``` python
tf.mlir.experimental.convert_graph_def(
    graph_def,
    pass_pipeline='tf-standard-pipeline'
)
```



<!-- Placeholder for "Used in" -->


#### Args:


* <b>`graph_def`</b>: An object of type graph_pb2.GraphDef or a textual proto
  representation of a valid GraphDef.
* <b>`pass_pipeline`</b>: A textual description of an MLIR Pass Pipeline to run on the
  module, see MLIR documentation for the
  [textual pass pipeline syntax](https://github.com/tensorflow/mlir/blob/master/g3doc/WritingAPass.md#textual-pass-pipeline-specification).


#### Returns:

A textual representation of the MLIR module corresponding to the graphdef.
Raises a RuntimeError on error.


## Compat aliases

* `tf.compat.v1.mlir.experimental.convert_graph_def`
* `tf.compat.v2.mlir.experimental.convert_graph_def`

