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

Installing the backend part of the application implies having ``PHP >= 5.4``.

First, get the sources:

.. code-block:: bash

	git clone https://github.com/openl10n/openl10n.git
	cd openl10n

Then install the project's dependencies.
PHP dependencies are managed via `Composer`_.
Download them using the ``install`` command:

.. code-block:: bash

	curl -sS https://getcomposer.org/installer | php
	php composer.phar install

.. note::

	You may want to install the Composer executable globally.
	Please refer to the `official Composer documentation`_ for more details.

Compiling the assets
--------------------

Assets are compiled using `Gulp`_ (which requires `Node`_ and `NPM`_):

.. code-block:: bash

	npm install
	npm install -g gulp bower
	bower install
	gulp build --prod

Accessing the application
-------------------------

In order to access the application, access the ``web/app_dev.php`` file via your web
browser.

.. tip::

    If you use PHP 5.4 or higher, you can also use the build-in webserver for
    Symfony. Run the ``php app/console server:run`` command and then access
    ``http://localhost:8000``.


.. _Composer: https://getcomposer.org/
.. _`official Composer documentation`: https://getcomposer.org/doc/00-intro.md#installation-nix
.. _Gulp: http://gulpjs.com/
.. _Node: http://nodejs.org/
.. _NPM: https://www.npmjs.org/
