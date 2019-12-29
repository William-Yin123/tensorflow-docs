<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.applications.imagenet_utils.preprocess_input" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.applications.imagenet_utils.preprocess_input

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/applications/imagenet_utils.py">View source</a>



Preprocesses a tensor or Numpy array encoding a batch of images.

``` python
tf.keras.applications.imagenet_utils.preprocess_input(
    x,
    data_format=None,
    mode='caffe'
)
```



<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`x`</b>: Input Numpy or symbolic tensor, 3D or 4D.
  The preprocessed data is written over the input data
  if the data types are compatible. To avoid this
  behaviour, `numpy.copy(x)` can be used.
* <b>`data_format`</b>: Data format of the image tensor/array.
* <b>`mode`</b>: One of "caffe", "tf" or "torch".
  - caffe: will convert the images from RGB to BGR,
      then will zero-center each color channel with
      respect to the ImageNet dataset,
      without scaling.
  - tf: will scale pixels between -1 and 1,
      sample-wise.
  - torch: will scale pixels between 0 and 1 and then
      will normalize each channel with respect to the
      ImageNet dataset.


#### Returns:

Preprocessed tensor or Numpy array.



#### Raises:


* <b>`ValueError`</b>: In case of unknown `data_format` argument.

## Compat aliases

* `tf.compat.v1.keras.applications.imagenet_utils.preprocess_input`
* `tf.compat.v2.keras.applications.imagenet_utils.preprocess_input`

