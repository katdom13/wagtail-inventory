.. image:: https://github.com/cfpb/wagtail-inventory/workflows/test/badge.svg
  :alt: Build Status
  :target: https://github.com/cfpb/wagtail-inventory/actions/workflows/test.yml
.. image:: https://coveralls.io/repos/github/cfpb/wagtail-inventory/badge.svg?branch=main
  :alt: Coverage Status
  :target: https://coveralls.io/github/cfpb/wagtail-inventory?branch=main

wagtail-inventory
=================

Search Wagtail pages by block type.

Wagtail Inventory adds the ability to search pages in your Wagtail site by the StreamField block types they contain. It adds a new Settings menu to the Wagtail admin site that allows you to search for pages that do or do not contain certain blocks. It supports searching both by Wagtail built-in blocks (like ``CharBlock``) as well as any custom blocks you might define.

Setup
-----

Install the package using pip:

.. code-block:: bash

  $ pip install wagtail-inventory

Add ``wagtailinventory`` as an installed app in your Django settings:

.. code-block:: python

  # in settings.py
  INSTALLED_APPS = (
      ...
      'wagtailinventory',
      ...
  )

Run migrations to create required database tables:

.. code-block:: bash

  $ manage.py migrate wagtailinventory

Run a management command to initialize database tables with current pages:

.. code-block:: bash

  $ manage.py block_inventory

You should now be able to search your pages in the Wagtail admin site, under Settings > Block Inventory.

Compatibility
-------------

This code has been tested for compatibility with:

* Python 3.8+
* Django 3.2 (LTS), 4.0, 4.1
* Wagtail 2.15 (LTS), 3.0, 4.0, 4.1 (LTS)

It should be compatible with all intermediate versions, as well.
If you find that it is not, please `file an issue <https://github.com/cfpb/wagtail-inventory/issues/new>`_.

Testing
-------

Running project unit tests requires `tox <https://tox.wiki/en/latest/>`_:

.. code-block:: bash

  $ tox

To run the test app interactively, run:

.. code-block:: bash

  $ tox -e interactive

Now you can visit http://localhost:8000/admin/ in a browser and log in with ``admin`` / ``changeme``.

Open source licensing info
--------------------------

#. `TERMS <https://github.com/cfpb/wagtail-inventory/blob/main/TERMS.md>`_
#. `LICENSE <https://github.com/cfpb/wagtail-inventory/blob/main/LICENSE>`_
#. `CFPB Source Code Policy <https://github.com/cfpb/source-code-policy>`_
