# Bloques

Cuando hablamos de bloques, pensamos en l�neas de c�digo, como las que est�n dentro
de un `if` o un `for`. En Ruby, un bloque es algo m�s especial: un bloque es c�digo que se comporta
como un m�todo pero sin nombre. Podemos verlo como un m�todo an�nimo. Veamos un ejemplo

## �Qu� es un Bloque?

Nada mejor que ilustrar con c�digo. Los n�meros enteros tienen un m�todo que permite usar al valor
num�rico como valores para iterar:

```ruby
3.times do |i|
    puts i
end
```

La salida es
```
0
1
2
```

�C�mo funcion� esto? Pues bien, el m�todo `times` parece que no recibe nada como par�metro, pero en realidad,
recibi� un bloque de c�digo a ejecutar. Ese bloque comenz� con `do` y termin� en `end`.

Otra sintaxis, alternativa, es:

```ruby
3.times { |i|
    puts i
}
```
En este caso usamos llaves para encerrar al bloque de c�digo.

Otro ejemplo de pasar un bloque en una llamada, familiar cuando manejamos arreglos, es:
```ruby
arreglo = ['uno', 'dos', 'tres']
arreglo.each do |elemento|
    puts elemento
end
```

## Usando Yield

Podemos escribir un m�todo que reciba un bloque y lo ejecute, sin poner un par�metro expl�cito y usando
una nueva palabra `yield`. Ejemplo, extendamos a los n�meros enteros con una nueva funci�n:

```ruby
class Fixnum
    def mytimes
        for k in 1..self
            yield k
        end
    end
end
```

Vemos que `mytimes` no tiene declarado un par�metro. Podr�a tenerlos, pero no es el caso de este ejemplo. Pero
usa la palabra `yield`. Cuando llega a ese punto, Ruby espera que le hayamos pasado a esta funci�n un bloque, que
se comporta como un par�metro adicional refernciado impl�citamente por el `yield`. 
En este ejemplo, invocamos a ese bloque pas�ndole el argumento `k`.

Si ahora invocamos:

```ruby
3.mytimes do |i|
    puts i
end
```

La salida es
```
1
2
3
```

(A completar)

## Arreglos y Bloques

```ruby
[1,2,3].collect do |x|
    x*2
end
```
```ruby
[1,2,3].collect{ |x| x*2 }
```

(A completar: ejemplos de funciones de arreglos que reciben una funci�n)
