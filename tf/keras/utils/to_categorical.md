<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.utils.to_categorical" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.utils.to_categorical

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/utils/np_utils.py">View source</a>



Converts a class vector (integers) to binary class matrix.

``` python
tf.keras.utils.to_categorical(
    y,
    num_classes=None,
    dtype='float32'
)
```



<!-- Placeholder for "Used in" -->

E.g. for use with categorical_crossentropy.

#### Arguments:


* <b>`y`</b>: class vector to be converted into a matrix
    (integers from 0 to num_classes).
* <b>`num_classes`</b>: total number of classes.
* <b>`dtype`</b>: The data type expected by the input. Default: `'float32'`.


#### Returns:

A binary matrix representation of the input. The classes axis is placed
last.


## Compat aliases

* `tf.compat.v1.keras.utils.to_categorical`
* `tf.compat.v2.keras.utils.to_categorical`

