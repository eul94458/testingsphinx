.. n documentation master file, created by
   sphinx-quickstart on Mon Aug  8 13:06:28 2022.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

Welcome to n's documentation!
=============================

.. toctree::
   :maxdepth: 3
   :caption: Contents:

   markd.md
   how_to_sphinx.md



Indices and tables
==================

* :ref:`genindex`
* :ref:`modindex`
* :ref:`search`


Trying Python Function
======================

.. py:function:: enumerate(sequence[, start=0])

   Return an iterator that yields tuples of an index and an item of the
   *sequence*. (And so on.)
   WOOWOOWOWOW


Code Block
==========

How to implement code-block

.. code-block:: console

   (.venv) pip install symqc

.. code-block:: python

   import sys
   sys.path.insert(0, "./")

You should check out the :doc:`text1` file for testing.



Testing AUTODOC
===============

.. automodule:: symqc
   :members:
   :inherited-members:
   :undoc-members:
   :private-members:
   :special-members: