# Acercándonos al uso del terminal y {bash}

Para esta primera parte trabajaremos en el terminal y como un acercamiento aprenderemos como ocupar algunos comandos

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

# Apuntes: 

- `ls`<- ocupamos ``$ls -lSh`` (para ordenarlo por tamaño, donde nos mostrara los datos por tamaño MB y KB)
- `mkdir`<- ocupamos este comando para poder hacer un nuevo directorio ``$mkdir -p`` (nos sirve para poder hacer nuevos directorios a pesar de que ya existan)
- `cp`<- es un comando que nos permite copiar cosas y `$cp -r` nos permite copiar directorios
- `mv`<- es un comando para poder mover

> Tip: `mv` no es necesario usarlo con el flag `-r` para mover un directorio

- `rm`<- es un comando para eliminar directorios, pero ojo al usarlo ya que se puede eliminar directorios que no se quieren eliminar > **usar con precaución** `$rm -r` se usa para eliminar un directorio y todo lo que este posee

- `tar`<- comando de ultra compresión utilizado por Linux/Unix, es muy utilizado para datos genómicos y los genera archivos gzip y bzip (más comprimido que un zip) esta ultra compresión está dada por la comparación de datos símiles y comprimirlos

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


- `nano` `vi` `touch`<- nos permite crear archivos directo desde la terminal
> La diferencia es que `touch` nos permite crear un archivo vacío y `nano` y `vi` nos deja crear archivos con contenido, como un `.txt`, la única diferencia es el cómo se ocupa vim o simplemente texto
> Para volver a abrir el archivo `.txt` se puede usar el mismo comando `nano "nombre del archivo"`
> La diferencia con `touch` es que nos permite crear un directorio vacío

- `curl` nos sirve para poder bajar archivos al computador o para transferir archivos FASTA de secuencias individuales o secuencias de genomas completos y se anota como `$ curl (opciones) (direcciónURL)`
- `*` nos permite buscar archivos que tengan los caracteres que están antes o después del `*`
ejemplo en la carpeta Maiz colocar `$ ls *.bed` nos va a permitir encontrar archivos que posean la marca .bed

> $ ls *. bed
> 
> ejemplo_final.bed          
> nuevos_final.bed

- `?` es parecido a "*" pero en este caso nos va indicar solo un carácter, es decir en el ejemplo de abajo usamos b y 2 caracteres cualquiera
> $ ls *.b??
>
> ejemplo_final.bed
>
> nuevos_final.bed
>
> nuevos_final.bim

- `[]` nos permite agrupar términos de búsqueda, en el ejemplo de abajo le estamos indicando que son solo caracteres, ahora si lo usáramos al revés `$ ls *[a-z].bed` y tuviéramos un archivo con un numero antes del "." no nos lo va a mostrar pero si le agregamos un `?` antes del punto le vamos a indicar que nos muestre cualquier carácter entre "]" y él "."   
> $ls [a-z]*.bed
>
> ejemplo_final.bed
> 
> nuevos_final.bed

> Nota: estos comodines se pueden combinar entre sí

- `more` nos permite poder ver el archivo en una lista hacia abajo y para poder salir hay que ocupar el `q`, podemos ver los archivos hacia abajo con las flechas y podemos ocupar la barra espaciadora para poder ver el archivo completo esto igual se cumple para `less`

> Tip: al entrar con `more` y `less` al archivo de puede agregar `/(palabra)` que se quiera buscar, como en el caso del `archivo nuevos_final.fam` del archivo `Maiz` y `/teos` encontramos que los archivos están en la línea 163-164

- `head` nos muestra los primeros archivos, por default son los primeros 10
- `tail` nos permite ver los últimos archivos, por default son los últimos 10
> Tip: si ocupamos el flag `-n (número)` nos permite ver los superiores o inferiores archivos según el número que le demos

- `wc` nos indica un resumen del archivo que les indiquemos "(número de líneas), (número de palabras) y (número de caracteres del archivo)". Se indica `wc (nombre del archivo)`

