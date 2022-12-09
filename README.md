# drf

## django rest framework

```bash
django-admin startproject drf .
django-admin startapp egapp

python3 manage.py migrate
python3 manage.py createsuperuser --email admin@email.123 --username admin

python3 manage.py runserver
http -a admin:password123 http://127.0.0.1:8000/users/
```

## serializers

ModelSerializers are similar to ModelForms,
but are not constrained to HTML-output/form-input.

Marshalls model instances and Python primitives, then parsers/renderers
marshal Python primitives and request/response content.

## hyperlinked model serializers

Uses hyperlinked relationships instead of primary key relationships.

Uses a 'url' field instead of the 'id' field.

## viewsets

Uses list(), retrieve(), create(), etc. instead of get(), post(), etc.

```python
user_list = UserViewSet.as_view({'get': 'list'})
user_detail = UserViewSet.as_view({'get': 'retrieve'})
```

Register the viewset with a router to auto-determine the URL conf.

```python
router = DefaultRouter() router.register(r'users', UserViewSet, 'user') urlpatterns = router.urls
```
