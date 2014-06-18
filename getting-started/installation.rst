.. index::
   single: Installation

Installation
============

The OpenLocalization application is composed of a REST API for the backend,
based on the Symfony framework, and a Javascript client in the frontend,
based on the BackboneJS library.

Both are available in the main repository and installed at the same time.

Installing the Symfony backend
------------------------------

`composer install``

Compiling the assets
--------------------

``gulp build --prod``

Accessing the application
-------------------------

In order to access the application, access the ``web/app_dev.php`` file via your web
browser.

.. tip::

    If you use PHP 5.4 or higher, you can also use the build-in webserver for
    Symfony. Run the ``php app/console server:run`` command and then access
    ``http://localhost:8000``.