- `cat` proviene de concatenar y nos permite pegar un archivo al final de otro
> ejemplo al usar `$cat nuevos_final.fam *.log` nos permitió pegar el archivo `.log` (solo hay un archivo .log) al final
> en el caso de como poder pegar más de un archivo lo podemos hacer simplemente dejando un espacio entre oraciones y agregar el nombre del archivo `$cat (nombre archivo uno) (nombre archivo dos) (nombre archivo tres)`

> Tip: para poder dejar los archivos en un archivo nuevo se puede `$cat (nombre del archivo) (nombre del archivo) > (nombre del archivo nuevo)` en caso que si se quieres sobrescribir se le pone `>>` en vez de `>` y para ver los archivos se ponen ocupa `more` o `less`

# `grep`

En este caso este comando es necesario separarlo por lo grande que es y las utilidades que nos puede dar
- `grep` es un comando que ocupa expresiones regulares para poder reformatear archivos, analizar ciertas muestras y no otras, además de identificar patrones cortos de DNA

> La forma de usarse es `$grep [acción] [expresión regular] [nombre del archivo]`
>
> Se puede usar tanto con **caracteres literarios** como letras y números, además con **metacaracteres** como los usados arriba `*`, `?`, `^`, entre otros.

- Las operaciones regulares se separan en **Operadores**, **Cuantificadores** y **Posicionadores**

#### Operadores

- [..] Nos sirve para generar una lista de caracteres, `[Bb]iology10[1234]` nos buscara aquellos que tengan la palabra biology como Biology, además de los que están enumerados 101, 102, 103, 104. Seria así `biology102` o `Biology104`
- [^..] Lista de caracteres que no queremos buscar 
- \w Nos permite buscar cualquier "carácter de palabra"
- \W Nos permite buscar cualquier "carácter **NO** palabra"
- \ Nos permite buscar los metacarateres ya que estos no se pueden usar por si solos, al usar esto se conoce como "escapar"
- | Significa "or" acepta un patrón u otro. p(err|at)o lo que nos va a permitir buscar tanto "perro" como "pato", a este símbolo se conoce como bash también
- (...) Grupos, que nos permite recuperar partes del patrón encontrado para ser usadas después

#### Cuantificadores
- * Cero o más ocurrencias del carácter anterior, 10*, va a aceptar "1", "10", "100", etc
- + Una o más ocurrencias del carácter anterior en este caso va a encontrar los mismos caracteres, pero no el "1" -> 10+ va a aceptar "10", "100", "1000", etc
- ? Van a aceptar la ocurrencia del carácter anterior, `patos?`, nos va a dar la cadena "pato" y "patos"
- {n,} Mínimo n veces el carácter anterior, seria 10{5,}, va a aceptar las cadenas "100000", "1000000", etc
- {n,m} Entre n y m veces el carácter anterior, seria 10{2,5}, va a aceptar las cadenas "100" y "10000"

#### Posicionadores
- < Nos indica el inicio de palabra, seria <GAAA, aceptaría "GAAACCTT", pero no "CCTCGA"
- > Nos indica el fin de la palabra o cadena, seria TCCA>, aceptaría "ACTTCCA", pero no "AACCTGTC"
- ^ Igual que los anteriores para el inicio de una línea
- $ Final de una línea

> En este caso usaremos el archivo tomatesverdes.fasta ubicado en `BioinfinvRepro-master/Unidad1/Prac_Uni1/Tomates`
>
> Es un archivo FASTA que posee 5 secuencias de DNA y el encabezado de las secuencias es `>gi|156629009|gb|EF438952.1| Physalis philadelphica isolate P059 maturase K (matK) gene, partial cds; chloroplast`

En este caso con `grep` podemos encontrar y obtener información de diferentes archivos aún más grandes que el archivo `tomatesverdes.fasta`

