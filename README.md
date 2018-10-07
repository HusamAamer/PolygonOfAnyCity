# PolygonOfAnyCity
How to get polygon of any city or state in the world and save it in MySql table

1- Enter this url and search for any city
https://nominatim.openstreetmap.org


2- Click on "details" button on the left side of your screen

3- Scroll down and look for relation number (`looks like this ==> 3242293`)

4- Now, Open this url and paste the relation number
http://polygons.openstreetmap.fr/index.py

5- Choose GeoJSON format

#### 🎉🎉🎉 Now we have a MultiPolygon

# Inserting a polygon to MySql
1- Prepare the polygon, Use the following format

    {
      “type” : “Polygon”,
      “coordinates” [[
        [xx ,xx],
        [xx ,xx],
        ...
        ..
      ]]
    }
*Note: I use jaysoon app in macOS to read and modify JSON easily.
Download jayson: https://itunes.apple.com/us/app/jayson-visual-json-editor/id1189824719?mt=12

2- Store JSON inside a text column.
3- Assuming your column is called `bounds` and table is `cities`,You can read it as follows:




**References :**
https://gis.stackexchange.com/a/192298
https://dev.mysql.com/doc/refman/5.7/en/spatial-geojson-functions.html

