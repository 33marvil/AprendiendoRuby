# M�dulos y Mixins

Podemos definir clases en Ruby, cada una con un nombre. Pero tambi�n podemos tener problemas en la organizaci�n
y consumo de esas clases. Imaginen que alguien programa una clase `Factura` para una venta, y
nosotros programas otra clase `Factura` porque estamos armando la parte de compras del sistema. Para evitar
la colisi�n de nombres en Ruby tenemos los m�dulos. Pero no es su principal utilidad: sirven para organizar
nuestro c�digo y encapsular lo que vamos escribiendo, sin afectar al resto del programa.

## M�dulos

Podemos ver a un m�dulo como una especie de contenedor de m�todos, clases y constantes. Los elementos que est�n dentro 
de un m�dulo se ven entre s�, pero no son visibles al c�digo de afuera del m�dulo.

Pero veamos un ejemplo, para entender mejor el tema:

```ruby
module MiLibreria
    LARESPUESTAES = 42
    
    def saludar
        puts "Hola, soy m�todo interno"
    end
    
    def MiLibreria.saludar
        puts "Hola, soy m�todo de m�dulo"
    end
end
```

Como en otras partes de Ruby, un m�dulo es un bloque de c�digo que termina en `end`.
