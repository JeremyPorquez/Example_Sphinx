Lumache
=======

**Lumache** (/lu'make/) is a Python library for cooks and food lovers that
creates recipes mixing random ingredients.  It pulls data from the `Open Food
Facts database <https://world.openfoodfacts.org/>`_ and offers a *simple* and
*intuitive* API.

.. note::

   This project is under active development.

Tutorial link
=============
https://www.sphinx-doc.org/en/master/tutorial/getting-started.html

.. code:: bash

    $ python -m venv .venv
    $ source .venv/bin/activate
    (.venv) $ python -m pip install sphinx
    (.venv) $ sphinx-build --version
    (.venv) $ sphinx-quickstart docs
    (.venv) $ sphinx-build -b html docs/source/ docs/build/html


conf.py
=======

.. code:: python

    # uncomment lines below and make sure os.path.abspath does not point to 
    # docs directory but to package directory which is '..'
    import os
    import sys
    sys.path.insert(0, os.path.abspath('..'))


Adding your python module
=========================

.. code:: bash

    (.venv) $ sphinx-apidoc -o docs .

Modify *index.rst* by adding `modules`

.. code:: rst

    .. toctree::
   
   :maxdepth: 2
   :caption: Contents:

   modules

.. automodule:: my_package
   :members:



Sphinx packages
===============

Autodoc
-------

    https://stackoverflow.com/questions/13516404/sphinx-error-unknown-directive-type-automodule-or-autoclass

.. code:: bash

    # Declare it in the conf.py
    extensions = [
        ...
        'sphinx.ext.autodoc',
        ...
    ]

Read the docs
-------------

    https://sphinx-rtd-theme.readthedocs.io/en/stable/installing.html

.. code:: bash

    (.venv) $ pip install sphinx_rtd_theme

In your ``conf.py`` file:

.. code:: python

    import sphinx_rtd_theme

    extensions = [
        ...
        'sphinx_rtd_theme',
    ]

    html_theme = "sphinx_rtd_theme"

Copy button
-----------

    https://stackoverflow.com/questions/39187220/how-to-add-a-copy-button-in-the-code-blocks-for-rst-read-the-docs

.. code:: bash

    (.venv) $ pip install sphinx-copybutton

    # Declare it in the conf.py
    extensions = [
        ...
        'sphinx_copybutton',
        ...
    ]




