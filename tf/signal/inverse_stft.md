<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.signal.inverse_stft" />
<meta itemprop="path" content="Stable" />
</div>

# tf.signal.inverse_stft

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/signal/spectral_ops.py">View source</a>



Computes the inverse [Short-time Fourier Transform][stft] of `stfts`.

``` python
tf.signal.inverse_stft(
    stfts,
    frame_length,
    frame_step,
    fft_length=None,
    window_fn=tf.signal.hann_window,
    name=None
)
```



<!-- Placeholder for "Used in" -->

To reconstruct an original waveform, a complementary window function should
be used with `inverse_stft`. Such a window function can be constructed with
<a href="../../tf/signal/inverse_stft_window_fn.md"><code>tf.signal.inverse_stft_window_fn</code></a>.
Example:

```python
frame_length = 400
frame_step = 160
waveform = tf.random.normal(dtype=tf.float32, shape=[1000])
stft = tf.signal.stft(waveform, frame_length, frame_step)
inverse_stft = tf.signal.inverse_stft(
    stft, frame_length, frame_step,
    window_fn=tf.signal.inverse_stft_window_fn(frame_step))
```

If a custom `window_fn` is used with <a href="../../tf/signal/stft.md"><code>tf.signal.stft</code></a>, it must be passed to
<a href="../../tf/signal/inverse_stft_window_fn.md"><code>tf.signal.inverse_stft_window_fn</code></a>:

```python
frame_length = 400
frame_step = 160
window_fn = tf.signal.hamming_window
waveform = tf.random.normal(dtype=tf.float32, shape=[1000])
stft = tf.signal.stft(
    waveform, frame_length, frame_step, window_fn=window_fn)
inverse_stft = tf.signal.inverse_stft(
    stft, frame_length, frame_step,
    window_fn=tf.signal.inverse_stft_window_fn(
       frame_step, forward_window_fn=window_fn))
```

Implemented with TPU/GPU-compatible ops and supports gradients.

#### Args:


* <b>`stfts`</b>: A `complex64`/`complex128` `[..., frames, fft_unique_bins]`
  `Tensor` of STFT bins representing a batch of `fft_length`-point STFTs
  where `fft_unique_bins` is `fft_length // 2 + 1`
* <b>`frame_length`</b>: An integer scalar `Tensor`. The window length in samples.
* <b>`frame_step`</b>: An integer scalar `Tensor`. The number of samples to step.
* <b>`fft_length`</b>: An integer scalar `Tensor`. The size of the FFT that produced
  `stfts`. If not provided, uses the smallest power of 2 enclosing
  `frame_length`.
* <b>`window_fn`</b>: A callable that takes a window length and a `dtype` keyword
  argument and returns a `[window_length]` `Tensor` of samples in the
  provided datatype. If set to `None`, no windowing is used.
* <b>`name`</b>: An optional name for the operation.


#### Returns:

A `[..., samples]` `Tensor` of `float32`/`float64` signals representing
the inverse STFT for each input STFT in `stfts`.



#### Raises:


* <b>`ValueError`</b>: If `stfts` is not at least rank 2, `frame_length` is not scalar,
  `frame_step` is not scalar, or `fft_length` is not scalar.

[stft]: https://en.wikipedia.org/wiki/Short-time_Fourier_transform

## Compat aliases

* `tf.compat.v1.signal.inverse_stft`
* `tf.compat.v2.signal.inverse_stft`

