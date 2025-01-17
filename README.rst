================
django CMS Style
================

|pypi| |build| |coverage|

**django CMS Style** is a plugin for `django CMS <http://django-cms.org>`_
that allows you to create a HTML container containing classes, styles, ids
and other attributes definable through the plugins settings.


.. note:: 

    This project is considered 3rd party (no supervision by the `django CMS Association <https://www.django-cms.org/en/about-us/>`_). Join us on `Slack                 <https://www.django-cms.org/slack/>`_ for more information.

.. image:: preview.gif


*******************************************
Contribute to this project and win rewards
*******************************************

Because this is a an open-source project, we welcome everyone to
`get involved in the project <https://www.django-cms.org/en/contribute/>`_ and
`receive a reward <https://www.django-cms.org/en/bounty-program/>`_ for their contribution. 
Become part of a fantastic community and help us make django CMS the best CMS in the world.   

We'll be delighted to receive your
feedback in the form of issues and pull requests. Before submitting your
pull request, please review our `contribution guidelines
<http://docs.django-cms.org/en/latest/contributing/index.html>`_.

We're grateful to all contributors who have helped create and maintain this package.
Contributors are listed at the `contributors <https://github.com/django-cms/djangocms-style/graphs/contributors>`_
section.

Documentation
=============

See ``REQUIREMENTS`` in the `setup.py <https://github.com/divio/djangocms-style/blob/master/setup.py>`_
file for additional dependencies:

|python| |django| |djangocms|


Installation
------------

For a manual install:

* run ``pip install djangocms-style``
* add ``djangocms_style`` to your ``INSTALLED_APPS``
* run ``python manage.py migrate djangocms_style``


Configuration
-------------

django CMS Style enables you to provide a list of predefined classes to be
displayed as first options, the default choices are: ::

    DJANGOCMS_STYLE_CHOICES = ['container', 'content', 'teaser']

You are encouraged to modify that setting to your projects specifications.

This addon provides a ``default`` template for all instances. You can provide
additional template choices by adding a ``DJANGOCMS_STYLE_TEMPLATES``
setting::

    DJANGOCMS_STYLE_TEMPLATES = [
        ('feature', _('Feature')),
    ]

You'll need to create the `feature` folder inside ``templates/djangocms_style/``
otherwise you will get a *template does not exist* error. You can do this by
copying the ``default`` folder inside that directory and renaming it to
``feature``.

The available tags can also be configured, the default choices are: ::

    DJANGOCMS_STYLE_TAGS = ['div', 'article', 'section', 'header', 'footer',
                            'h1', 'h2', 'h3', 'h4', 'h5', 'h6']

NOTICE::

    All tags included in this list should be "paired tags" that require a
    closing tag. It does not make sense to attempt to use 'img', 'input',
    'meta', or other self-closing tags in this setting.

    Also, the developer is advised to choose the tag-types wisely to avoid HTML
    validation issues and/or unintentional security vulnerabilities. For
    example, the 'script' tag should never be allowed in
    ``DJANGOCMS_STYLE_TAGS`` (though, we do not prevent this). If you have
    an application where you find yourself wishing to do this, please see
    djangocms-snippet as an alternative, but note these projects also come
    with appropriate security warnings.

After that you can place any number of other plugins inside this style plugin.
It will create a div (or other tag-type) with a class that was prior selected
around the contained plugins.


Running Tests
-------------

You can run tests by executing::

    virtualenv env
    source env/bin/activate
    pip install -r tests/requirements.txt
    python setup.py test


.. |pypi| image:: https://badge.fury.io/py/djangocms-style.svg
    :target: http://badge.fury.io/py/djangocms-style
.. |build| image:: https://travis-ci.org/divio/djangocms-style.svg?branch=master
    :target: https://travis-ci.org/divio/djangocms-style
.. |coverage| image:: https://codecov.io/gh/divio/djangocms-style/branch/master/graph/badge.svg
    :target: https://codecov.io/gh/divio/djangocms-style

.. |python| image:: https://img.shields.io/badge/python-3.5+-blue.svg
    :target: https://pypi.org/project/djangocms-style/
.. |django| image:: https://img.shields.io/badge/django-2.2,%203.0,%203.1-blue.svg
    :target: https://www.djangoproject.com/
.. |djangocms| image:: https://img.shields.io/badge/django%20CMS-3.7%2B-blue.svg
    :target: https://www.django-cms.org/
