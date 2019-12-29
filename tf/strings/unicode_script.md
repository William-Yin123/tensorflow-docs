<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.strings.unicode_script" />
<meta itemprop="path" content="Stable" />
</div>

# tf.strings.unicode_script

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>



Determine the script codes of a given tensor of Unicode integer code points.

``` python
tf.strings.unicode_script(
    input,
    name=None
)
```



<!-- Placeholder for "Used in" -->

This operation converts Unicode code points to script codes corresponding to
each code point. Script codes correspond to International Components for
Unicode (ICU) UScriptCode values. See http://icu-project.org/apiref/icu4c/uscript_8h.html.
Returns -1 (USCRIPT_INVALID_CODE) for invalid codepoints. Output shape will
match input shape.

#### Examples:


>>> tf.strings.unicode_script([1, 31, 38])
<tf.Tensor: id=357, shape=(3,), dtype=int32, numpy=array([0, 0, 0])>

#### Args:


* <b>`input`</b>: A `Tensor` of type `int32`. A Tensor of int32 Unicode code points.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` of type `int32`.


## Compat aliases

* `tf.compat.v1.strings.unicode_script`
* `tf.compat.v2.strings.unicode_script`

