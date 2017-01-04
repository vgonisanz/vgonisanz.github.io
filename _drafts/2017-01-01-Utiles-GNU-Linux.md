# Cosas útiles del terminal de GNU/Linux

Para los que usamos la terminal de linux a diario, nos congratula dominarla. Sus posibilidades son infinitas, y muchas veces no sabemos sacarle todo el provecho que queremos por falta de tiempo o interés. Aqui intento recopilar unos cuantos trucos que siempre olvido y que vienen muy bien.

## Búsqueda de un string dentro de un fichero desconocido

Si necesitas buscar un trozo de texto en un path o subpath, esto te resultará útil:
```
grep -rnw '/path/to/somewhere/' -e "pattern"
```
* -r or -R implica búsqueda recursiva.
* -n implica número de linea en el output
* -w implica que el patrón est completo.
* -l (lower-case L) implica que solo nombra los ficheros.
* --exclude, --include, --exclude-dir o --include-dir 
Por ejemplo:
```
grep --exclude=*.o --exclude-dir=output -rnw '.' -e "define"
```
Buscará todos los ficheros que contengan la palabra define desde el punto donde estamos en el terminal, excluyendo carpeta output y ficheros .o.
