# CRIMEGRID

The CRIMEGRID id is the identifier used to get detailed data.


## Get all CRIMEGRID ids

We use the gis server on delawareonline to search.  Search for all that contain 0 or 1.  Inspection of the maps show that all ids start with 0 or 1.  For now we do not get any geometry back.  Just a quick and dirty grab to json.

    curl "http://gis.delawareonline.com/arcgisREST/services/crimeSerious/MapServer/0/query?text=0&geometry=&geometryType=esriGeometryEnvelope&inSR=&spatialRel=esriSpatialRelIntersects&where=&returnGeometry=false&outSR=&outFields=&f=pjson" -o 0.json

    curl "http://gis.delawareonline.com/arcgisREST/services/crimeSerious/MapServer/0/query?text=1&geometry=&geometryType=esriGeometryEnvelope&inSR=&spatialRel=esriSpatialRelIntersects&where=&returnGeometry=false&outSR=&outFields=&f=pjson" -o 1.json


## Filter jsons to get list of CRIMEGRID

jq - commandline tool for json manipulation
https://stedolan.github.io/jq/

https://jqplay.org/s/CUxKPEphYp

    jq '(.features[].attributes.CRIMEGRID)'

## Get results table

HTML results for modgrid.  modgrid = CRIMEGRID

http://php.delawareonline.com/news/evergreen/crime/popupSummary.php?modgrid=090346
