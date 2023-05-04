# For django projects
## _Classes and functions to create django projects with Bootstrap Css Framework_

[![N|Solid](https://devarech.me/static/images/icon/logo-devarech.svg)](https://devarech.me)

## Installation

Requires [Django](https://www.djangoproject.com/) v2.2+ and [Python](https://www.python.org/) v3.6+ to run.

Add apps in INSTALLED_APPS:

```sh
INSTALLED_APPS = [
    ...
    'for_django_projects.form_utils',
    'for_django_projects.pwa'
    ...
]
```

Add in settings.py:

```sh
SIMBOLO_MONEDA = '$'
URL_GENERAL = 'http://your_domain.com'
CONSTRAINT_MSG = {} #dict of name of constraints as key and error message as value  
```

# Classes
#### CustomValueDb
Inherited from `django.db.models.Value`, automatically adds data type in output_field attribute.

#### NormalModel
Inherited from `django.db.models.Model`, adds fields **(in all models inheriting from NormalModel)** according to the field type.
Example: If there is a field of type BooleanField with the name `is_enabled`, then the `is_enabled_boolhtml` attribute will be added with a [Fontawesome](https://fontawesome.com/search?m=free) icon named **fa-check-circle**, otherwise **fa-times-circle** is added.
######

## License

MIT

**Free Software, Hell Yeah!**
