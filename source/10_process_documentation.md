# Process Documentation

This chapter will describe how one would style a custom version
of OSM before and after our solution. This is necessary
to show the added value of our project and help the understanding.

## Diagram

![Flow diagram of producing vector tiles from OSM planet files \label{ref_a_figure}](source/figures/osm2vectortiles.png)

![Flow diagram of serving vector tiles to Mapbox Studio \label{ref_a_figure}](source/figures/vectortiles-server.png)

![Flow diagram of serving raster tiles to a web client \label{ref_a_figure}](source/figures/rastertiles-server.png)

## Goal

The user wants to create a custom styled version of OpenStreetMap
where he highlights all luxury shops.

## Before

### Variant 1

Completly rely on Mapbox. Use Mapbox Studio to create the styles
and upload your styles in the Mapbox Cloud.

### Variant 2: Using TileMill

Using TileMill one can select the prepared OSM style of Mapbox
and explicitely render MBTiles with raster data.
This data can then be easily hosted.


### Variant 3

Manually apply the styles and host them yourselves.
This involves building your own tileserver\footnote{\url{https://https://switch2osm.org/serving-tiles/manually-building-a-tile-server-14-04/}}.

## After

User downloads a vector tile server image containing the OSM pbfs.
He then connects via Mapbox tilejson urls.
Then he exports the tmz file and puts it into the tileserver docker container.
The user starts the tileserver docker container and has a viable tile hosting service.

## How to do copying

https://github.com/mapbox/mapbox-studio-classic/issues/1080
