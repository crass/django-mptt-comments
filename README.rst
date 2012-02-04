====================
Django Mptt Comments
====================

Django Mptt Comments is a simple way to display threaded comments instead of the django contrib comments.

Repo moved `here`__ .

__ http://bitbucket.org/fivethreeo/django-mptt-comments/

Installation
============

#. Get the required third party modules ::

    pip install "django-mptt>=0.5.0"

#. Add the needed apps to `INSTALLED_APPS` ::

    'django.contrib.comments',
    'django.contrib.markup',
    'mptt',
    'mptt_comments'

#. Add needed settings to your settings.py ::

    COMMENTS_APP = 'mptt_comments'

#. Add `mptt_comments.urls` to your projects urlconf ::

    (r'^comments/', include('mptt_comments.urls')),

#. Add javascript translation support your projects urlconf ::

    url(r'^jsi18n/(?P<packages>\S+?)/$', 'django.views.i18n.javascript_catalog'),

#. Add the required code to the objects detail page (see Usage)

#. Copy the templates to adapt them for your site

#. Style the forms using css

Usage
=====

In any detail template that wants to use `mptt_comments` ::
        
        {% block extrahead %}
        
        {% load mptt_comments_tags %}
        {% get_mptt_comments_media %}
        
        {% endblock extrahead %}

To display the toplevel tree in templates: ::

        {% load mptt_comments_tags %}    

        {% display_comment_toplevel_for object %}
        

TODO
====
- Make the more link work without javascript