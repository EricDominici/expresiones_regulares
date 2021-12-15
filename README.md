# Expresiones Regulares

Esta practica te va a enseñar qué son las expresiones regulares y cómo utilizarlas. Por ejemplo aplicaciones de búsqueda y filtrado, las expresiones regulares son extremadamente potentes,
aprende a utilizarlas y tendrás una gran herramienta digital para cualquier área a la que te
dediques.
Las expresiones regulares son patrones de caracteres que te permiten ir seleccionando o
descartando datos en un archivo de texto como por ejemplo csv , o en una línea o un input ,
según coincidan o no con este patrón.
Prácticamente todos los lenguajes de programación tienen librerías o módulos para manejar
expresiones regulares.
Las expresiones regulares pueden ser muy complejas pero no son nada difíciles de entender.
A través de esta practica, sin tecnicismos y con ejemplos puntuales, vamos a aprender a
utilizarlas para que sean esa herramienta que siempre nos ayude, y sea la primera para
solucionar problemas de grandes cantidades de datos en string .

***Tambien podran observar como en este repositorio s epuden visualizar todas las respuestas a los 15 niveles***

> Una pagina que les podria ayudar si quieren saber mas al respecto de de las expresiones regulares visitar"https://lenguajejs.com/javascript/caracteristicas/expresiones-regulares/"

## Sección 1: Nuestro entorno de pruebas 

En esta seccion nos muestra que podemos utilizar Visual Studio Code (VSC) para probar los distintos tipos de expresiones regulares

## Sección 2: Introducción al lenguaje de Expresiones Regulares

**Buscar cualquier caracter con** **.** **(el punto de toda la vida)** 

Encuentra todo lo que sea un carácter. 

**Paso #1:** El punto es muy útil cuando no te importa que carácter sea que forme tu patrón, como en la sección anterior la expresión .e buscaba cualquier texto que tuviera un carácter sea letra, numero o caracteres especiales como el espacio en blanco, todas esas combinaciones coinciden con tu ExReg. Ejemplo si quieres buscar el patrón e..b buscara las coincidencias donde tengas e seguido de dos caracteres cualquiera terminados en b 

