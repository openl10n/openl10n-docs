Installation
============

The OpenLocalization application is composed of a REST API for the backend
based on the Symfony framework, and a Javascript web-app for the frontend.

.. note::

    Initially the Javascript frontend was included in the main repository
    (`openl10n/openl10n <https://github.com/openl10n/openl10n>`_)
    as a BackboneJS application.
    However a new version of the frontend is being developped in a separate repository
    (`openl10n/openl10n-app <https://github.com/openl10n/openl10n-app>`_) using the AngularJS framework.


Requirements
------------

- PHP 5.4 (or higher)
- MySQL or PostgreSQL server

.. tip::

    The following section explains how to install the application from the source files.
    But you can skip it and directly grap the latest release archive (**openl10n-vX_X_X.zip**)
    from the `release section on GitHub <https://github.com/openl10n/openl10n/releases>`_
    which contains every compiled files needed to run the app.


Install from the sources
------------------------

First, clone the source files via git:

.. code-block:: bash

    git clone https://github.com/openl10n/openl10n.git
    cd openl10n


Then install the project's dependencies. PHP dependencies are managed via `Composer <https://getcomposer.org>`_.
Download them using the ``install`` command:

.. code-block:: bash

    curl -sS https://getcomposer.org/installer | php
    php composer.phar install

.. tip::

    You may want to install the Composer executable globally.
    Please refer to the `official Composer documentation <https://getcomposer.org/doc/00-intro.md#installation-nix>`_
    for more details.

For the new frontend side, you have nothing to do since the compiled scripts
is already available from a CDN.
But since the legacy app is being used, it's recommended to have `NodeJS <https://github.com/joyent/node/wiki/installation>`_
and `npm <https://www.npmjs.org/doc/cli/npm-install.html>`_ installed locally.

CSS compilation depends on `Sass <http://sass-lang.com>`_ (which requires Ruby).

.. code-block:: bash

    gem install sass

Compile the assets the `Gulp <http://gulpjs.com>`_ task manager.

.. code-block:: bash

    npm install
    npm install -g gulp
    gulp build --prod


Setup the database
------------------

When installing PHP dependencies via the ``composer install`` command, a prompt should
have asked you about application configuration (eg. database credentials).
But you can also fill the configuration file ``app/config/parameters.yml`` manually
(see ``app/config/parameters.yml`` as an example).

Once the credentials configured, you can create the database schema by running the
following commands:

.. code-block:: bash

    app/console doctrine:database:create --env=prod --no-debug
    app/console doctrine:schema:create --env=prod --no-debug

You can also create a new user by running this interactive command:

.. code-block:: bash

    app/console openl10n:user:new --env=prod --no-debug


Run the application
-------------------

In order to access the application, access the ``web/app.php`` file via your web
browser.

If you are using Nginx or Apache, please refer to the official Symfony documentation:
`Configuring a Web Server <http://symfony.com/doc/current/cookbook/configuration/web_server_configuration.html>`_

If you want try it locally, just run the basic PHP built-in server via the
``php app/console server:run`` command and then access ``http://localhost:8000``
with your browser.


Deployment
----------

WIP

Upgrades
--------

WIP
