---
title: 'rf: Receiver function calculation in seismology'
tags:
  - Python
  - geophysics
  - seismology
  - receiver function
  - deconvolution
authors:
  - name: Tom Eulenfeld
    affiliation: 1
affiliations:
 - name: Institute of Geosciences, Friedrich Schiller University Jena, Germany
   index: 1
date: 9 Octobober 2019
bibliography: paper.bib

---

# Summary

The receiver function method is a popular seismological technique to investigate crustal and upper mantle velocity
discontinuities like the Moho. Basic concept of the method is that a part of incident P-waves from a teleseismic
event gets converted to S-waves at significant discontinuities under the receiver.
The travel time difference between the first arriving P-wave and the converted S-wave constrains
the depth of the discontinuity and the velocity ratio of P- and S-waves of the overlaying structure.
To remove source side and propagation effects, receiver function calculation often involves a deconvolution
of different components of the rotated seismogram.

``rf`` is a Python package for calculating receiver functions. It provides the ``RFStream`` class which extents Obspy's
``Stream`` class [@obspy] with functionality needed for receiver function calculation.
Among those are, waveform input/output with metadata preservation,
calculation of incidence angles for rotation of waves into ZRT or LQT coordinate systems,
frequency domain or time domain deconvolution techniques, move-out correction,
calculation of and stacking by piercing points.
Receiver functions of S to P converted waves can also be calculated.

``rf`` is designed to be used by both researchers and students of seismology. Most often it will be used as a library
in other researcher's code. Additionally, rf could act as glue for other codes with specialized functionality
relevant to receiver function calculation. These codes are often written in Fortran
and it is easy to integrate Fortran codes with NumPy's f2py into the project [@f2py].
As an example, `rf` makes already use of the Fortran Toeplitz package [@toeplitz] for time domain deconvolution.
The package can be used together with recently open-sourced `telewavesim` package [@telewavesim]
to invert for crustal velocity models.
`rf` can be installed from pypi, an online documentation and tutorials are available on the project site.

# References
