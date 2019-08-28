---
layout: classic-docs
title: Installing Airbrake in a Django app
short-title: Django
language: django
categories: [installing-airbrake]
description: installing airbrake in a Django app
---

![python flag](/docs/assets/img/docs/python_flag.jpeg)

## Features
* Simple to install and configure
* Automatically report exceptions from your django app
* Compatible with [Airbrake on-premise](https://airbrake.io/enterprise)

## Installation

Our [Python library
pybrake](https://github.com/airbrake/pybrake#django-integration) requires
Python 3.4+. If you are using an earlier version, please check out
[airbrake-django](https://github.com/airbrake/airbrake-django).

```sh
pip install -U pybrake
```

## Django integration
First you need to add your pybrake config to your Django `settings.py` file
using your project's `id` and `api_key`.

```python
AIRBRAKE = dict(
    project_id=123,
    project_key='FIXME',
)
```

The next step is activating the Airbrake middleware.

```python
MIDDLEWARE = [
    ...
    'pybrake.django.AirbrakeMiddleware',
]
```

The last step is configuring the airbrake logging handler. After that you are
ready to start reporting errors to Airbrake from your Django app.

```python
LOGGING = {
    'version': 1,
    'disable_existing_loggers': False,
    'handlers': {
        'airbrake': {
            'level': 'ERROR',
            'class': 'pybrake.LoggingHandler',
        },
    },
    'loggers': {
        'app': {
            'handlers': ['airbrake'],
            'level': 'ERROR',
            'propagate': True,
        },
    },
}
```


## Going further

Please visit our [official GitHub
repo](https://github.com/airbrake/pybrake#django-integration) for details on
useful features like:
* [Adding custom params to
  errors](https://github.com/airbrake/pybrake#adding-custom-params)
* [Filtering errors](https://github.com/airbrake/pybrake#filtering-keys)
