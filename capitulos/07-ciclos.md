# Ciclos e Iteradores

Muchas veces en programaci�n tenemos que ejecutar un bloque de c�digo repetidas veces. Ruby, como otros lenguajes,
provee comandos de ciclos, y hasta m�todos sobre colecciones que reciben un bloque a ejecutar.

## Ciclo `for`

```ruby
for k in [1,2,3] do
    puts k
end
```

```ruby
[1,2,3].each do |k|
    puts k
end
```

```ruby
(1..10).each do |k|
    puts k
end
```

(A completar)