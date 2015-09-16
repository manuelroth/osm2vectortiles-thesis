# Management Summary

## Introduction

Creating a custom styled OSM map is one of the most common use cases among cartographers yet
it is very difficult to do so. With the new emerging technology of vector tiles it is possible
to allow anyone to create their custom OSM maps without downloading the entire database
and managing complex infrastructure. The task of this project is to make this as easy
as possible.

## Approach / Technologies

Our project is focused on creating a free and Open Source vector tiles of Open Street Map
that can easily used by developers, cartographers and designers to create their
custom maps.

Through the use of Docker we can provide workflows that don't need a complicate setup
and are deployable across operating systems.


## Result

- Docker Container to create vector tiles (MBTiles with PBF) from OSM
- Docker Container to serve vector tiles together with custom styles as raster data
