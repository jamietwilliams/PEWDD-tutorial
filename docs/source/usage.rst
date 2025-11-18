Usage
=====

.. _installation:

Installation
------------

To access PEWDD, download it as a .csv file. To make any diagnostic plots, also download the PEWDD_functions.py file and all associated packages.

>>> import pandas as pd
>>> import numpy as np
>>> import matplotlib.pyplot as plt
>>> from random import randint
>>> import matplotlib.lines as mlines
>>> import PEWDD_functions as pf

Accessing PEWDD
----------------
To access PEWDD, I recommend using the Python pandas module.

>>> import pandas as pd
>>> PEWDD = df.read_csv('PEWDD.csv')

Manipulation of this DataFrame can be used to access data on specific white dwarfs or groups of white dwarfs.

Each entry has a unique "Identifier" label which can be used to obtain information on a single white dwarf from a paper.

>>> GD362_Zuckerman2007 = PEWDD[PEWDD["Identifier"] == "GD362 Zuckerman 2007"]

Because several papers may use different names for the same white dwarf, I recommend using the "Gaia_designation" column to search for information on a white dwarf from several papers.

>>> G29_38 = PEWDD[PEWDD["Gaia_designation"] == "Gaia DR3 2660358032257156736"]

A column can also be accessed. A word of warning: PEWDD contains data on all published white dwarf abundances. This means that some white dwarfs will show up more than once, e.g. the calcium abundance for G29-38 has been measured several times, and all these abundances are in PEWDD. Make sure to remove any duplicates with the Gaia ID (Jamie-include code for this?).

>>> Ca = PEWDD["log(Ca/H(e))"]

The full list of columns is available in the original PEWDD paper.

Multiple constraints can be applied in order to select groups of white dwarfs. For example, warm hydrogen-dominated atmosphere white dwarfs which are below 0.6 solar masses:

>>> lowmass_warm_DAZs = PEWDD[(PEWDD["atmosphere"] == 'H') & (PEWDD["T_eff"] >= 15000) & (PEWDD["mass"] <= 0.6)]
