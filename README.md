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
#### _CustomValueDb_
Inherited from `django.db.models.Value`, automatically adds data type in output_field attribute.

#### _NormalModel_
Inherited from `django.db.models.Model`, adds fields **(in all models inheriting from NormalModel)** according to the field type.
Example: If there is a field of type BooleanField with the name `is_enabled`, then the `is_enabled_boolhtml` attribute will be added with a [Fontawesome](https://fontawesome.com/search?m=free) icon named **fa-check-circle**, otherwise **fa-times-circle** is added.
### Attributes to be added in objects inherited from _NormalModel_ according to field type:
#### django.db.models.BooleanField:
- `fieldname_boolhtml` ➝ [SafeString](https://docs.djangoproject.com/es/2.2/_modules/django/utils/safestring/#mark_safe): Return `<i class="fas fas fa-clock text-info"></i>` if `fieldname` value is `None`, `<i class="fas fa-check-circle text-success"></i>` if is `True` or `<i class="fas fa-times-circle text-secondary"></i>` if is `False`.
<br><br>
- `fieldname_texthtml ➝ str`: Return `HABILITADO` if `fieldname` value is `True`, else return `DESHABILITADO`.
<br><br>
- `fieldname_yesorno ➝ str`: Return `Sí` if `fieldname` value is `True`, else return `No`.

#### django.db.models.DecimalField:
- `fieldname_unlocalize ➝ str`: Returns the same value but replacing the comma `,` character with dot `.`.
<br><br>
- `fieldname_money ➝ str`: Return `fieldname_unlocalize` with `settings.SIMBOLO_MONEDA`, example `$10.50`.
<br><br>
- `fieldname_integer ➝ int`: Return the `fieldname` value rounded.

#### django.db.models.FileField:
- `fieldname_icon` ➝ [SafeString](https://docs.djangoproject.com/es/2.2/_modules/django/utils/safestring/#mark_safe): Returns [Fontawesome](https://fontawesome.com/search?m=free) icon according to file extension.
<br><br>
- `fieldname_a_tag` ➝ [SafeString](https://docs.djangoproject.com/es/2.2/_modules/django/utils/safestring/#mark_safe): Returns `<a target="_blank" href="URL">{fieldname_icon} descargar</a>`.
<br><br>
- `fieldname_is_image ➝ bool`.
<br><br>
- `fieldname_extension ➝ str`.

#### _ModeloBase_
Inherited from `NormalModel`, add new fields in model as `fecha_registro -> models.DateTimeField` and `sin_eliminar -> models.BooleanField`.

## License

MIT

**Free Software, Hell Yeah!**
