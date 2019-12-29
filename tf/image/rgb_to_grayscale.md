<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.image.rgb_to_grayscale" />
<meta itemprop="path" content="Stable" />
</div>

# tf.image.rgb_to_grayscale

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/image_ops_impl.py">View source</a>



Converts one or more images from RGB to Grayscale.

``` python
tf.image.rgb_to_grayscale(
    images,
    name=None
)
```



<!-- Placeholder for "Used in" -->

Outputs a tensor of the same `DType` and rank as `images`.  The size of the
last dimension of the output is 1, containing the Grayscale value of the
pixels.

```python
>>> original = tf.constant([[[1.0, 2.0, 3.0]]])
>>> converted = tf.image.rgb_to_grayscale(original)
>>> print(converted.numpy())
[[[1.81...]]]

```

#### Args:


* <b>`images`</b>: The RGB tensor to convert. The last dimension must have size 3 and
  should contain RGB values.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

The converted grayscale image(s).


## Compat aliases

* `tf.compat.v1.image.rgb_to_grayscale`
* `tf.compat.v2.image.rgb_to_grayscale`

