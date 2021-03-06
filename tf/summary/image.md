<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.summary.image" />
<meta itemprop="path" content="Stable" />
</div>

# tf.summary.image

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">

<td>
  <a target="_blank" href="https://github.com/tensorflow/tensorboard/tree/master/tensorboard/plugins/image/summary_v2.py">
    <img src="https://www.tensorflow.org/images/GitHub-Mark-32px.png" />
    View source on GitHub
  </a>
</td></table>



Write an image summary.

``` python
tf.summary.image(
    name,
    data,
    step=None,
    max_outputs=3,
    description=None
)
```



<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`name`</b>: A name for this summary. The summary tag used for TensorBoard will
  be this name prefixed by any active name scopes.
* <b>`data`</b>: A `Tensor` representing pixel data with shape `[k, h, w, c]`,
  where `k` is the number of images, `h` and `w` are the height and
  width of the images, and `c` is the number of channels, which
  should be 1, 2, 3, or 4 (grayscale, grayscale with alpha, RGB, RGBA).
  Any of the dimensions may be statically unknown (i.e., `None`).
  Floating point data will be clipped to the range [0,1).
* <b>`step`</b>: Explicit `int64`-castable monotonic step value for this summary. If
  omitted, this defaults to <a href="../../tf/summary/experimental/get_step.md"><code>tf.summary.experimental.get_step()</code></a>, which must
  not be None.
* <b>`max_outputs`</b>: Optional `int` or rank-0 integer `Tensor`. At most this
  many images will be emitted at each step. When more than
  `max_outputs` many images are provided, the first `max_outputs` many
  images will be used and the rest silently discarded.
* <b>`description`</b>: Optional long-form description for this summary, as a
  constant `str`. Markdown is supported. Defaults to empty.


#### Returns:

True on success, or false if no summary was emitted because no default
summary writer was available.



#### Raises:


* <b>`ValueError`</b>: if a default writer exists, but no step was provided and
  <a href="../../tf/summary/experimental/get_step.md"><code>tf.summary.experimental.get_step()</code></a> is None.

## Compat aliases

* `tf.compat.v2.summary.image`

