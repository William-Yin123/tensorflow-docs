<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.image.random_flip_left_right" />
<meta itemprop="path" content="Stable" />
</div>

# tf.image.random_flip_left_right

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/image_ops_impl.py">View source</a>



Randomly flip an image horizontally (left to right).

``` python
tf.image.random_flip_left_right(
    image,
    seed=None
)
```



<!-- Placeholder for "Used in" -->

With a 1 in 2 chance, outputs the contents of `image` flipped along the
second dimension, which is `width`.  Otherwise output the image as-is.
When passing a batch of images, each image will be randomly flipped
independent of other images.

#### Example usage:

Randomly flip a single image.
>>> import numpy as np

```
>>> image = np.array([[[1], [2]], [[3], [4]]])
>>> tf.image.random_flip_left_right(image, 5).numpy().tolist()
[[[2], [1]], [[4], [3]]]
```

Randomly flip multiple images.
>>> images = np.array(
... [
...     [[[1], [2]], [[3], [4]]],
...     [[[5], [6]], [[7], [8]]]
... ])
>>> tf.image.random_flip_left_right(images, 6).numpy().tolist()
[[[[2], [1]], [[4], [3]]], [[[5], [6]], [[7], [8]]]]



#### Args:


* <b>`image`</b>: 4-D Tensor of shape `[batch, height, width, channels]` or 3-D Tensor
  of shape `[height, width, channels]`.
* <b>`seed`</b>: A Python integer. Used to create a random seed. See
  <a href="../../tf/compat/v1/set_random_seed.md"><code>tf.compat.v1.set_random_seed</code></a> for behavior.


#### Returns:

A tensor of the same type and shape as `image`.



#### Raises:


* <b>`ValueError`</b>: if the shape of `image` not supported.

## Compat aliases

* `tf.compat.v1.image.random_flip_left_right`
* `tf.compat.v2.image.random_flip_left_right`

