###Create categories
* checkear que todas las categorias tengan su slug, sobretodo las PARENT
* checkear que las categorias existan en la tabla geodesic_catetgories
* las que si existen en el campo ACTION llevaran USE
* en el campo ACTOIN si hay 2 idiomas, va el idioma default de el pais en USE, o NEW (si el id de la categoria es nuevo completamente), y el otro en lenguage, por lo general ingles es el segundo idioma para latinoamerica, pero en otros esel principal, ojo con eso.

#####Querys utiles 
**buscar el ID de un idioma por su nombre**  `SELECT * from geodesic_olx_languages WHERE language_name LIKE '%spani%';`
**buscar un pais por nombre:** `SELECT country_id,name,olx_url,OLXCountry FROM geodesic_countries WHERE name like 'ecua%';`
**buscar en que paises esta una categoria** `SELECT country_id, category_id FROM olx_country_category WHERE category_id=821;`
**buscar las categorias que hay en un pais** `SELECT country_id, country_id, category_id FROM olx_country_category WHERE country_id=62 and category_id < 1000;`


#####Querys para testear
**testear categorias en la tabla de idiomas:**
`SELECT country_id,category_id,category_name,language_id,description from geodesic_classifieds_categories_languages where category_id in (815,816,817,830) and language_id in (1,10) and country_id=62 ORDER BY language_id;`
**ver en que paises existe una categoria en la tabla COUNTRY CATEGORY:**
`SELECT country_id,category_id from olx_country_category where category_id=821;`
**ver si las nuevas categorias aparecen en la tabla COUNTRY_CATEGORY:**
`SELECT country_id, category_id FROM olx_country_category WHERE country_id=62 and category_id in (811,813,814);`
**ver que hijas tiene una parent:**
`SELECT parent_id,category_id,category_name FROM geodesic_categories WHERE parent_id=821;`

**ver si**
`SELECT t1.country_id,t2.parent_id,t2.category_id,t1.category_id,t2.category_name FROM olx_country_category AS t1, geodesic_categories AS t2 WHERE t1.category_id < 1000 and t2.category_id < 1000 and t2.parent_id=821 and t1.country_id=62;`

**ver idiomas de paìses**
`SELECT * FROM geodesic_olx_country_language cl JOIN geodesic_olx_languages ol ON cl.language_id = ol.language_id WHERE Language_Name LIKE '%Engl%';`
