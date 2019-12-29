<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.experimental.tensorrt.Converter" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="build"/>
<meta itemprop="property" content="convert"/>
<meta itemprop="property" content="save"/>
</div>

# tf.experimental.tensorrt.Converter

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/compiler/tensorrt/trt_convert.py">View source</a>



## Class `Converter`

An offline converter for TF-TRT transformation for TF 2.0 SavedModels.



<!-- Placeholder for "Used in" -->

Currently this is not available on Windows platform.

Note that in V2, is_dynamic_op=False is not supported, meaning TRT engines
will be built only when the corresponding TRTEngineOp is executed. But we
still provide a way to avoid the cost of building TRT engines during inference
(see more below).

There are several ways to run the conversion:

1. FP32/FP16 precision

   ```python
   params = DEFAULT_TRT_CONVERSION_PARAMS._replace(
       precision_mode='FP16')
   converter = tf.experimental.tensorrt.Converter(
       input_saved_model_dir="my_dir", conversion_params=params)
   converter.convert()
   converter.save(output_saved_model_dir)
   ```

   In this case, no TRT engines will be built or saved in the converted
   SavedModel. But if input data is available during conversion, we can still
   build and save the TRT engines to reduce the cost during inference (see
   option 2 below).

2. FP32/FP16 precision with pre-built engines

   ```python
   params = DEFAULT_TRT_CONVERSION_PARAMS._replace(
       precision_mode='FP16',
       # Set this to a large enough number so it can cache all the engines.
       maximum_cached_engines=16)
   converter = tf.experimental.tensorrt.Converter(
       input_saved_model_dir="my_dir", conversion_params=params)
   converter.convert()

   # Define a generator function that yields input data, and use it to execute
   # the graph to build TRT engines.
   # With TensorRT 5.1, different engines will be built (and saved later) for
   # different input shapes to the TRTEngineOp.
   def my_input_fn():
     for _ in range(num_runs):
       inp1, inp2 = ...
       yield inp1, inp2

   converter.build(input_fn=my_input_fn)  # Generate corresponding TRT engines
   converter.save(output_saved_model_dir)  # Generated engines will be saved.
   ```

   In this way, one engine will be built/saved for each unique input shapes of
   the TRTEngineOp. This is good for applications that cannot afford building
   engines during inference but have access to input data that is similar to
   the one used in production (for example, that has the same input shapes).
   Also, the generated TRT engines is platform dependent, so we need to run
   `build()` in an environment that is similar to production (e.g. with
   same type of GPU).

3. INT8 precision and calibration with pre-built engines

   ```python
   params = DEFAULT_TRT_CONVERSION_PARAMS._replace(
       precision_mode='INT8',
       # Currently only one INT8 engine is supported in this mode.
       maximum_cached_engines=1,
       use_calibration=True)
   converter = tf.experimental.tensorrt.Converter(
       input_saved_model_dir="my_dir", conversion_params=params)

   # Define a generator function that yields input data, and run INT8
   # calibration with the data. All input data should have the same shape.
   # At the end of convert(), the calibration stats (e.g. range information)
   # will be saved and can be used to generate more TRT engines with different
   # shapes. Also, one TRT engine will be generated (with the same shape as
   # the calibration data) for save later.
   def my_calibration_input_fn():
     for _ in range(num_runs):
       inp1, inp2 = ...
       yield inp1, inp2

   converter.convert(calibration_input_fn=my_calibration_input_fn)

   # (Optional) Generate more TRT engines offline (same as the previous
   # option), to avoid the cost of generating them during inference.
   def my_input_fn():
     for _ in range(num_runs):
       inp1, inp2 = ...
       yield inp1, inp2
   converter.build(input_fn=my_input_fn)

   # Save the TRT engine and the engines.
   converter.save(output_saved_model_dir)
   ```

<h2 id="__init__"><code>__init__</code></h2>

<a target="_blank" href="/code/stable/tensorflow/python/compiler/tensorrt/trt_convert.py">View source</a>

``` python
__init__(
    input_saved_model_dir=None,
    input_saved_model_tags=None,
    input_saved_model_signature_key=None,
    conversion_params=DEFAULT_TRT_CONVERSION_PARAMS
)
```

Initialize the converter.


#### Args:


* <b>`input_saved_model_dir`</b>: the directory to load the SavedModel which contains
  the input graph to transforms. Used only when input_graph_def is None.
* <b>`input_saved_model_tags`</b>: list of tags to load the SavedModel.
* <b>`input_saved_model_signature_key`</b>: the key of the signature to optimize the
  graph for.
* <b>`conversion_params`</b>: a TrtConversionParams instance.


#### Raises:


* <b>`ValueError`</b>: if the combination of the parameters is invalid.



## Methods

<h3 id="build"><code>build</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/compiler/tensorrt/trt_convert.py">View source</a>

``` python
build(input_fn)
```

Run inference with converted graph in order to build TensorRT engines.


#### Args:


* <b>`input_fn`</b>: a generator function that yields input data as a list or tuple,
  which will be used to execute the converted signature to generate TRT
  engines.
  Example: `def input_fn(): yield input1, input2, input3`

<h3 id="convert"><code>convert</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/compiler/tensorrt/trt_convert.py">View source</a>

``` python
convert(calibration_input_fn=None)
```

Convert the input SavedModel in 2.0 format.


#### Args:


* <b>`calibration_input_fn`</b>: a generator function that yields input data as a
  list or tuple, which will be used to execute the converted signature for
  calibration. All the returned input data should have the same shape.
  Example: `def input_fn(): yield input1, input2, input3`


#### Raises:


* <b>`ValueError`</b>: if the input combination is invalid.


#### Returns:

The TF-TRT converted Function.


<h3 id="save"><code>save</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/compiler/tensorrt/trt_convert.py">View source</a>

``` python
save(output_saved_model_dir)
```

Save the converted SavedModel.


#### Args:


* <b>`output_saved_model_dir`</b>: directory to saved the converted SavedModel.





## Compat aliases

* `tf.compat.v2.experimental.tensorrt.Converter`

