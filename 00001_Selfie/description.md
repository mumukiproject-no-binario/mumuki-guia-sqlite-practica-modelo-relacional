Fotogram es una aplicación donde cada usuarie puede hacer publicaciones de fotos y videos.

Con eso ya podemos armar este modelo inicial:

<div
  class='mu-erd'
  data-entities='{
    "usuarios": {
      "id_usuario": {
        "type": "Integer",
        "pk": true
      },
      "nombre_usuario": {
        "type": "Text"
      },
      "foto_perfil_url": {
        "type": "Text"
      }
    },
    "publicaciones": {
      "id_publicacion": {
        "type": "Integer",
        "pk": true
      },
      "foto_video_url": {
        "type": "Text"
      },
      "id_duenio": {
        "type": "Integer",
        "pk": false,
        "fk": {
          "to": { "entity": "usuarios", "column": "id_usuario" },
          "type": "many_to_one"
        }
      },
      "fecha": {
        "type": "Text"
      },
      "es_temporal": {
        "type": "Integer"
      }
    }
  }'>
</div>

Observamos del DER que:

1. Cada usuarie tiene un nombre y una foto de perfil.
2. Une usuarie puede tener muchas publicaciones, pero hay de dos tipos:
  * publicaciones temporales, más conocidas como "historias", que solo duran un día.
  * publicaciones fijas, que obviamente no son temporales y perduran por siempre (a menos que le dueñe las borre... :stuck_out_tongue_winking_eye:).
   
Por último, existe la función `DATE('AAAA-MM-DD')`, que recibe un _string_ con el formato que ves, y devuelve la fecha correspondiente. 

> Eliminá las publicaciones con fecha anterior al 2 de Enero de 2018.