<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.signal.frame" />
<meta itemprop="path" content="Stable" />
</div>

# tf.signal.frame

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/signal/shape_ops.py">View source</a>



Expands `signal`'s `axis` dimension into frames of `frame_length`.

``` python
tf.signal.frame(
    signal,
    frame_length,
    frame_step,
    pad_end=False,
    pad_value=0,
    axis=-1,
    name=None
)
```



<!-- Placeholder for "Used in" -->

Slides a window of size `frame_length` over `signal`'s `axis` dimension
with a stride of `frame_step`, replacing the `axis` dimension with
`[frames, frame_length]` frames.

If `pad_end` is True, window positions that are past the end of the `axis`
dimension are padded with `pad_value` until the window moves fully past the
end of the dimension. Otherwise, only window positions that fully overlap the
`axis` dimension are produced.

#### For example:



```python
# A batch size 3 tensor of 9152 audio samples.
audio = tf.random.normal([3, 9152])

# Compute overlapping frames of length 512 with a step of 180 (frames overlap
# by 332 samples). By default, only 50 frames are generated since the last
# 152 samples do not form a full frame.
frames = tf.signal.frame(audio, 512, 180)
frames.shape.assert_is_compatible_with([3, 50, 512])

# When pad_end is enabled, the final frame is kept (padded with zeros).
frames = tf.signal.frame(audio, 512, 180, pad_end=True)
frames.shape.assert_is_compatible_with([3, 51, 512])
```

#### Args:


* <b>`signal`</b>: A `[..., samples, ...]` `Tensor`. The rank and dimensions
  may be unknown. Rank must be at least 1.
* <b>`frame_length`</b>: The frame length in samples. An integer or scalar `Tensor`.
* <b>`frame_step`</b>: The frame hop size in samples. An integer or scalar `Tensor`.
* <b>`pad_end`</b>: Whether to pad the end of `signal` with `pad_value`.
* <b>`pad_value`</b>: An optional scalar `Tensor` to use where the input signal
  does not exist when `pad_end` is True.
* <b>`axis`</b>: A scalar integer `Tensor` indicating the axis to frame. Defaults to
  the last axis. Supports negative values for indexing from the end.
* <b>`name`</b>: An optional name for the operation.


#### Returns:

A `Tensor` of frames with shape `[..., frames, frame_length, ...]`.



#### Raises:


* <b>`ValueError`</b>: If `frame_length`, `frame_step`, `pad_value`, or `axis` are not
  scalar.

## Compat aliases

* `tf.compat.v1.signal.frame`
* `tf.compat.v2.signal.frame`

