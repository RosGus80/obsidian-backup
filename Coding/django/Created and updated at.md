
Any field with the [`auto_now`](https://docs.djangoproject.com/en/2.2/ref/models/fields/#django.db.models.DateField.auto_now) attribute set will also inherit `editable=False` and therefore will not show up in the admin panel. There has been talk in the past about making the `auto_now` and [`auto_now_add`](https://docs.djangoproject.com/en/2.2/ref/models/fields/#django.db.models.DateField.auto_now_add) arguments go away, and although they still exist, I feel you're better off just using a [custom `save()` method](https://docs.djangoproject.com/en/2.2/topics/db/models/#overriding-model-methods).

So, to make this work properly, I would recommend not using `auto_now` or `auto_now_add` and instead define your own `save()` method to make sure that `created` is only updated if `id` is not set (such as when the item is first created), and have it update `modified` every time the item is saved.

I have done the exact same thing with other projects I have written using Django, and so your `save()` would look like this:

```python
from django.utils import timezone

class User(models.Model):
    created_at = models.DateTimeField(editable=False)
    modified_at = models.DateTimeField()

    def save(self, *args, **kwargs):
        ''' On save, update timestamps '''
        if not self.pk:
            self.created_at = timezone.now()
        self.modified_at = timezone.now()
        return super(User, self).save(*args, **kwargs)
```

https://stackoverflow.com/questions/1737017/django-auto-now-and-auto-now-add
