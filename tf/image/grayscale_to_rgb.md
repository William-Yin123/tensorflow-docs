<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.image.grayscale_to_rgb" />
<meta itemprop="path" content="Stable" />
</div>

# tf.image.grayscale_to_rgb

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/image_ops_impl.py">View source</a>



Converts one or more images from Grayscale to RGB.

``` python
tf.image.grayscale_to_rgb(
    images,
    name=None
)
```



<!-- Placeholder for "Used in" -->

Outputs a tensor of the same `DType` and rank as `images`.  The size of the
last dimension of the output is 3, containing the RGB value of the pixels.
The input images' last dimension must be size 1.

```python
>>> original = tf.constant([[[1.0], [2.0], [3.0]]])
>>> converted = tf.image.grayscale_to_rgb(original)
>>> print(converted.numpy())
[[[1. 1. 1.]
  [2. 2. 2.]
  [3. 3. 3.]]]

```

#### Args:


* <b>`images`</b>: The Grayscale tensor to convert. The last dimension must be size 1.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

The converted grayscale image(s).


## Compat aliases

* `tf.compat.v1.image.grayscale_to_rgb`
* `tf.compat.v2.image.grayscale_to_rgb`

