Diagnostic plots
================

.. _massfraction:

Mass fractions
--------------

PEWDD can be used to produce a mass fraction pie chart or bar chart.

>>> import pandas as pd
>>> import numpy as np
>>> import matplotlib.pyplot as plt
>>> from random import randint
>>> import matplotlib.lines as mlines
>>> import PEWDD_functions as pf
>>> PEWDD = pd.read_csv('PEWDD.csv')
>>> WDs = ["PG 0843+516 Gansicke 2012", "SDSS J1043+0855 Melis & Dufour 2017", "G238-44 Johnson 2022", "WD J2047-1259 Hoskin 2020"]
>>> pf.mass_fraction_bar_chart(PEWDD, WDs, trace_limit=0.05, SS_objects=[])

WDs is a list of all of the Identifiers which you want to plot.
trace_limit is the limit at which an element will be included in the "trace" category instead of being plotted as an individual element. The preliminary value is 5%.

Note

A word of caution: rocky material predominantly consists of O, Mg, Si, and Fe (these four elements make up about 95% of the mass of Earth). If all four metals are not detected, the mass fractions may not be realistic. Additionally, other elements may significantly contribute if the material is not like bulk Earth. For example, a Kuiper Belt analogue may have a large nitrogen mass fraction, but is only a trace element in the Earth.