- Con `grep` a secas y si le señalamos algún carácter entre comillas podemos buscar u obtener la información que contenga ese carácter

> En el caso de buscar los encabezados de `jitomate.fasta` tenemos que son solo 3 secuencias y posee el siguiente encabezado `>gi|385137316|gb|JQ412261.1| Solanum lycopersicum voucher BS0156 maturase K (matK) gene, partial cds; chloroplast`

- `grep -c` nos permite poder ver las líneas que presentan el carácter seleccionado que va entre comillas `$grep -c ">" (nombre del archivo)` en este caso nos podría mostrar cuantas líneas hay y estas corresponderían a las secuencias que hay del gen en concreto

- `grep -l` nos enlista los archivos en los cuales se encunetran la expresión buscada, pero no nos muestra las líneas

> Sí ocupamos `$grep -l Physalis *.fasta` nos muestra los siguientes archivos `tomates.fasta` y `tomatesverdes.fasta`

- `grep -i` nos permite buscar sin necesidad de preocuparnos por las mayúsculas/minúsculas

> `$grep -l physalis *.fasta` no nos va a mostrar ningún resultado ya que los nombres están escritos con mayúsculas, por eso al agregar el flag `-i`. Seria `$grep -li physalis *.fasta` nos mostraría los mismos que vimos anteriormente

- `grep -w` nos permite buscar palabras completas, es decir nos muestra exactamente lo que indicamos

> si usamos en comando `$grep iso tomatesverdes.fasta` nos va a mostrar todos los datos que contengan la sigla "iso" pero al usar `grep -w iso tomatesverdes.fasta` no nos va a mostrar nada porque no hay ningún dato que tenga en su nombre solo iso ya que son `isolate`

- `grep -E` nos permite encontrar una expresión regular completa. Es útil usarlo con el flag `-o` para mostrar solo la parte del texto encontrado que cumple con la expresión regular

> para buscar con `grep` y obtener el nombre la especie sin "|" ocupamos `$grep -Eo (el nombre de la especie`
 
> Tip: si queremos buscar los nombres de las secuencias de más de un archivo ocupamos el mismo `grep -Eo` pero esta vez agregamos los nombres de ambos archivos, por ejemplo con los archivos `tomatesverdes.fasta` y `jitomate.fasta` ocupamos el siguiente comando `$grep -Eo "\| \w+ \w+" tomatesverdes.fasta jitomate.fasta` y si queremos guardar los nombres en un nuevo archivo ocupamos el comando `>` de la siguiente manera `$grep -Eo "\| \w+ \w+" tomatesverdes.fasta jitomate.fasta > mezclas.txt`, de esta manera tendremos un archivo de texto que contenga los nombres de las especies de las diferentes secuencias contenidas en ambos archivos

> **Consular como hacer las `secsIDs`**

## Redirección con bash

- `>` nos permite llevar uno o más archivos a un archivo en específico o uno nuevo

> Tip: Sí utilizas el `>` y el archivo ya existe este se va a eliminar, pero para evitar esto hay que usar `>>` lo que va a permitir que se agreguen los datos al final

> Nota: Utilizamos `sed` para poder sustituir "Solanum Lycopersicum" del archivo tomates.fasta por "jitomate" se hace con el siguiente comando `$sed 's/Solanum lycopersicum/jitomate' tomates.fasta`

- `|` la utilización de este comando nos permite utilizar otros comandos a la vez
> Por ejemplo `$ls | wc -l` para que nos indique el número de los archivos que hay
>  
> O usar el `$cat *.fam | more` nos muestra de forma conjunta todos los archivos `.fam` y la información completa

> Tip: Sí utilizas el comando `history` te muestra los comandos que has escribido y si lo combinas con `|` y `grep` puedes encontrar cuantas veces se ha usado lo que busques, por ejemplo `$history | grep -Eo "less"` y nos muestra cuantas veces hemos usado el comando `less` en el historial

## Loops con bash

