Veamos un concepto más. 

Supongamos que quisiéramos mostrar a cada usuarie con la cantidad de seguidores que tiene. 

Podríamos hacer esta consulta:

``` sql
SELECT id_seguido, COUNT(id_seguidor) AS cantidad_seguidores
FROM seguidores;
```

Eso nos devuelve esto:

<div
  class='mu-sql-table'
  data-name='resultado'
  data-columns='[{"name": "id_seguido", "pk": true, "fk": true}, "cantidad_seguidores"]'
  data-rows='[
    [4, 7]
  ]'>
</div>

Pero si el usuario con ID = 4 tiene 7 seguidores, podemos imaginar entonces que existen otros usuarios, y que deben tener seguidores también. ¿Por qué no los vemos? :confused:

> La solución está acá. Copiá esta query en el editor y mirá lo que devuelve. ¿Te imaginás qué hace la sentencia `GROUP BY`?

> ``` sql
> SELECT id_seguido, COUNT(id_seguidor) AS cantidad_seguidores
> FROM seguidores
> GROUP BY id_seguido;
> ```
