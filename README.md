Introduction
============
Pageviews is a very simple middleware based page view counter. It's sole purpose is to increment page views.

PageviewsPlus adds the ability to ignore a list of urls and user agents such as search engine bots.  A default list is included for both.




Quickstart
==========

1. Install from github or clone the repository:
```bash
    pip install git+git://github.com/shadowym/django-pageviewsplus.git
```

2. Add 'pageviewsplus' to INSTALLED_APPS.
```python
    INSTALLED_APPS = (
        '...',
        'pageviewsplus',
    )
```

3. Add 'pageviewsplus.middleware.PageViewsPlusMiddleware' to MIDDLEWARE_CLASSES.
```python
    MIDDLEWARE_CLASSES = (
        '...',
        'pageviewsplus.middleware.PageViewsPlusMiddleware'
    )
```

4. Run 'python manage.py syncdb' or 'python manage.py migrate'.
```bash
    python manage.py migrate
```

5. Add {% load pageviewsplus_tags %} to templates.

6. Optionally insert {% pageviewsplus %} or {% pageviewsplus_url request.path %} to templates.

Configuration
=============

The ``settings.py`` file contains the following settings.

* ``IGNORED_URLS``: Defines what urls to ignore.  A default list is provided. Can be overridded in project ``settings.py`` file.
* ``IGNORED_USER_AGENTS``: Case sensitive list defines what user agents to ignore. Default list can be overridden in project ``settings.py``.
