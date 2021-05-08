¡No te asustes! Es como cuando trabajábamos con dos tablas, pero se nos agregó una más. Eso implica más tablas en el `FROM`, y más condiciones de igualdad en el `WHERE`. Para no mezclar los campos, recordá que podés usar _alias_ diferenciando de qué tabla es cada uno. Te dejamos un ejemplo:

``` sql
SELECT p.nombre, c.teléfono
FROM personas p, contactos c
WHERE p.id = c.id;
```

Fijate qué campos te llevan de una tabla a otra. :wink:

Y si es necesario, lápiz y papel nunca están de más. :memo: Podés anotarte:

* ¿Qué datos necesito?
* ¿Qué datos tengo?
* ¿Dónde?

Recordá que tenemos la función `COUNT()` y que podemos devolver ese resultado bajo un nombre con la palabra clave `AS`
También que en SQL tenemos el operador NOT :stuck_out_tongue_winking_eye:
