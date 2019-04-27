# Descripción de la problematica.

Se tiene un conjunto de noticias en texto libre pre-procesadas y limpias, sobre el cual se desea calcular:

Índice Invertido, donde por cada palabra que se ingrese por teclado, se liste en orden descendente por frecuencia de palabra en el contenido <content> de la noticia, las noticias más relevantes. Listar máx 10 <frec,doc_id,title>.

        frec = frecuencia de la palabra en la noticia <id>
        id = id de la noticia
        title = título de la noticia.

# 1. Análisis
## 1.1 Descripción

La función del algoritmo propuesto es dado 1 documentos que contiene diferentes noticias, listar los 10 registros con la mayor frecuencia de la palabra ingresada

Para esto se define una función encargada de crear diccionarios(Estructura de datos en python) por cada noticia,
creando con esto conjuntos de llave - valor, teniendo como llave el identificador del articulo ("Id") y como valor la frecuencia de este. ("Frec").

![](./dict1.png)

Adicionalmente a ello, por cada palabra identificada en el articulo se crea un diccionario mayor, dónde se definirá como llave 
la palabra actual y como valor el resultado del diccionario anterior. 

![](./dict2.png)

Al momento de buscar la palabra, la estrategia es bastante simple, se define una función la cual se encarga de convertir en 
una lista los resultados brindados al buscar en el diccionario la palabra. 

y de esta forma, con una lista de [Id,Frecuencia], aplicamos una función lambda la cual ordena descendentemente con base al segundo item del arreglo.

![](./order.png)

## 1.2 Definición de tecnología de desarrollo para el algoritmo:

* Lenguaje de Programación: Python - PySpark
* Técnica Aplicada: Diccionario de diccionarios con filtro lambda. 
