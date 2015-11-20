## State of the Art

Current web maps are mostly based on raster images.


### History of Webmaps

#### Phase 1: Untiled Static Maps

Statically generated image for a extract of a map.

#### Phase 2: Raster Tiles

Google introduced XYZ tiles\footnote{\url{http://wiki.openstreetmap.org/wiki/Slippy_Map}} which delivered a idempotent raster image for coordinates specified by a tile index.

#### Phase 2.5: Raster Tiles with Vector Overlays

To provide interactivity tools like Leaflet\footnote{\url{http://leafletjs.com/}}
supported rendering vector data like SVG on top of a raster base map.

#### Phase 2.75: Raster Tiles from Vector Tiles

For backwards compability and faster serving of raster tiles vector tiles where
introduced to avoid querying a database.

#### Phase 3: Vector Tiles

Vector tiles are delivered directly to the browser and rendered by Web GL based
clients.

### Vector Tile Formats

#### Mapbox Vector Tiles

When Mapbox introduced it's geography tool Mapbox Studio in 2013 they created the *Mapbox Vector Tiles Specification* \footnote{\url{https://github.com/mapbox/vector-tile-spec}} which is implemented by a variety of tools and clients \footnote{\url{https://github.com/mapbox/awesome-vector-tiles}} including *Mapbox GL JS*, *Open Layers 3*, *Leaflet*, *Mapzen Tangram* and Esri
\footnote{\url{https://www.mapbox.com/blog/vector-tile-adoption/}}
in the future.

### Geopackage

The *GeoPackage Encoding Standard* is the OGC counterpart to the *Mapbox Vector Tiles Specification* which was introduced later and is supported by QGIS, ESRI and GDAL.

### Google Maps

Google Maps is using vector tiles since 2010 under the hood and was the first provider implementing this. Styling is limited and the format propretiary.

### Mapbox

In 2013 Mapbox introduced Mapbox Studio a geography tool working with vector
tiles.

### Mapzen

Was machen andere / welche ähnlichen Arbeiten gibt es zum Thema? Was kann von anderen verwendet 
werden?

### Vector Tile Providers

#### Mapbox

#### Kartotherian

#### Mapzen

Diese Einleitung soll für den Ingenieur irgendeiner Fachrichtung verständlich sein. 

Sie stellt die Aufgabe 
in einen grösseren Zusammenhang und liefert eine genaue Beschreibung der Problemstellung.

Allfällige 
Vorarbeiten oder ähnlich gelagerte Arbeiten werden diskutiert. 


Theoretische Grundlagen sind nur so weit auszuarbeiten, als dies für die Lösung der Aufgabe nötig ist 
(keine Lehrbücher schreiben).

Die Erkenntnisse aus den theoretischen Untersuchungen sind wenn immer möglich direkt mit der Problemlösung zu verknüpfen.
