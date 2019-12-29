<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.image.rot90" />
<meta itemprop="path" content="Stable" />
</div>

# tf.image.rot90

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/image_ops_impl.py">View source</a>



Rotate image(s) counter-clockwise by 90 degrees.

``` python
tf.image.rot90(
    image,
    k=1,
    name=None
)
```



<!-- Placeholder for "Used in" -->


#### For example:


```python
a=tf.constant([[[1],[2]],[[3],[4]]])
# rotating `a` counter clockwise by 90 degrees
a_rot=tf.image.rot90(a,k=1) #rotated `a`
print(a_rot) # [[[2],[4]],[[1],[3]]]
```
Args:
  image: 4-D Tensor of shape `[batch, height, width, channels]` or 3-D Tensor
    of shape `[height, width, channels]`.
  k: A scalar integer. The number of times the image is rotated by 90 degrees.
  name: A name for this operation (optional).

#### Returns:

A rotated tensor of the same type and shape as `image`.



#### Raises:


* <b>`ValueError`</b>: if the shape of `image` not supported.

## Compat aliases

* `tf.compat.v1.image.rot90`
* `tf.compat.v2.image.rot90`

