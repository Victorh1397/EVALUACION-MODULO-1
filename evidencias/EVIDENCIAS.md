## Evidencias Requeridas configuracion rama main

Es importante bloquear la rama principal para evitar que por accidente se altere la versión del software de producción. También permite que otros desarrolladores revisen el código mediante la Pull Request antes de ir a producción, así como realizar pruebas automatizadas para detectar algún fallo o error.

He configurado la opción Require a pull request before merging para que cualquier cambio en la rama main sea hecho mediante un pull request.

![Require PR before merging](Proteccion_Rama_Main_1.jpg)

Adicionalmente he seleccionado Do not allow bypassing the above settings para evitar que incluso yo como administrador pueda de forma accidental hacer un push directamente a la rama main, de esta forma saldrá un error si quiero hacer un git push origin main.

![Do not allow bypassing](Proteccion_Rama_Main_2.jpg)


Por último muestro un intento de hacer un push en la rama main lo cual arroja un error en Git. Esto demuestra que la configuración fue realizada apropiadamente.


![Error en Git](Error_Git_Proteccion_Rama.jpg)

Ahora deshago el commit de la rama principal y subo el archivo de evidencias a github, lo cual realizo creando una rama feature/evidencias y haciendo push.


![push de evidencias 1](Añadiendo_archivo_evidencias_1.jpg)


![push de evidencias 2](Añadiendo_archivo_evidencias_2.jpg)


## Configuracion de .gitignore

Empiezo creando la rama feature/gitignore. Luego creo el archivo .gitignore y le agrego las reglas correspondientes las cuales son ignorar los .log y el directorio '__pycache__/'.

Los archivos .log son registros que van creciendo continuamente y no aportan un valor adicional, mientras que __pycache__/ contiene archivos complilados de Python que dependen de la arquitectura de cada máquina por lo tanto tampoco conviene subirlos al repositorio.



![creando gitignore](Creando_archivo_gitignore.jpg)

Ahora creo un archivo .log y un .txt con la informacion de gitstatus para demostrar que Git está ignorando los archivos .log

![Creacion archivo log y txt](Demostracion_archivo_log_gitignore.jpg)

Se evidencia en el archivo gitignore-status.txt que el archivo log que cree no aparece en la lista de archivos detectados por Git.

![imagen gitignore-status.txt](imagen_archivo_gitignore_status.jpg)

