<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.image.random_brightness" />
<meta itemprop="path" content="Stable" />
</div>

# tf.image.random_brightness

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/image_ops_impl.py">View source</a>



Adjust the brightness of images by a random factor.

``` python
tf.image.random_brightness(
    image,
    max_delta,
    seed=None
)
```



<!-- Placeholder for "Used in" -->

Equivalent to `adjust_brightness()` using a `delta` randomly picked in the
interval `[-max_delta, max_delta)`.

#### Args:


* <b>`image`</b>: An image or images to adjust.
* <b>`max_delta`</b>: float, must be non-negative.
* <b>`seed`</b>: A Python integer. Used to create a random seed. See
  <a href="../../tf/compat/v1/set_random_seed.md"><code>tf.compat.v1.set_random_seed</code></a> for behavior.


#### Returns:

The brightness-adjusted image(s).



#### Raises:


* <b>`ValueError`</b>: if `max_delta` is negative.

## Compat aliases

* `tf.compat.v1.image.random_brightness`
* `tf.compat.v2.image.random_brightness`