![img](https://lh4.googleusercontent.com/C4TmnogukiF9VbwG40B2qkv4ynJkJ584GLd9YD0hE_TAIdHmIPxORlv4NlQmLK4hfU-Bdjh21ounqeIvdIEe_PhnVlotsJ8-ipNn7vQrS0kr9kZ8YVuELmU1noShwbcMv7Z0U-EH)

**Nota**: En nuestro proyecto la palabra enables tiene coincidencia con nuestra expresión regular e..b . 

**Paso #2:** Si quieres buscar palabras con mas de 3 caracteres puedes usar la expresión regular ... tendrá coincidencia con cualquier coincidencia de 3 caracteres consecutivos. Pero notaras algo extraño, como que prácticamente toda la linea en tu archivo coinciden. 

![img](https://lh5.googleusercontent.com/zYxxXJtkJ7GukfVy4y9vRH9LACngSbZQiOJtLlnzBK5nd1UdEchTm7YucEAzPLYjwNEWxKZQ0LKrRY7uNTRwzedaNsqdqOd_7px4egJn3Qhur3OLLnqS6jxloe0ppPjLCHPI9imp)Lo que sucede es que nuestra expresión regular va tomando linea por linea los grupos de tres caracteres incluyendo los espacios en blanco , si tu linea tiene un numero de caracteres divisible entre 3 tendrás la linea seleccionada completamente, pero en algunos casos no 

posee un numero de caracteres divisibles entre 3 y dejara uno que otro fuera de la selección, ejemplo en la linea 3 de la imagen anterior queda la s fuera de la selección.

Sigue practicando con el uso del . hasta logres entenderlo, recuerda usa el método científico hipótesis, prueba y observación. 

**Buscando por clases** **\d \w \s \D \W \S** 

**Buscar dígitos con** **\d** 

Encuentra todos los dígitos de 0 a 9 . 

\d es equivalente a poner [ 0-9] . 

Si en vez de \d , usamos por ejemplo [0-2] nos encontrará solamente los dígitos de 0 a 2 . Podemos usar \D para encontrar justo lo contrario, todo lo que no son dígitos. 

**Buscar caracteres de palabras** **\w** 

Encuentra todo lo que puede ser parte de una palabra, tanto letras (minúsculas o mayúsculas) como números. 

\w es equivalente a poner [a-zA-Z0-9] . 

Si en vez de \w , usamos por ejemplo [a-zA-Z] nos encontrará solamente las letras. Podemos usar \W para encontrar justo lo contrario, todos los caracteres que no son parte de palabras. 

**Buscar Espacios** **\s** 

Encuentra todos los espacios (los saltos de línea también son espacios). 

Podemos usar \S para encontrar justo lo contrario, todo lo que no son espacios. 

**Paso #3:** La siguiente expresión regular coincide con el código de colores en Hexadecimal que solemos usar en nuestro css , la expresión es #[a-fA-F0-9]{3,6}  

Crea un archivo colores.md y prueba la expresión regular anterior. 

yellow #ff 

navy #000080 

blue #0ff 

teal #0z8080

![img](https://lh3.googleusercontent.com/MEi8kfSYJ5dioADAPbwrQyd131_0g7CmI2L82_luWWOkek77fdij1mpaoGE7MsiTr-SL_wyrLFHKUSGx1h92VTsFqEddaqSAICFhf5NcqAKFwDrrEfWVE-Ph7wo-X1Q8onErFQtV)

**Notaras** que se obtienen 2 resultados del archivo colors.md , el primero es navy #000080  y blue #0ff que coinciden con nuestra expresión regular gracias {3, 6} que permite buscar coincidencias de 3 y 6 caracteres consecutivos. El caso de yellow #ff queda fuera porque no posee 3 o 6 caracteres luego del carácter # , solo posee 2. El caso de teal #0z8080 no coincide porque posee un carácter z , #[a-fA-F0-9] solo permite caracteres en minúsculas o mayúsculas entre a-f o A-F o entre 0-9 . 

**Buscando con delimitadores** **+ \* ?** 

**Delimitadores**: 

(*) : Cero o más veces 

(?): Cero o una sola vez 

(+): una o más veces. 

Aplican al carácter o sentencia que preceden 

**[a-z]?** : Esto es que puede estar **una sola vez** o ***no estar\*** una letra minuscula de la **(a)** a la **(z)**. 

**\d\***: Esto es que puede estar ***muchas veces\*** o ***no estar\*** un **dígito**. 

**\d+**: Esto es que puede estar ***muchas veces\*** o ***una sola vez\*** un **dígito**.

![img](https://lh3.googleusercontent.com/R2iLKfHBS2AjcgLbJ3_wQXFmx07XJeS9Plzq-EWCbMMQsyPHFboSnB8Bw1YoKWFNFlNkj-Uj4U3cpm4KQyS-AoRMVC2v3BYpXfgdoZyRwp0m6fpXzoL33w2HevM1ggkMi_cD4f5D)

![img](https://lh3.googleusercontent.com/zCj3-kXbDiel7LhSNl9WANht0YOtVEwrND9XFDZWOjmBBrUgFg8Fh_jzJklbZxaFqs_urZYNGMihbssIoGSXExz2Mn1voR-wHGZkcwYJCncx33DwBDOnnr129UDYCbJ6ec8G9Y-i)

## **Sección #3: Aprende jugando** 

En esta seccion utilizaremos un curso didactico, que tiene la finalidad de enseñarnos las expresiones regulares mientras jugamos

> si quiere participar en este maravilloso juego "https://manzdev.github.io/regex-people/"
