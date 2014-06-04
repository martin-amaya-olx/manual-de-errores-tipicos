Manual de Procedimiento
=======================

###create category

	PASO 1- revisar que el template
		1.x: -se completen los nombres y los slug
		1.x: -de haber mas de un lenguaje ver que que se encuentren los category name y el slug para ese idioma
		1.x: -revisar que no exista en ese pais una categoriaque pueda reutilizarce


	PASO 2- CSV => corrida PHP => SQL resultantes
		2.x: -el csv para la corrida

		2.x: -La corrida
			NOTA: en DEVTEST somos nosotros mismos quienes corremos los SQL en la DB
			y tras testear, se pueden comitear los SQL resultantes

		2.x: -los SQL resultantes de la corrida deben moverce a la carpeta de DB para ser comiteados 
			colocandose segun corresponda en las siguientes rutas
				/db/SQLCANDIDATES/DBOLX_1/DDL/PROC-123-pais_items_tables.sql
				/db/SQLCANDIDATES/DBOLX_1/DML/PROC-123-pais_create_categories.sql
				/db/SQLCANDIDATES/DBOLX_1/GENERATOR/PROC-123-pais_filter-category-generator.sql
				/db/SQLCANDIDATES/DBOLX_1/ROLLBACK/PROC-123-pais_rollback1.sql
				/db/SQLCANDIDATES/DBOLX_1/ROLLBACK/PROC-123-pais_rollback2.sql
			y tras comitear los archivos en git, se debera entraren github, y verificar que el comit este realizado, 
			hecho esto se procedera a hacer un pull Request al repositorio de dev, y se esperara el merge


	PASO X- post
		x.x: -si las categorias son nuevos ID que se incertaron en la DB deben tenerse en cuentaa lo siguiente
			-a: crear un ftiket para SAS para queden de alta las nuevos ID en ABL ej: https://jira.olx.com/browse/SAS-1584
			-b: crear un subtiket del PROC para que se indexen los nuevos ID en spanhandler ej: https://jira.olx.com/browse/PROC-382

		x.x: -restart de ABL	
###
