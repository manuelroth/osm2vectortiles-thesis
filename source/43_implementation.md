## Implementation

### Architecture

#### System Overview

NOTE: Show component diagram of our solution

#### Deployment

NOTE: Write about DockerHub

#### User Tests

NOTE: We could create user tests for cartographers to test ease of use

### Workflow Documentation

#### Workflow description: Producing vector tiles

##### First step: Getting OSM data

There are many different sources available to get OSM data from. Most of the time Geofabrik\footnote{\url{http://download.geofabrik.de/}} was referenced for getting single countries, continents or even the whole planet. But many times people only need a single city or region, because of this demand Mapzen\footnote{\url{https://mapzen.com/data/metro-extracts/}} provides OSM data for many cities and regions around the globe.

The OSM data is missing something very important: the administrative boundaries. This needs to be downloaded separatly due to the fact, that somebody could manipulate the boundary of a region. As a result of this administrative boundaries get checked by the OSM community and released separatly.

The data is available in the PBF and OSM XML format. If available the PBF(Protocolbuffer Binary Format)\footnote{\url{http://wiki.openstreetmap.org/wiki/PBF_Format}} version should be choosen, as it is 30% smaller and 5-6 times faster to read and write than the bzipped OSM XML version.

##### Second step: Importing OSM data into Postgis

As with the data sources there are many possiblities to import and store OSM data. The database type and importing schema should be choosen based on the primary use case. 
Since the goal of this workflow is to render vector tiles, our primary use case is rendering. The OSM community recommends\footnote{\url{http://wiki.openstreetmap.org/wiki/Databases_and_data_access_APIs}} PostgreSQL with the Postgis extension and imposm or osm2pgsql as schema.

###### imposm importer

Imposm is an import tool for osm data, it is not a schema. But it defines a default schema\footnote{\url{http://imposm.org/docs/imposm/latest/database_schema.html}}, which could possibly be changed by provinding a custom mapping file. An advantage of the default schema is that it groups data thematically into tables. Which results in smaller tables and simpler queries.
Imposm 3 supports updating the database from OSM diff files\footnote{\url{http://imposm.org/docs/imposm3/latest/tutorial.html\#diff}}

###### osm2pgsql importer

Osm2pgsql is must commonly used to import OSM data for the rendering use case. The import schema is also called osm2pgsql and defines a very simple schema(line, point, polygon and roads)\footnote{\url{http://wiki.openstreetmap.org/wiki/Osm2pgsql/schema}}. This results in very large tables, so it is recommended to create good indices.
Osm2pgsql supports updating of the database, if the values have been stored as hstore. 

For our use case it is important, that the import is efficent and that the import tool supports updating based on OSM diff files. Imposm 3 is faster than osm2pgsql and supports updatability. So we decided to take imposm for importing.

#### Third step: Mapbox studio source project

A Mapbox studio source project is divided into the following folder structure\footnote{\url{https://www.mapbox.com/guides/source-manual/\#source-project}}:
```
source-project.tm2source/
	data.yml
    data.xml
    .thumb.png
```
The data file defines all feature sets(layers) like landuse, waterway, road etc. The definition contains metadata like id, datasource(db, host, query, srid, extent), description, fields and properties. Mapbox Studio needs the yml version and mapnik the xml version of this file. 
.thumb.png is a thumbnail image that gets displayed in the projects list.

#### Fourth step: Generating vector tiles

To generate the vector tiles we use mapnik. Mapbox provides a very handy tool to generate vector tiles.
```
tilelive-copy --bounds=-180,-85,180,85 bridge:///home/mapbox/tmp/project.tm2source/data.xml mbtiles:///tmp/project.mbtiles
```
tilelive-copy provides the Mapnik XML file and the extent to mapnik which then generates the vector tiles. Tilelive-copy outputs these vector tiles in the mbtiles container.

![Flow diagram of producing vector tiles from OSM planet files \label{ref_a_figure}](source/figures/osm2vectortiles.png)

![Flow diagram of serving vector tiles to Mapbox Studio \label{ref_a_figure}](source/figures/vectortiles-server.png)

![Flow diagram of serving raster tiles to a web client \label{ref_a_figure}](source/figures/rastertiles-server.png)

#### Workflow description: Serving vector tiles

##### ToDo: Document Serving vector tiles
