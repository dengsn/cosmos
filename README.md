# Cosmos

**Cosmos** is an OpenStreetMap implementation written in Python. It uses Redis as a backend for storing the data.

An [overview of components](https://wiki.openstreetmap.org/wiki/Component_overview) of the OSM implementation:
![Component overview](https://wiki.openstreetmap.org/w/images/2/27/OSM_Components.svg)

## cosmos.osm
This package contains the model for OSM elements and tags:
* [Tag](https://wiki.openstreetmap.org/wiki/Tag)
* [Element](https://wiki.openstreetmap.org/wiki/Elements)
* [Node](https://wiki.openstreetmap.org/wiki/Node)
* [Way](https://wiki.openstreetmap.org/wiki/Way)
* [Relation](https://wiki.openstreetmap.org/wiki/Relation)

## cosmos.database
This package contains an ORM to map OSM elements to a Redis [database](https://wiki.openstreetmap.org/wiki/Database). Preferably it contains [changesets](http://wiki.openstreetmap.org/wiki/OsmChange) that reference the elements that are part of it.

An overview of the database schema:
![Database schema](https://wiki.openstreetmap.org/w/images/5/58/OSM_DB_Schema_2016-12-13.svg)

## cosmos.api
This package contains the API to interact with the OSM elements (i.e. by means of iD or JOSM), compatible with [API v0.6](http://wiki.openstreetmap.org/wiki/API_v0.6).

## cosmos.renderer
This package contains the code to convert the OSM elements to a visual representation. Preferably it has a MapCSS implementation that handles the style of the visuals.

## cosmos.tileserver
This package contains the API to view tiles using a [TMS tile server](http://wiki.openstreetmap.org/wiki/TMS), i.e. in a [Slippy map](http://wiki.openstreetmap.org/wiki/Slippy_map_tilenames). While running the server delegates missing tiles to the renderer.
