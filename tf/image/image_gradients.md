<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.image.image_gradients" />
<meta itemprop="path" content="Stable" />
</div>

# tf.image.image_gradients

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/image_ops_impl.py">View source</a>



Returns image gradients (dy, dx) for each color channel.

``` python
tf.image.image_gradients(image)
```



<!-- Placeholder for "Used in" -->

Both output tensors have the same shape as the input: [batch_size, h, w,
d]. The gradient values are organized so that [I(x+1, y) - I(x, y)] is in
location (x, y). That means that dy will always have zeros in the last row,
and dx will always have zeros in the last column.

#### Arguments:


* <b>`image`</b>: Tensor with shape [batch_size, h, w, d].


#### Returns:

Pair of tensors (dy, dx) holding the vertical and horizontal image
gradients (1-step finite difference).



#### Usage Example:

```python
BATCH_SIZE = 1
IMAGE_HEIGHT = 5
IMAGE_WIDTH = 5
CHANNELS = 1
image = tf.reshape(tf.range(IMAGE_HEIGHT * IMAGE_WIDTH * CHANNELS,
  delta=1, dtype=tf.float32),
  shape=(BATCH_SIZE, IMAGE_HEIGHT, IMAGE_WIDTH, CHANNELS))
dx, dy = tf.image.image_gradients(image)
print(image[0, :,:,0])
tf.Tensor(
  [[ 0.  1.  2.  3.  4.]
  [ 5.  6.  7.  8.  9.]
  [10. 11. 12. 13. 14.]
  [15. 16. 17. 18. 19.]
  [20. 21. 22. 23. 24.]], shape=(5, 5), dtype=float32)
print(dx[0, :,:,0])
tf.Tensor(
  [[5. 5. 5. 5. 5.]
  [5. 5. 5. 5. 5.]
  [5. 5. 5. 5. 5.]
  [5. 5. 5. 5. 5.]
  [0. 0. 0. 0. 0.]], shape=(5, 5), dtype=float32)
print(dy[0, :,:,0])
tf.Tensor(
  [[1. 1. 1. 1. 0.]
  [1. 1. 1. 1. 0.]
  [1. 1. 1. 1. 0.]
  [1. 1. 1. 1. 0.]
  [1. 1. 1. 1. 0.]], shape=(5, 5), dtype=float32)
```



#### Raises:


* <b>`ValueError`</b>: If `image` is not a 4D tensor.

## Compat aliases

* `tf.compat.v1.image.image_gradients`
* `tf.compat.v2.image.image_gradients`

