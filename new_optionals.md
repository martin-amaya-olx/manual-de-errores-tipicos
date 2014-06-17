#CREATE OPTIONAL



###QUeris utiles
**ver si existe el dataset (pais category)**`select dataset_id,category_id,country_id from olx_catspec_applicable_field where category_id in (822,823,824,876) and country_id=62;`

###Buscar opcionales por categoría y por país
```
SELECT  cpv.field_id, 
        cpv.enabled,
        cpv.value,
        cs.slug,
        cpv.id,
        cs.category_id,
        cs.country_id 
 FROM   olx_catspec_slugs cs 
 JOIN   olx_catspec_possible_value cpv ON cpv.id = cs.possible_value_id 
 WHERE  cpv.enabled = 1 
 AND    country_id = 162 
 AND    category_id = 322 
 AND    cpv.field_id = 53;  --53 muestra los opcionales de primer nivel
```
