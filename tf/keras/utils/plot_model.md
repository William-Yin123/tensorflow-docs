<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.utils.plot_model" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.utils.plot_model

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/utils/vis_utils.py">View source</a>



Converts a Keras model to dot format and save to a file.

``` python
tf.keras.utils.plot_model(
    model,
    to_file='model.png',
    show_shapes=False,
    show_layer_names=True,
    rankdir='TB',
    expand_nested=False,
    dpi=96
)
```



<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`model`</b>: A Keras model instance
* <b>`to_file`</b>: File name of the plot image.
* <b>`show_shapes`</b>: whether to display shape information.
* <b>`show_layer_names`</b>: whether to display layer names.
* <b>`rankdir`</b>: `rankdir` argument passed to PyDot,
    a string specifying the format of the plot:
    'TB' creates a vertical plot;
    'LR' creates a horizontal plot.
* <b>`expand_nested`</b>: Whether to expand nested models into clusters.
* <b>`dpi`</b>: Dots per inch.


#### Returns:

A Jupyter notebook Image object if Jupyter is installed.
This enables in-line display of the model plots in notebooks.


## Compat aliases

* `tf.compat.v1.keras.utils.plot_model`
* `tf.compat.v2.keras.utils.plot_model`

