# Evidencias Requeridas 

## 1. Creación del repositorio y primer commit

A continuación se muestra la creacion del repositorio y el primer commit en Git con su respectivo archivo README.md

![creacion repositorio](image-1.png)


Creación del repositorio en GitHub

![repo nuevo github](image-2.png)

Publicación del repositorio en GitHub

![subiendo repo](image-3.png)


## 2. Configuracion rama main

Es importante bloquear la rama principal para evitar que por accidente se altere la versión del software de producción. También permite que otros desarrolladores revisen el código mediante la Pull Request antes de ir a producción, así como realizar pruebas automatizadas para detectar algún fallo o error.

He configurado la opción Require a pull request before merging para que cualquier cambio en la rama main sea hecho mediante un pull request.

![Require PR before merging](Proteccion_Rama_Main_1.jpg)

Adicionalmente he seleccionado Do not allow bypassing the above settings para evitar que incluso yo como administrador pueda de forma accidental hacer un push directamente a la rama main, de esta forma saldrá un error si quiero hacer un git push origin main.

![Do not allow bypassing](Proteccion_Rama_Main_2.jpg)


Creando el archivo de EVIDENCIAS.md

![creando EVIDENCIAS.md](image-4.png)



Por último muestro un intento de hacer un push en la rama main lo cual arroja un error en Git. Esto demuestra que la configuración fue realizada apropiadamente.


![Error en Git](Error_Git_Proteccion_Rama.jpg)

Ahora deshago el commit de la rama principal y subo el archivo de evidencias a github, lo cual realizo creando una rama feature/evidencias y haciendo push.


![push de evidencias 1](Añadiendo_archivo_evidencias_1.jpg)


![push de evidencias 2](Añadiendo_archivo_evidencias_2.jpg)


## 3. Configuracion de .gitignore

Empiezo creando la rama feature/gitignore. Luego creo el archivo .gitignore y le agrego las reglas correspondientes las cuales son ignorar los .log y el directorio `__pycache__/`.

Los archivos .log son registros que van creciendo continuamente y no aportan un valor adicional, mientras que `__pycache__/` contiene archivos compilados de Python que dependen de la arquitectura de cada máquina por lo tanto tampoco conviene subirlos al repositorio.



![creando gitignore](Creando_archivo_gitignore.jpg)

Ahora creo un archivo .log y un .txt con la informacion de gitstatus para demostrar que Git está ignorando los archivos .log

![Creacion archivo log y txt](Demostracion_archivo_log_gitignore.jpg)

Se evidencia en el archivo gitignore-status.txt que el archivo log que cree no aparece en la lista de archivos detectados por Git.

![imagen gitignore-status.txt](imagen_archivo_gitignore_status.jpg)

Ahora subo a GitHub todo lo que este pendiente por subir, haciendo git add ., el correspondiente commit y push

![push gitignore-status.txt](Push_Gitignore-status.jpg)

En GitHub ahora tengo el el Pull Request de la rama feature/gitignore

![PR gitignore-status.txt](PR_feature_gitignore.jpg)


Haciendo Merge de ese Pull Request 


![Merge gitignore-status.txt](Merge_PR_feature_gitignore.jpg)


![Merge completado gitignore-status.txt](Merge_PR_feature_gitignore%20(COMPLETED).jpg)



## 4. Creación de ramas

Actualizando la rama main en local mediante git pull

![git pull](4_Pull_Origin_Main.jpg)

Creando la rama feature/suma

![creando feature/suma](4_Creando_Rama_feature_suma.jpg)

Definiendo el archivo operations.py y las funciones info y suma. Hay que considerar que en el push utilice -f puesto que anteriormente habia hecho un commit con un nombre incorrecto del archivo operations.py.

![push feature/suma](4_Push_feature_suma.jpg)


Creando la rama feature/resta, añadiendo las funciones info y resta al archivo operations.py para luego hacer commit y push

![push feature/resta](4_Creacion_y_Push_feature_resta.jpg)


Ahora se aprecian los Pull Request de las ramas feature/suma y feature/resta en Github

![PR suma y resta](4_PR_Suma_Resta.jpg)


## 5. Simulación y resolución de un conflicto

Aceptando y mergeando la rama feature/suma

![PR suma](5_PR_Suma.jpg)

![Merge PR suma](5_Merge_PR_Suma.jpg)


Conflicto en pull request de feature/resta al intentar integrarse a main:

![Conflicto Resta](5_Conflicto_Merge_Resta.jpg)


Actualizando la rama main en local

![Actualizando main](5_Actualizando_Rama_Main.jpg)

Intentando el merge de la rama main dentro de feature/resta

![Conflicto Git merge](5_Conflicto_Git_Merge_Failed.jpg)


Se observa el conflicto en operations.py. 

![Conflicto en operations](5_Conflicto_en_Operations.jpg)



Entonces solucionamos el conflicto dejando la suma y la resta en operations.py

![Conflicto en operations resuelto](5_Conflicto_en_Operations_SOLUCIONADO.jpg)

Hacemos el commit y el push de la rama feature/resta

![push feature resta](5_push_feature_resta.jpg)


Ahora aparece sin conflicto la rama feature/resta en Github y está lista para hacer merge.

![mergeando feature resta](5_merge_feature_resta.jpg)


Finalmente el merge ha sido exitoso

![merge feature resta completado](5_merge_feature_resta_completado.jpg)


Se crea el archivo git-log.txt:

![creacion git-log.txt](5_Creacion_git-log_txt.jpg)

![git-log.txt](5_capture_git_log_txt.jpg)


## 6. Automatizacion con Github actions

Actualizando rama main y creando nueva rama llamada feature/ci

![actualizando main y creando feature/ci](6_creando_rama_feature_ci.jpg)


Creando el archivo .github/workflows/demo.yml 

![creando .yml](6_Creando_yaml.jpg)

El archivo demo.yml queda con el siguiente contenido despues de editarlo en notepad. La idea es que el workflow_dispatch solicite el nombre completo y luego se ejecute la acción correspondiente mostrando ese nombre por consola.

![sintaxis archivo demo yml](6_archivo_demo_yml.jpg)


Subiendo los cambios al repositorio

![push_feature_ci](6_push_feature_ci.jpg)


Creando Pull Request

![Creando PR](6_Creando_PR.jpg)


Mergeando Pull Request

![Creando PR](6_Merge_PR.jpg)


Ejecutando manualmente el workflow desde GitHub Actions:

![Ejecutando_Workflow](6_Ejecutando_Workflow.jpg)


Se observa el workflow completado en Actions

![Workflow_Completado](6_Workflow_Completado.jpg)


Creación del archivo evidencias/action-output.txt :

![evidencias action output](6_Creando_evidencias_action-output.jpg)


Contenido del archivo action-output.txt (copiado desde Github Actions):

![contenido action output](6_contenido_action-output.jpg)


Copiando status badge desde Actions

![copiando status badge](6_copiando_status_badge_github.jpg)


Contenido del README.md despues de agregar el badge

![contenido README.md con status badge](6_contenido_nuevo_badge_readme.jpg)











