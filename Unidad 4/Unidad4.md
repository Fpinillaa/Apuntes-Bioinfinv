# Introducción al software especializado 

Los software especializados que permiten realizar operaciones complejas con datos genéticos, por ejemplo VFCtools se define como:

"vcftools es un conjunto de funciones para usar en datos de variación genética en forma de archivos VCF y BCF. Las herramientas proporcionadas se utilizarán principalmente para resumir datos, ejecutar cálculos sobre datos, filtrar datos y convertir datos a otros formatos de archivo útiles."

Para más información revisar se aconseja revisar los diferentes software en los siguientes links: [VCFtools](https://vcftools.github.io/index.html), [Stacks](http://catchenlab.life.illinois.edu/stacks/manual/), [Mothur](https://mothur.org/wiki/) o [Trinity](https://github.com/trinityrnaseq/trinityrnaseq/wiki/Running%20Trinity).

## Documentación de software especializado

Estos software poseen documentación especializada, la cual comprende del manual y diferentes tutoriales para los diferentes programas, cabe destacar que los manuales están presentes para todos los software no así los tutoriales que pueden o no tener estos software.

En el caso de los manuales estos se pueden obtener directamente desde el terminal `(>_)` con el comando `$ man (nombre_del_software)` o directamente desde la web. Estos manuales son iguales a los manuales de los diferentes paquetes tanto de `bash` como de `R`, en el cual nos presentan una descripción del software, los usos de sus comandos y unos ejemplos breves.

***Terminal***
![](man_vcf.png)

***Web***
![](man_vcf_inter.png)

### Instalación 

los diferentes softwares se instalan mediante líneas de comando de manera directa en un terminal (estos software están preferentemente para sistemas Linux y MacOS), además estos software están escritos en diferentes lenguajes como C++, phyton, entre otros. Debido a esto la instalación de estos programas no se hace con solo dar clic, si no que posee una serie de pasos para instalarse.

#### Pasos:

1) Buscar la versión más actualizada del software, estos por lo general están en su propia página o en un GitHub como este con las instrucciones y datos ya mencionados anteriormente

En este caso nos vamos a centrar en [VCFtools](http://vcftools.github.io/index.html) que fue el que instale.

2) En la página nos centraremos en buscar la seccion que diga ***Download*** (en algunos puede aparecer como ***Install***), esto te llevara a descargar un archivo `.tar` o un comando para poder bajar el programa desde GitHub

      ![](vcfdescarga.png)

3) Bajamos el codígo.

Al bajarlo podremos visualizar los contenidos del archivo `.tar` podremos visualizar diferentes archivos:

![](vcfread.png)

4) En el archivo `.tar` como se muestra vemos que contiene un archivo de texto llamado ***README*** (este archivo también podría ser un Markdown). Este es el primer archivo que se debe revisar ya que en el vienen las instrucciones de instalación y los pasos a seguir

![](readme.png)

5) La instalación consiste finalmente en seguir los pasos que nos dice el README


#### Importante

- Lo anterior descrito corre para otros programas pero pueden haber variasiones en los terminos como README por INSTALL
- La instalación y los pasos a seguir pueden diferir entre los programas y a su vez dentro de los diferentes sistemas operativos
- La instalación puede requerir de los siguientes comandos (de hecho estan en las instrucciones del README de VCFtools)
  * `sudo`
  * `./configure`
  * `make`
  * `make install`
> Dato: 
> - Estos comandos son importantes para poder correr el script del programa que queremos instalar y asi posteriormente poder utilizarlo como un programa completo
> - `sudo` es el comando super poderoso que nos permitira realizar o usar un comando con los permisos de super administrador donde nos pedira que autorisemos su uso mediante la clave de usuario
> - Para mas informacion de que hacen los diferenes comandos mencionados revisar el repositorio principal ([BioinfinvRepro](https://github.com/ravuch/BioinfinvRepro)) o bien en el siguiente [link](https://thoughtbot.com/blog/the-magic-behind-configure-make-make-install)

#### Como lo instale

En mi caso la instalación resulto ser no tan simple, debido a que el equipo que ocupo posee `MacOS Monterrey` y al parecer a este le falta algunos comandos por lo que los tuve que instalar de manera externa.

Por lo que el consejo dado por el [BioinfinvRepro](https://github.com/ravuch/BioinfinvRepro) al comienzo es sumamente importante "siempre buscar en foros".

El problema que se me presento fue un error con el archivo `autogen.sh` el cual decía lo siguiente `$./autogen.sh line 3 autoreconf command not found vcftools`, y la resolución para este problema fue la falta de los siguientes comandos:

- `autoconf`
- `pkg-config`
- `libtools`
- `automake`
- `zlib`

Los cuales para instalarlos necesitaba la instalación de `brew` o `MacPorts` los cuales son administradores de paquetes para el ambiente Mac y permiten la utilización, instalación y actualización de diferentes líneas de comando. En mi caso instale [`MacPorts`](https://www.macports.org/install.php) con el cual pude instalar los comandos necesarios, además poseen una forma más simple de instalación de VCFtools con el siguiente comando por si no se quisiera realizar la instalación manual `$sudo port install vcftools`

> Dato: La página [ports.macports](https://ports.macports.org/) posee un sin fin de programas y comandos para el ambiente Mac, con una forma de instalación más simple mediante comandos `$port`

> Al buscar otros programas software asociados a bioinformática y específicamente genética encontre `Bowtie`, el cual es una ultra rápida herramienta de lectura de alineamientos cortos de DNA, el cual posee una documentación de instalación que se puede observar a simple vista, pero no posee tutorial y si todo resultara de buena manera (cosa difícl que pase, en fin la ley de Murphy) puede ser que se demore lo que necesita el equipo para descargar y procesar los datos que podrían ser unos 15-30 min.
