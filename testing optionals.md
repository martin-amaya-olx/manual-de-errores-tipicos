#Testing optionals

###Buscar opcionales
```
SELECT  cpv.field_id,
        cpv.enabled,
        cpv.value,
        cs.slug,
        cpv.id,
        cs.category_id,
        cs.country_id
  FROM  olx_catspec_slugs cs
  JOIN  olx_catspec_possible_value cpv ON cpv.id = cs.possible_value_id 
  WHERE cpv.enabled = 1 
  AND   country_id = 162 
  AND   category_id = 322
  AND   cpv.field_id = 53;  --field_id = 53 son los opcionales de primer nivel
```
