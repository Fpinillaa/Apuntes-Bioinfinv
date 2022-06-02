# Tareas-Bioinfinv
Repositorio con tareas y anotaciones para el repositorio Bioinfinv

En la primera parte realizaremos las tareas referentes a la Unidad 1, en la que trabajaremos en el terminal (es un acercamiento a como ocupar algunos comandos del terminal)

## Tenemos códigos disponibles de ubicación que son: 

- ``pwd`` (nos da la ubicación de nuestro directorio)
- ``cd`` (nos permite cambiar el directorio)
- ``cd ~`` (es un comando corto para llevarnos al inicio de todo sin la necesidad de escribir todo el recorrido)
- ``../`` (es para poder volver una carpeta atrás en nuestro directorio)
- ``./`` (nos permite observar el directorio actual)


## Tenemos códigos para observar nuestro directorio actual

- ``ls`` (nos permite ver el entorno del directorio y donde nos encontramos)
- ``ls -l`` (nos permite poder enlistar los datos, pero con información de si es un archivo o un directorio y los permisos que posee)
- ``ls -lt`` (lo que nos permite ordenar los datos enlistados por fecha)

> Tip: para usar estos comando y no saber qué hace cada uno se puede copar el comando man seguido del comando para así poder encontrar el manual del comando (es muy similar a ? de R)

Con esto podemos pasar a realizar los ejercicios

# Ejercicios: 

``ls``<- ocupamos ``$ls -lSh`` (para ordenarlo por tamaño, donde nos mostrara los datos por tamaño MB y KB)

``mkdir``<- ocupamos este comando para poder hacer un nuevo directorio ``$mkdir -p`` (nos sirve para poder nuevos directorios a pesar de que ya existan)

`cp`<- es un comando que nos permite copiar cosas y `$cp -r` nos permite copiar directorios

`mv`<- es un comando para poder mover
> Tip: `mv` no es necesario usarlo con el flag `-r` para mover un directorio

`rm`<- es un comando para eliminar directorios, pero ojo al usarlo ya que se puede eliminar directorios que no se quieren eliminar > **usar con precaución** `$rm -r` se usa para eliminar un directorio y todo lo que este posee

`tar`<- comando de ultra compresión utilizado por Linux/Unix, es muy utilizado para datos genómicos y los genera archivos gzip y bzip (más comprimido que un zip) esta ultra compresión está dada por la comparación de datos símiles y comprimirlos

> `tar -cvzf` <- `c` Crea un nuevo archivo .tar.

>               `v` Muestra el progreso de la compresión

>               `z` Especifica que queremos un `.gzip.`

>               `f` Nombre del archivo `.tar.gz`
>               y al final de la escritura se le indica el archivo que se quiere comprimir

>               ej: `$ tar -cvzf Maiz.tar.gz Maiz` `$ tar -cvzf "como se va a llamar" "el archivo"`

> `tar -xvf`<- `x` nos inidica que se va a extraer
>              `v` ver cómo va la descompresión
>              `f` el archivo que queremos descomprimir

> `tar -tvf`<- nos permite ver el contenido sin descomprimirlo

`nano` `vi` `touch`<- nos permite crear archivos directo desde la terminal
> La diferencia es que `touch` nos permite crear un archivo vacío y `nano` y `vi` nos deja crear archivos con contenido, como un `.txt`, la única diferencia es el cómo se ocupa vim o simplemente texto
> Para volver a abrir el archivo `.txt` se puede usar el mismo comando `nano "nombre del archivo"`









