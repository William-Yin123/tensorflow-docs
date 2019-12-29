<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.io.write_file" />
<meta itemprop="path" content="Stable" />
</div>

# tf.io.write_file

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>



Writes contents to the file at input filename. Creates file and recursively

``` python
tf.io.write_file(
    filename,
    contents,
    name=None
)
```



<!-- Placeholder for "Used in" -->

creates directory if not existing.

#### Args:


* <b>`filename`</b>: A `Tensor` of type `string`.
  scalar. The name of the file to which we write the contents.
* <b>`contents`</b>: A `Tensor` of type `string`.
  scalar. The content to be written to the output file.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

The created Operation.


## Compat aliases

* `tf.compat.v1.io.write_file`
* `tf.compat.v1.write_file`
* `tf.compat.v2.io.write_file`

