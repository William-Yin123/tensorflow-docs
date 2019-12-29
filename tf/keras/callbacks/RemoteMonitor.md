<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.callbacks.RemoteMonitor" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="set_model"/>
<meta itemprop="property" content="set_params"/>
</div>

# tf.keras.callbacks.RemoteMonitor

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/callbacks.py">View source</a>



## Class `RemoteMonitor`

Callback used to stream events to a server.

Inherits From: [`Callback`](../../../tf/keras/callbacks/Callback.md)

<!-- Placeholder for "Used in" -->

Requires the `requests` library.
Events are sent to `root + '/publish/epoch/end/'` by default. Calls are
HTTP POST, with a `data` argument which is a
JSON-encoded dictionary of event data.
If send_as_json is set to True, the content type of the request will be
application/json. Otherwise the serialized JSON will be sent within a form.

#### Arguments:


* <b>`root`</b>: String; root url of the target server.
* <b>`path`</b>: String; path relative to `root` to which the events will be sent.
* <b>`field`</b>: String; JSON field under which the data will be stored.
    The field is used only if the payload is sent within a form
    (i.e. send_as_json is set to False).
* <b>`headers`</b>: Dictionary; optional custom HTTP headers.
* <b>`send_as_json`</b>: Boolean; whether the request should be
    sent as application/json.

<h2 id="__init__"><code>__init__</code></h2>

<a target="_blank" href="/code/stable/tensorflow/python/keras/callbacks.py">View source</a>

``` python
__init__(
    root='http://localhost:9000',
    path='/publish/epoch/end/',
    field='data',
    headers=None,
    send_as_json=False
)
```

Initialize self.  See help(type(self)) for accurate signature.




## Methods

<h3 id="set_model"><code>set_model</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/keras/callbacks.py">View source</a>

``` python
set_model(model)
```




<h3 id="set_params"><code>set_params</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/keras/callbacks.py">View source</a>

``` python
set_params(params)
```








## Compat aliases

* `tf.compat.v1.keras.callbacks.RemoteMonitor`
* `tf.compat.v2.keras.callbacks.RemoteMonitor`

