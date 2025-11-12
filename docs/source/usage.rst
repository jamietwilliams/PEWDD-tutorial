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

Each entry has a unique "Identifier" label which can be used to obtain information on a single white dwarf from a paper.

>>> GD362_Zuckerman2007 = PEWDD[PEWDD["Identifier"] == "GD362 Zuckerman 2007"]

Because several papers may use different names for the same white dwarf, I recommend using the "Gaia_designation" column to search for information on a white dwarf from several papers.

>>> G29-38 = PEWDD[PEWDD["Gaia_designation"] == "Gaia DR3 2660358032257156736"]
