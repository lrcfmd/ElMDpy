# ElMD
The Element Movers Distance (ElMD) is a similarity measure for chemical compositions. This distance between two compositions is calculated from the minimal amount of work taken to transform one distribution of elements to another along the modified Pettifor scale. 

This repository provides the reference implementations as described in our paper "[The Earth Movers Distance as a metric for the space of inorganic compositions](https://chemrxiv.org/articles/preprint/The_Earth_Mover_s_Distance_as_a_Metric_for_the_Space_of_Inorganic_Compositions/12777566)". 

We recommend installation via pip

`pip install ElMD`

The branch "njit" contatins byte-compiled python using the numba package which is much faster in practice. During testing this had a tendency to break python environments with materials science python libraries, so use with care. The pip version is stable with all environments if you do have issues.

## Usage
For simple usage initiate an object with its compositional formula

`from ElMD import ElMD`

`x = ElMD("CaTiO3")`

Calculate the distance to a second object with the `elmd` method. 

`x.elmd("SrTiO3")` 

`0.2`

Alternate chemical scales may be accessed via the "metric" argument, e.g.

`x = ElMD("CaTiO3", metric="atomic")`

`x.elmd("SrTiO3")`

`3.6`

## Documentation

Complete documentation may be found at www.elmd.io/api

