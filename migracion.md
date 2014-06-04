MIGRACION
---------

###CSV

1. los archivos deben tenes encabezado
2. los archivos deben estar separados por "," (coma)
3. todas las reglas deben tener una categoria default, la cual **debe** ser proporcionada por la gente de producto.
4. de haber archivos de keywords controlar que los nombres en el archivo de migracion sea **exactamente** los mismos

####COMMIT
1. AMBIENTES Y COMMIT
	1. tanto para l ambiente de "DEV", como en "TESTING" los archivos **.csv** deben comitearce a el repo de **olx-scripts** parados en el branch de **dev**
		*tipsutiles para git: *` git branch`
							* `git checkout dev`
2. el archivo **.csv** de migracion debe colocarse en la carpeta *olx-scripts/one-time-scripts/sas/cattree/files/(id_pais)/*
3. si tiene archivos de keyword deben colocarse en la carpeta *olx-scripts/one-time-scripts/sas/cattree/files/(id_pais)/keywords/*
 