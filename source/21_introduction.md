## Introduction

Creating a custom styled OSM map is one of the most common use cases among cartographers yet it is very difficult to do so. With the new emerging technology of vector tiles it is possible to allow anyone to create their custom OSM maps without downloading the entire database and managing complex infrastructure. The task of this project is to make this as easy as possible.

### Vision

Michal Migurski published on March 15, 2013 a blog post\footnote{\url{http://mike.teczno.com/notes/postgreslessness-mapnik-vectiles.html}}, in which he described his first attempts to use vector tiles as a source for the mapnik tile renderer. In this post he describes the vision of vector tiles. 

Vector tiles only contain geometries and metadata. The visual style can be applied when the tiles get requested. Since vector tiles do not contain any information about the style, they are smaller than raster tiles. This enables high resolution maps, fast map loads and efficient caching.

### Targets

The main target of this thesis is to allow anyone to create their custom OSM map without managing complex infrastructure. This main target is split into multiple subtargets, which we defined in the project proposal at the beginning.

	- Deliver a Docker Container to create vector tiles from OSM Data
	- Provide the vector tiles for Switzerland
	- Provide a Docker Container to serve the vector tiles together with custom styles as raster data
	- Optional: Vector tiles for the whole world

### Project procedure

This project was roughly split into the following steps:

1. Inception: Kickoff meeting with Petr Pridal, Stefan Keller and definition of project proposal
---
3. Prototyping: At the beginning we spent some time to get to know the whole software stack and create a small prototype of every part. 
---
2. Evaluation and Requirements: Evaluation of different parts of the stack like data import tools, vector tile server. The evaluation of this technology as well as additional technologies are part of the section technology evaluation.
---
3. Implementation: The creation of the map was an iterative process. We started at the lowest zoomlevel (14) and implemented level by level up to zoom level 0. On the way we identified many different problems which are further described in the section implementation of the project documentation. We documented all of our decisions during the implementation process, so that Petr Pridal and Stefan Keller could follow every step we took.
---
4. Optimizations: Once we had a first alpha version, we added an additional data source (Natural Earth) to further improve the quality of the upper zoomlevels. During the implementation phase we did a refectoring of the project structure and added continuous deployment to our setup.
---
5. Rendering: At the end of the project there was a long period for the actual rendering of the vector tiles.
---

