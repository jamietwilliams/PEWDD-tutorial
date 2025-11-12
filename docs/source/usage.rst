Usage
=====

.. _installation:

Installation
------------

To install PEWDD, download it as a .csv file.

Accessing PEWDD
----------------
To access PEWDD, I recommend using the Python pandas module.

>>> import pandas as pd
>>> PEWDD = df.read_csv('PEWDD.csv')


Creating recipes
----------------

To retrieve a list of random ingredients,
you can use the ``lumache.get_random_ingredients()`` function:

.. autofunction:: lumache.get_random_ingredients

The ``kind`` parameter should be either ``"meat"``, ``"fish"``,
or ``"veggies"``. Otherwise, :py:func:`lumache.get_random_ingredients`
will raise an exception.

.. autoexception:: lumache.InvalidKindError

For example:

>>> import lumache
>>> lumache.get_random_ingredients()
['shells', 'gorgonzola', 'parsley']

