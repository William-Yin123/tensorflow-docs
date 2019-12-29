<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.applications.imagenet_utils.decode_predictions" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.applications.imagenet_utils.decode_predictions

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/applications/imagenet_utils.py">View source</a>



Decodes the prediction of an ImageNet model.

``` python
tf.keras.applications.imagenet_utils.decode_predictions(
    preds,
    top=5
)
```



<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`preds`</b>: Numpy tensor encoding a batch of predictions.
* <b>`top`</b>: Integer, how many top-guesses to return.


#### Returns:

A list of lists of top class prediction tuples
`(class_name, class_description, score)`.
One list of tuples per sample in batch input.



#### Raises:


* <b>`ValueError`</b>: In case of invalid shape of the `pred` array
  (must be 2D).

## Compat aliases

* `tf.compat.v1.keras.applications.imagenet_utils.decode_predictions`
* `tf.compat.v2.keras.applications.imagenet_utils.decode_predictions`

