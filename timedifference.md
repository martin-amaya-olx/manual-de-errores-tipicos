###Time Difference

* la tabla inplicada en esto es la tabla geodesic_countries
* al finalizar de correr en LIVE, hay que flushear cache, y despues restartear abl
* para saber la hora que es en los distintos pasises es util esta pagina timeanddate.com
* contrastar los ultimos item publicados en el pais correspondiente, y con la pagina timeanddate.com


####Querys Utiles
**averiguar el ID de el pais en la tabla geodesic_countries** `SELECT country_id,name,timeDifference FROM geodesic_countries ẀHERE name like '%argen%';`
**comparar la diferencia con new york** `SELECT country_id,name,timeDifference FROM geodesic_countries ẀHERE country_id in (1,193);`

####Testeo
**ver en que estado esta**`SELECT country_id,name,timeDifference FROM geodesic_countries ẀHERE country_id = 193;`

####PROC format
	*Country name:* South Africa
	*Country id:* 193
	*Time difference with NY:* 6 hours

	UTC time: UTC/GMT +2:00 hours, SA Standard Time 
	No Daylight Saving Time

	----
	*Dev information*

	Current {{timeDifference}} for South Africa:

	{noformat}
	DB-ONLINE>select country_id, name, timeDifference from geodesic_countries where country_id = 193;
	+------------+-------------+----------------+
	| country_id | name        | timeDifference |
	+------------+-------------+----------------+
	|        193 | SouthAfrica |              7 |
	+------------+-------------+----------------+
	1 row in set (0.37 sec)
	{noformat}

	We need to replace 7 by 6.ç

####RLS format
	*Deploy*

	# DBA :: Execute script:
	{noformat}
	DBOLX_1/DML/PROC-436_southAfrica_timedifference.sql
	{noformat}
	# RM :: Restart ABL