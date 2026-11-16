
```
**[Service]**
User=root
Group=www-data
WorkingDirectory=/var/www/html/hb-django
Environment="PATH=/var/www/html/hb-django/venv/bin"
ExecStart=/var/www/html/hb-django/venv/bin/gunicorn \  config.wsgi:application \
    --workers 3 \
    --bind unix:/var/www/html/hb-django/django.sock \
    --access-logfile - \
    --error-logfile - \
    --log-level info

Restart=always
```
