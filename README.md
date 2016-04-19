Caneda User's Manual
====================

Caneda uses *Sphinx* and *Read the Docs* as the project documentation system. *Read the Docs* hosts the documentation, making it fully searchable and easy to find, while *Sphinx* is the document format used by *Read the Docs*. *Read the Docs* supports webhooks so the docs get automatically built when you commit code.

Amongs the main features of *Read the Docs*, you can find: 
  * GitHub integration
  * Auto-updating
  * Internationalization of pages
  * Versions of the docs
  * Automatic PDF Generation
  * Integrated search

You can read Caneda's help online, generated automatically from this repository at:

http://caneda.readthedocs.org/en/latest/


Adding Documentation
--------------------
To add new documents, simply create a new ``document.rst`` file (or edit an existing one) and push your changes to the repository.

To review your changes before commiting, run the following command from a terminal:

``$ make html``

The previous command will created a local copy of the html documents, and will place them in the ``_build`` folder.


Read the Docs Sphinx Theme
--------------------------
The documentation in this repository uses a local mobile-friendly sphinx, developed by *readthedocs.org*. To work, it is locally installed (alongside *Sphinx*) by using the following command:

``$ pip install sphinx_rtd_theme``

Or by installing it directly from your distribution repository. As an alternative, the source code for the theme could be downloaded and installed in the `docs/_themes/sphinx_rtd_theme`` directory, however the previous method was used to keep it up to date.

Currently if you import sphinx_rtd_theme in your local sphinx build, the *Read the Docs* site will fail, since it gets confused. To be able to run this theme locally and then also have it build on RTD, the following lines are added to the  ``conf.py`` file:

.. code:: python

    # on_rtd is whether we are on readthedocs.org, this line of code grabbed from docs.readthedocs.org
    on_rtd = os.environ.get('READTHEDOCS', None) == 'True'

    if not on_rtd:  # only import and set the theme if we're building docs locally
        import sphinx_rtd_theme
        html_theme = 'sphinx_rtd_theme'
        html_theme_path = [sphinx_rtd_theme.get_html_theme_path()]

    # otherwise, readthedocs.org uses their theme by default, so no need to specify it

   
