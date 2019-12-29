<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.train.do_quantize_training_on_graphdef" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.train.do_quantize_training_on_graphdef

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/training/quantize_training.py">View source</a>



A general quantization scheme is being developed in `tf.contrib.quantize`. (deprecated)

``` python
tf.compat.v1.train.do_quantize_training_on_graphdef(
    input_graph,
    num_bits
)
```



<!-- Placeholder for "Used in" -->

Warning: THIS FUNCTION IS DEPRECATED. It will be removed in a future version.
Instructions for updating:
GraphDef quantized training rewriter is deprecated in the long term.

Consider using that instead, though since it is in the tf.contrib namespace,
it is not subject to backward compatibility guarantees.

#### Args:


* <b>`input_graph`</b>: A `GraphDef`.
* <b>`num_bits`</b>: The number of bits for quantize training.


#### Returns:

The graph with quantize training done.


