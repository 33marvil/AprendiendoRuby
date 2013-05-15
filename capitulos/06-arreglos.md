# Arreglos y Diccionarios

En la mayor�a de los lenguajes, tenemos arreglos. Ruby los tiene, y son din�micos: pueden variar de tama�o. Se
comportan como las listas de Java y .NET. Como las variables, no tienen tipo: cada elemento es libre de
tener cualquier valor, hasta otro arreglo. Los arreglos son objetos, que pertenecen a una clase, se pueden
crear y tienen m�todos asociados. Adem�s de soportar arreglos, Ruby maneja diccionarios, donde los elementos 
se acceden por clave, no necesariamente num�rica.

## Arreglos

Un arreglo es una colecci�n secuencial de items, y cada item puede ser referenciado por un �ndice. Vean que
es importante lo de ser secuencial: hay un orden en los items. Si no fuera as�, ser�a una simple colecci�n
de items, donde el orden no importa. 

> Nota: Uso la palabra colecci�n, porque no necesariamente los items forman un conjunto. En un conjunto los
elementos no se repiten

```ruby
numeros = ['cero', 'uno', 'dos', 'tres']
numeros[0] # => retorna 'cero'
numeros[2] # => retorna 'dos'
```
(A Completar)

### Creando Arreglos

Los arreglos son objetos, y son objetos de la clase Array. Se pueden crear como instancias de la clase
`Array`. El `new` de esa clase tiene variantes:

```ruby
arreglo = Array.new      # un arreglo vacio
arreglo = Array.new(2)   # un arreglo de dos elementos [nil, nil]
arreglo = Array.new(2, 'Hola')  # un arreglo con dos elementos repetidos ['Hola', 'Hola']
```

(A Completar)

### Arreglos Multidimensionales

Un elemento de un arreglo, a su vez, puede ser un arreglo. Esa es la forma de tener arreglos multidimensionales
en Ruby. Como en el caso de los unidimensionales, cada una de las dimensiones es variable.

(A Completar)

### Iterando sobre Arreglos

(A Completar)

## Diccionarios

```ruby
miobjeto = Object.new
```

(A Completar)