Mongo
=====
Zadanie 1a<br />
Zaimportowanie pliku Train.csv wymagało wstępnego przygotowania, wykorzystałem poniższy skrypt:<br />
https://github.com/nosql/aggregations-2/blob/master/scripts/wbzyl/2unix.sh

![ter2](https://github.com/mperkowski/Mongo/blob/master/ter2.png)

Wykorzystanie procesora przedstawiają poniższe zrzuty ekranu:

![first](https://github.com/mperkowski/Mongo/blob/master/first.png)

![second](https://github.com/mperkowski/Mongo/blob/master/second.png)

Zadanie 1b<br />
Zliczanie rekordów:

![ter](https://github.com/mperkowski/Mongo/blob/master/ter.png)

Importowanie trwało 1:18:06

<h3>Zadanie 1d</h3?<br />
<h3>Geojson</h3><br />
![Mapa](https://github.com/mperkowski/Mongo/blob/master/places.geojson)

Zapytania wraz z wynikami śą dostępne tutaj:<br />
[Geospatial queries](https://github.com/mperkowski/Mongo/blob/master/queries)



Dane na temat kolekcji przed i po dodaniu indexów:
```
db.places.stats()
{
	"ns" : "test.spr",
	"count" : 12,
	"size" : 2112,
	"avgObjSize" : 176,
	"storageSize" : 8192,
	"numExtents" : 1,
	"nindexes" : 1,
	"lastExtentSize" : 8192,
	"paddingFactor" : 1,
	"systemFlags" : 1,
	"userFlags" : 1,
	"totalIndexSize" : 8176,
	"indexSizes" : {
		"_id_" : 8176
	},
	"ok" : 1
}
```
```
db.places.stats()
{
	"ns" : "test.spr",
	"count" : 12,
	"size" : 2112,
	"avgObjSize" : 176,
	"storageSize" : 8192,
	"numExtents" : 1,
	"nindexes" : 2,
	"lastExtentSize" : 8192,
	"paddingFactor" : 1,
	"systemFlags" : 1,
	"userFlags" : 1,
	"totalIndexSize" : 89936,
	"indexSizes" : {
		"_id_" : 8176,
		"loc_2dsphere" : 81760
	},
	"ok" : 1
}
```