Estos comandos permiten repetir una serie de comando con diferentes variables de una lista, en donde el comando después del `for` nos indica como el elemento de una lista

> `$for [letra o símbolo con el cual identificaremos las siguientes variables] in [las variables]`

> $ for x in adenina citosina guanina timina; do
> echo "La $x es una base nitrogenada"
> 
> done
>
> La adenina es una base nitrogenada
> 
> La citosina es una base nitrogenada
> 
> La guanina es una base nitrogenada
> 
> La timina es una base nitrogenada

#### **Datos extras**

- Los datos se separan por espacio
- Para referirnos al elemento, letra o símbolo del primer [..] ocupamos `$`

> Tip: ocupamos comillas para poder referirnos a una frase en vez de una palabra
> `;` nos permite separar lo que estamos pidiendo de los comandos `for x in {1..100};do` + `mkdir directorio$x; done` esto nos hizo directorios con el nombre directorio desde el 1 - 100 y para eliminarlos ocupamos `$rm -r directorio{1..100}`

## **Definir variables**

Para los `for loops` tambien podemos ocupar variables definidas anteriormente y sin necesidad de ponerlas en el comando de `for loop` 

> Tip: para usarse al armar la variable esta no debe ire separada de signo igual `$ ladra=guau` y luego se agrega al `for loop`

> $ ladrar=guau
> $ for c in perro perrito; do
> 
> for> echo El $c hace $ladrar
> 
> for> done
> 
> El perro hace guau
>  
> El   perrito hace guau

> Tip: **lograr armar un directorio en `Tomates/verdesFritos` con `for loop` y poseer una variable externa**

## Crear arrays y utilizarlos como una lista en un loop

Los arrays son una lista y se generan parecida a las variables

> `$ l=( perro perrito )`

Luego de eso hay que definir en nuesto loop que `l` es un array y para decirle esto al loop hay que usar la anotación `${l[@]}`

> for i in ${l[@]}; do echo El $i hace guau; done
> 
> El perro hace guau
> 
> El perrito hace guau

En este caso tambien podemos ocupar la variable como un comando `grep`, usando la siguiente configuracion `[letra para una array]=($(comando))`

> a=($(grep -Eo "\w+_[0-9]*" nuevos_final.fam))
> 
> for i in `${a[@]}`; do echo Hacer algo con la muestra $i; done
>
> En el archivo `Prac_Uni1/Maiz` 
> 
> Con esto le agregara el "Hacer algo con la muestra" a todos los nombres de los datos contenidos en `nuevos_final.fam`

> Tip: **buscar bien como poder hacer una variable desde un comando**

A veces los array presentan problemas, pero como los datos son tantos es muy dificil verlos por lo que se prefiere mejor leer los elementos directo a un archivo

> `grep -Eo "\w+_[0-9]*" nuevos_final.fam > muestras.txt`
> 
> (para poder ver los nombres del archivo en un archivo nuevo .txt)
> 
> `for i in $(cat muestras.txt); do echo Hacer algo con la muestra $i; done`
> 
> (para usar `for loops` y asi poder darle un agregado a nuestros datos, pero estos se van a borrar a no ser que los guardemos en un documento
>
> `for i in $(cat muestras.txt); do echo Hacer algo con la muestra $i; done > muestras2.txt`
> 
> (la parte final de esta linea nos deja poder llevar los datos extraidos a un archivo nuevo .txt

##### Ejercicios

1.- `grep -Eo "\w+_[0-9]*" nuevos_final.fam > nombres_nuevosfinal.txt` con esto podemos crear un archivo .txt con los combres de los datos de `nuevos_final.fam`

2.- `for i in {A..D}; do mkdir Pob$i; done` y para eliminarlos `rm -r Pob{A..D}`, pero para poder armar un archivo que tenga nombre Pob{A..D} y que dentro de el contenga un archivo de texto que se llame igula que el directorio hay que ocupar el siguiente scrip `for i in {A..D}; do mkdir -p Pob$i/Pob$i.txt; done`
