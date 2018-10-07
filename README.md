# PolygonOfAnyCity
How to get polygon of any city or state in the world and save it in MySql table

1- Enter this url and search for any city
https://nominatim.openstreetmap.org


2- Click on "details" button on the left side of your screen

3- Scroll down and look for relation number (`looks like this ==> 3242293`)

4- Now, Open this url and paste the relation number
http://polygons.openstreetmap.fr/index.py

5- Choose GeoJSON format

to insert it to MySql
https://dev.mysql.com/doc/refman/5.7/en/spatial-geojson-functions.html

Use the following format
{
“type” : “Polygon”,
“coordinates” [[
[xx ,xx],[xx ,xx],[xx ,xx],[xx ,xx],…….
]]
}

Inset it in text column and use the following functions to read it as geometry  

SELECT ST_AsText(ST_GeomFromGeoJSON(bounds)) FROM `cities`



references :
https://gis.stackexchange.com/a/192298


