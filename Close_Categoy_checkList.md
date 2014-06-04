####CLOSE CATEGORY
* checkear los id de las categorias a cerrar
* cuando se cierran todas las subcategorias de una parent preguntar que pasa con la parent
* checkear que pasa con los item de las categorias a cerrar
* ver cuales se cieran con item y cuales no
* recordar que para las categorias que se cierran con item hay que hacer una corrida por parent ej: PROC-402

#####Querys utiles 
**ver cuantos item tiene la categoria que se cerrara con items** `SELECT id,parent_category_id,category_id,country_id,live FROM olx_items WHERE country_id=62 and category_id in (187,248,401,244,382,191,372,370,322,324,199,414,371,198,323,207,186,281,279,280,278,283,190,329,265,255,257,260,374,386,270,259,254,593,264,256,375,261,384,267,373,266,263,385,268);`
**ver cuantos item tiene la categoria que se va a cerrar con item** `SELECT COUNT(id) FROM olx_items_62_187 WHERE category in (381,413);`

#####Querys para testear
**paraque sirve** `SELECT language_id,country_id,category_id,category_name,visible FROM geodesic_classifieds_categories_languages WHERE country_id = 62 and language_id in (1,10) and category_id in (187,381,413);`


https://www.youtube.com/watch?v=yd9ma2UVLHM
