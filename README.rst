Adding line numbers to richtext (rtf) format (and importing to power point).
===================
1. The line numbers are shown in black color (RGB(0,0,0)). This is done by modifying ``pygments/formatters/rtf.py``.
2. To avoid the conflict with the mainstream Pygments package, I modified the package name when installing it. In particular, the ``Pygments`` becomes ``Pygments1``; the ``pygmentize`` becomes ``pygmentize1``.
3. To install, just run ``python setup.py install``. See ``setup.cfg`` for more details.

On MacOS, to generate highlighted code in richtext and insert into power point, you can use ``pygmentize1 -f rtf FILE.php | pbcopy``, then you paste to TextEdit. Recopy the content from TextEdit and finally paste to power point. That's it [1].

[1]: https://gist.github.com/ept/4475995/

Bugs: 
1. Code comments are usually in italic style. When a comment lies at the end of a line, and the next line starts with intents, the line number of the next line migit be italic style also. This is because the line end character and the intents (tabs or spaces) in the next line consists of one token in Pygments. Therefore, the line number I insert is also rendered with the local italic style.

Welcome to Pygments
===================

This is the source of Pygments.  It is a **generic syntax highlighter** written
in Python that supports over 500 languages and text formats, for use in code
hosting, forums, wikis or other applications that need to prettify source code.

Installing
----------

... works as usual, use ``pip install Pygments`` to get published versions,
or ``python setup.py install`` to install from a checkout.

Documentation
-------------

... can be found online at https://pygments.org/ or created with Sphinx by ::

   cd doc
   make html

Development
-----------

... takes place on `GitHub <https://github.com/pygments/pygments>`_, where the
Git repository, tickets and pull requests can be viewed.

Continuous testing runs on GitHub workflows:

.. image:: https://github.com/pygments/pygments/workflows/Pygments/badge.svg
   :target: https://github.com/pygments/pygments/actions?query=workflow%3APygments

The authors
-----------

Pygments is maintained by **Georg Brandl**, e-mail address *georg*\ *@*\ *python.org*
and **Matthäus Chajdas**.

Many lexers and fixes have been contributed by **Armin Ronacher**, the rest of
the `Pocoo <https://dev.pocoo.org/>`_ team and **Tim Hatch**.

The code is distributed under the BSD 2-clause license.  Contributors making pull
requests must agree that they are able and willing to put their contributions
under that license.
