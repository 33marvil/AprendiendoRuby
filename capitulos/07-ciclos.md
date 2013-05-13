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

### M�ltiples Argumentos

```ruby
[[1,2,3], [4,5,6], [7,8,9]].each do |a, b, c|
    puts "#{a} #{b} #{c}"
end
```

## Ciclo `while`

```ruby
k = 1
while k < 10
    puts k
    k = k + 1
end
```

### Modificador `while`

```ruby
k = 1
begin
    puts k
    k = k + 1
end while k < 10
```

(A completar)