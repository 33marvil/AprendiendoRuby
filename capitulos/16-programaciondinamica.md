# Programaci�n Din�mica

Ya he mencionado al comienzo que Ruby es un lenguaje din�mico. Pero �qu� es lo que consideramos como
lenguaje din�mico?

Bueno, por una parte, Ruby es un lenguaje din�micamente tipado. Las variables y m�todos no tienen tipo,
sino que los valores que albergan y devuelven son los que son objetos de alguna clase. No hay variables
string o enteras, sino valores string y valores enteros. Lenguajes est�ticamente tipados son Java y C#.

Pero tambi�n Ruby es din�mico porque puede:

- Evaluar expresiones que se calculan u obtienen en ejecuci�n, en lugar de estar determinadas al momento
de lanzar el programa
- Modificar el propio programa en ejecuci�n

## Programas Automodificables

Una cosa es escribir un programa, y otra es ejecutarlo. En los lenguajes compilados, todo el c�digo
a ejecutar queda definido al escribirlo y compilarlo. Pero la mayor�a de los lenguajes interpretados
permite evaluar c�digo creado en el momento.

### El Gran `eval`

Esta funci�n ya definida en Ruby nos permite tomar un string y evaluarlo como c�digo Ruby. 
Por ejemplo, podemos pedir una l�nea por consola y evaluarla como expresi�n Ruby, si es v�lida:

```ruby
expresion = gets.chomp
eval(expresion)
```

Esto abre la puerta para que podamos, por ejemplo, tomar expresiones de campos de una base de datos, y evaluarlas
din�mica en nuestro programa. Y si lo que evaluamos implica definir un m�todo, una clase, u otro elemento
de programaci�n Ruby, estaremos modificando el programa en ejecuci�n. Ejemplo:

```ruby
eval('def foo; puts "foo"; end')
```
define un nuevo m�todo `foo` que podemos invocar de ahora en m�s.

### Otros Tipos de `eval`

(A completar: instance_eval, class_eval, module_eval)

### Definiendo un M�todo Din�micamente

Supongamos que tenemos que definir una clase Semaforo con un estado interno que se puede modificar
por m�todos:

```ruby
class Semaforo
    def rojo
        @estado = :rojo
    end
    
    def verde
        @estado = :verde
    end
    
    def amarillo
        @estado = :amarillo
    end
end
```

Ac� fueron tres estados, pero podr�an ser m�s. Hay otra forma de definir un m�todo, usando `define_method`
que espera dos par�metros: un s�mbolo con el nombre del m�todo a definir, y un bloque que sea el cuerpo
del m�todo. Veamos:

```ruby
class Semaforo
    [:rojo, :verde, :amarillo].each do |nombre|
        define_method nombre do
            @estado = nombre
        end
    end
end
```

(A completar)

## Fuentes Consultadas

- [Ruby: Dynamically Define Method](http://blog.jayfields.com/2008/02/ruby-dynamically-define-method.html)
- [Ruby Metaprogramming: Declaratively Adding Methods to a Class](http://www.vitarara.org/cms/ruby_metaprogamming_declaratively_adding_methods_to_a_class)
- [Ruby�s define_method, method_missing, and instance_eval](http://www.trottercashion.com/2011/02/08/rubys-define_method-method_missing-and-instance_eval.html)
- [How do you pass arguments to define_method?](http://stackoverflow.com/questions/89650/how-do-you-pass-arguments-to-define-method)



