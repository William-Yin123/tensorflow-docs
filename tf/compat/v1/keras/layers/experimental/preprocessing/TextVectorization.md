<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.keras.layers.experimental.preprocessing.TextVectorization" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="adapt"/>
<meta itemprop="property" content="get_vocabulary"/>
<meta itemprop="property" content="set_vocabulary"/>
</div>

# tf.compat.v1.keras.layers.experimental.preprocessing.TextVectorization

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/layers/preprocessing/text_vectorization_v1.py">View source</a>



## Class `TextVectorization`

Text vectorization layer.

Inherits From: [`TextVectorization`](../../../../../../../tf/keras/layers/experimental/preprocessing/TextVectorization.md)

<!-- Placeholder for "Used in" -->

This layer has basic options for managing text in a Keras model. It
transforms a batch of strings (one sample = one string) into either a list of
token indices (one sample = 1D tensor of integer token indices) or a dense
representation (one sample = 1D tensor of float values representing data about
the sample's tokens).

The processing of each sample contains the following steps:
  1) standardize each sample (usually lowercasing + punctuation stripping)
  2) split each sample into substrings (usually words)
  3) recombine substrings into tokens (usually ngrams)
  4) index tokens (associate a unique int value with each token)
  5) transform each sample using this index, either into a vector of ints or
     a dense float vector.

#### Attributes:


* <b>`max_tokens`</b>: The maximum size of the vocabulary for this layer. If None,
  there is no cap on the size of the vocabulary.
* <b>`standardize`</b>: Optional specification for standardization to apply to the
  input text. Values can be None (no standardization),
  LOWER_AND_STRIP_PUNCTUATION (lowercase and remove punctuation) or a
  Callable.
* <b>`split`</b>: Optional specification for splitting the input text. Values can be
  None (no splitting), SPLIT_ON_WHITESPACE (split on ASCII whitespace), or a
  Callable.
* <b>`ngrams`</b>: Optional specification for ngrams to create from the possibly-split
  input text. Values can be None, an integer or tuple of integers; passing
  an integer will create ngrams up to that integer, and passing a tuple of
  integers will create ngrams for the specified values in the tuple. Passing
  None means that no ngrams will be created.
* <b>`output_mode`</b>: Optional specification for the output of the layer. Values can
  be INT, BINARY, COUNT or TFIDF, which control the outputs as follows:
    INT: Outputs integer indices, one integer index per split string token.
    BINARY: Outputs a single int array per batch, of either vocab_size or
      max_tokens size, containing 1s in all elements where the token mapped
      to that index exists at least once in the batch item.
    COUNT: As BINARY, but the int array contains a count of the number of
      times the token at that index appeared in the batch item.
    TFIDF: As BINARY, but the TF-IDF algorithm is applied to find the value
      in each token slot.
* <b>`output_sequence_length`</b>: Optional length for the output tensor. If set,
  the output will be padded or truncated to this value in INT mode.
* <b>`pad_to_max_tokens`</b>: If True, BINARY, COUNT, and TFIDF modes will have their
  outputs padded to max_tokens, even if the number of unique tokens in the
  vocabulary is less than max_tokens.

<h2 id="__init__"><code>__init__</code></h2>

<a target="_blank" href="/code/stable/tensorflow/python/keras/layers/preprocessing/text_vectorization.py">View source</a>

``` python
__init__(
    max_tokens=None,
    standardize=LOWER_AND_STRIP_PUNCTUATION,
    split=SPLIT_ON_WHITESPACE,
    ngrams=None,
    output_mode=INT,
    output_sequence_length=None,
    pad_to_max_tokens=True,
    **kwargs
)
```






## Methods

<h3 id="adapt"><code>adapt</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/keras/layers/preprocessing/text_vectorization.py">View source</a>

``` python
adapt(
    data,
    reset_state=True
)
```

Fits the state of the preprocessing layer to the dataset.

Overrides the default adapt method to apply relevant preprocessing to the
inputs before passing to the combiner.

#### Arguments:


* <b>`data`</b>: The data to train on. It can be passed either as a tf.data Dataset,
  or as a numpy array.
* <b>`reset_state`</b>: Optional argument specifying whether to clear the state of
  the layer at the start of the call to `adapt`. This must be True for
  this layer, which does not support repeated calls to `adapt`.

<h3 id="get_vocabulary"><code>get_vocabulary</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/keras/layers/preprocessing/text_vectorization.py">View source</a>

``` python
get_vocabulary()
```




<h3 id="set_vocabulary"><code>set_vocabulary</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/keras/layers/preprocessing/text_vectorization.py">View source</a>

``` python
set_vocabulary(
    vocab,
    df_data=None,
    oov_df_value=None,
    append=False
)
```

Sets vocabulary (and optionally document frequency) data for this layer.

This method sets the vocabulary and DF data for this layer directly, instead
of analyzing a dataset through 'adapt'. It should be used whenever the vocab
(and optionally document frequency) information is already known. If
vocabulary data is already present in the layer, this method will either
replace it, if 'append' is set to False, or append to it (if 'append' is set
to True).

#### Arguments:


* <b>`vocab`</b>: An array of string tokens.
* <b>`df_data`</b>: An array of document frequency data. Only necessary if the layer
  output_mode is TFIDF.
* <b>`oov_df_value`</b>: The document frequency of the OOV token. Only necessary if
  output_mode is TFIDF. OOV data is optional when appending additional
  data in TFIDF mode; if an OOV value is supplied it will overwrite the
  existing OOV value.
* <b>`append`</b>: Whether to overwrite or append any existing vocabulary data.


#### Raises:


* <b>`ValueError`</b>: If there are too many inputs, the inputs do not match, or
  input data is missing.





