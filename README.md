# triglobe
Marching triangulation of signed distance function surfaces.

This is implementation of of the algorithm presented in "Curvature Dependent Polygonization of Implicit Surfaces" by Bruno Rodrigues de Araújo and Joaquim Armando Pires Jorge, limited to surfaces defined as signed distance function (SDF).

The SDF restriction makes the projection-to-surface part of the algorithm trivial and simplifies the Hessian considerably as well.

triglobe source code includes a copy of [nanoflann](https://github.com/jlblancoc/nanoflann) header only library for building KD-trees.

