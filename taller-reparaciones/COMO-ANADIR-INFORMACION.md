# Añadir manuales y averías al archivo técnico

La página carga sus fichas desde [`data/fabricantes.json`](./data/fabricantes.json). Para mantener el contenido no hace falta tocar el HTML: edita ese JSON desde GitHub, añade el registro bajo el fabricante correspondiente y guarda los cambios. La web se actualiza al publicarse el cambio.

## Pasos en GitHub

1. Abre `taller-reparaciones/data/fabricantes.json`.
2. Pulsa el lápiz **Edit this file**.
3. Busca el fabricante (por ejemplo, `"nombre": "Unidesa"`).
4. Añade el objeto en la lista correspondiente: `manuales`, `averias`, `tecnica`, `contactos` o `modelos`.
5. Comprueba que los objetos de una lista estén separados por comas y que el JSON use comillas dobles.
6. Pulsa **Commit changes**. Tras la publicación de GitHub Pages, la ficha mostrará los datos y el buscador los encontrará.

También puedes usar [este enlace para editar el archivo de datos](https://github.com/buendi/buendi.github.io/edit/main/taller-reparaciones/data/fabricantes.json).

## Ejemplo: añadir un manual

Dentro del arreglo `"manuales": []`, sustituye `[]` por una lista como esta. Cambia los valores de ejemplo por datos reales y enlaces que tengas autorización para compartir:

```json
"manuales": [
  {
    "titulo": "Manual de servicio",
    "modelo": "Nombre del modelo",
    "revision": "Rev. 1",
    "idioma": "ES",
    "fecha": "2026-11",
    "notas": "Incluye puesta en marcha y mantenimiento preventivo.",
    "url": "https://ejemplo.com/documentacion",
    "fuente": "Fabricante"
  }
]
```

Para varios manuales, separa los objetos con coma:

```json
"manuales": [
  { "titulo": "Manual A", "modelo": "Modelo A", "url": "https://ejemplo.com/manual-a" },
  { "titulo": "Manual B", "modelo": "Modelo B", "url": "https://ejemplo.com/manual-b" }
]
```

## Ejemplo: añadir una avería

Dentro de `"averias": []`, usa campos descriptivos. `verificado` debe ser `true` solo si la solución se ha comprobado; si todavía es una hipótesis, usa `false`.

```json
"averias": [
  {
    "titulo": "No inicia tras el encendido",
    "modelo": "Nombre del modelo",
    "fecha": "2026-11",
    "sintoma": "Describe exactamente qué muestra o hace la máquina.",
    "comprobaciones": "Anota las comprobaciones realizadas y sus resultados.",
    "solucion": "Describe la solución aplicada o indica que sigue pendiente.",
    "verificado": false,
    "fuente": "Experiencia propia / referencia consultada"
  }
]
```

## Otros datos

- **Modelos:** añade nombres de modelo como texto (`"Modelo X"`) o como objeto (`{ "nombre": "Modelo X", "plataforma": "Plataforma Y" }`).
- **Información técnica/repuestos:** `{"titulo":"Referencia de pieza","modelo":"Modelo X","texto":"Nota o compatibilidad confirmada","url":"https://ejemplo.com/fuente","fuente":"Fuente"}`.
- **Contactos:** `{"departamento":"Soporte técnico","telefono":"+34 ...","email":"...","horario":"...","url":"https://...","fuente":"Web oficial","verificado":"2026-11"}`. Publica solo datos profesionales disponibles públicamente o autorizados.

## Consejos para evitar errores

- No borres la coma entre fabricantes ni añadas una coma después del último elemento de una lista.
- Conserva las comillas dobles en claves y textos JSON; escapa comillas dentro de un texto como `\"`.
- Evita publicar manuales protegidos. Enlaza a la documentación oficial o a una copia que tengas permiso para compartir.
- Documenta fuente y fecha; distingue claramente las observaciones de las soluciones verificadas.
- El buscador busca en todo el contenido. Para consultar una ficha, escribe el fabricante, modelo, síntoma o palabra clave y despliega el apartado correspondiente.
