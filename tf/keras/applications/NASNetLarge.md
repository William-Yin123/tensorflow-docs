<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.applications.NASNetLarge" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.applications.NASNetLarge

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/applications/nasnet.py">View source</a>



Instantiates a NASNet model in ImageNet mode.

**Aliases**: `tf.keras.applications.nasnet.NASNetLarge`

``` python
tf.keras.applications.NASNetLarge(
    input_shape=None,
    include_top=True,
    weights='imagenet',
    input_tensor=None,
    pooling=None,
    classes=1000
)
```



<!-- Placeholder for "Used in" -->

Optionally loads weights pre-trained on ImageNet.
Note that the data format convention used by the model is
the one specified in your Keras config at `~/.keras/keras.json`.

#### Arguments:


* <b>`input_shape`</b>: Optional shape tuple, only to be specified
    if `include_top` is False (otherwise the input shape
    has to be `(331, 331, 3)` for NASNetLarge.
    It should have exactly 3 inputs channels,
    and width and height should be no smaller than 32.
    E.g. `(224, 224, 3)` would be one valid value.
* <b>`include_top`</b>: Whether to include the fully-connected
    layer at the top of the network.
* <b>`weights`</b>: `None` (random initialization) or
    `imagenet` (ImageNet weights)
* <b>`input_tensor`</b>: Optional Keras tensor (i.e. output of
    <a href="../../../tf/keras/Input.md"><code>layers.Input()</code></a>)
    to use as image input for the model.
* <b>`pooling`</b>: Optional pooling mode for feature extraction
    when `include_top` is `False`.
    - `None` means that the output of the model
        will be the 4D tensor output of the
        last convolutional layer.
    - `avg` means that global average pooling
        will be applied to the output of the
        last convolutional layer, and thus
        the output of the model will be a
        2D tensor.
    - `max` means that global max pooling will
        be applied.
* <b>`classes`</b>: Optional number of classes to classify images
    into, only to be specified if `include_top` is True, and
    if no `weights` argument is specified.


#### Returns:

A Keras model instance.



#### Raises:


* <b>`ValueError`</b>: in case of invalid argument for `weights`,
    or invalid input shape.
* <b>`RuntimeError`</b>: If attempting to run this model with a
    backend that does not support separable convolutions.

## Compat aliases

* `tf.compat.v1.keras.applications.NASNetLarge`
* `tf.compat.v1.keras.applications.nasnet.NASNetLarge`
* `tf.compat.v2.keras.applications.NASNetLarge`
* `tf.compat.v2.keras.applications.nasnet.NASNetLarge`

