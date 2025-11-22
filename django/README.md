# Django Template Theme for ParsOps

This folder contains the ParsOps homepage converted to Django template format.

## Structure

```
django/
├── templates/
│   └── index.html          # Main Django template with {% load static %} tags
└── static/
    ├── css/
    │   └── styles.css      # All CSS styles
    └── js/
        └── script.js       # All JavaScript functionality
```

## Usage in Django Project

### 1. Add to your Django settings.py:

```python
TEMPLATES = [
    {
        'BACKEND': 'django.template.backends.django.DjangoTemplates',
        'DIRS': [BASE_DIR / 'path/to/django/templates'],
        'APP_DIRS': True,
        'OPTIONS': {
            'context_processors': [
                'django.template.context_processors.debug',
                'django.template.context_processors.request',
                'django.contrib.auth.context_processors.auth',
                'django.contrib.messages.context_processors.messages',
            ],
        },
    },
]

STATIC_URL = '/static/'
STATICFILES_DIRS = [
    BASE_DIR / 'path/to/django/static',
]
```

### 2. Create a view in views.py:

```python
from django.shortcuts import render

def index(request):
    return render(request, 'index.html')
```

### 3. Add URL pattern in urls.py:

```python
from django.urls import path
from . import views

urlpatterns = [
    path('', views.index, name='index'),
]
```

## Features

- ✅ Django template tags (`{% load static %}`, `{% static 'path' %}`)
- ✅ Bootstrap 5 integration
- ✅ Bootstrap Icons
- ✅ Responsive design
- ✅ Scroll animations
- ✅ Testimonial slider
- ✅ Modern DevOps-themed design

## Note

The template uses CDN for Bootstrap 5 and Bootstrap Icons, so no additional installations are needed.
