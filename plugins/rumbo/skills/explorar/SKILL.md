---
name: explorar
description: Averigua un dato que el mapa necesita (una norma, un proveedor, cómo lo hacen otros) y lo deja escrito con la fuente de cada afirmación.
disable-model-invocation: true
---

Resolver un ticket de tipo `explorar`: traer un **dato** que está fuera de la cabeza de la persona y dejarlo como **hallazgo**, con la fuente de cada afirmación. Explorar trae hechos; las decisiones que se siguen de ellos quedan para `preguntar`.

Leé primero, siempre:

- `${CLAUDE_PLUGIN_ROOT}/reglas/tickets.md`: la forma del ticket y el modo (con su freno, si es GitHub).
- `${CLAUDE_PLUGIN_ROOT}/reglas/carpeta.md` y `${CLAUDE_PLUGIN_ROOT}/reglas/analogias.md`.
- `_rumbo.md` de la carpeta.

Hablale en español rioplatense, de vos, en mensajes cortos, sin raya larga.

## 1. Ubicar la pregunta

Si la persona nombró un ticket, es ese; si no, los del frente con `resuelve: explorar`. Acá sí se puede resolver más de uno por sesión. Sin mapa, sugerile `/rumbo:trazar` y terminá.

Leé el `MAPA.md` y el ticket, y escribí para vos en una línea qué dato contesta la pregunta y qué fuente sería la dueña de ese dato.

## 2. Buscar en la fuente dueña

Cada dato tiene una **fuente primaria**: quien lo produce o lo rige.

- Una norma o resolución: el boletín oficial o el sitio del organismo que la dictó.
- Un producto o servicio: el catálogo, la ficha técnica o las condiciones del proveedor.
- Cómo se hace algo en la organización: los documentos de la carpeta (`referencia/` primero) o lo que la persona tenga a mano.
- Un número del trabajo (cantidades, tiempos, costos): la planilla o el registro de donde sale.

Las fuentes de segunda mano (notas, blogs, resúmenes, foros) sirven para encontrar la primaria; si una afirmación se queda solo con una secundaria, se marca así. Seguí cada afirmación hasta la fuente que la sostiene.

Con datos de pacientes o de personas en los archivos, resumí lo que hace falta (cantidades, patrones) y dejá afuera nombres y documentos.

Si no tenés acceso a internet o a una fuente, decilo y seguí con lo que haya: lo que no se pudo verificar va al hallazgo como no encontrado, con dónde habría que buscarlo.

Terminado cuando cada parte de la pregunta tiene una afirmación con fuente o figura como no encontrada.

## 3. Escribir el hallazgo

`trabajos/<tema>/hallazgos/<pregunta-corta>.md`:

```markdown
# <La pregunta del ticket>

## Respuesta corta

<De dos a cuatro líneas, para quien no va a leer más.>

## Lo que encontré

- <afirmación> [1]
- <afirmación> [2]

## Lo que no encontré

- <qué faltó y dónde habría que buscarlo>

## Fuentes

1. <título>, <enlace o ruta del archivo>. Consultada el <AAAA-MM-DD>. Primaria | Secundaria.
```

En el ticket, la respuesta corta en `## Respuesta` con el enlace al hallazgo, y `estado: cerrado`. Si el dato abre una decisión, va como `Surgieron: <la decisión que abre>` para que `trazar` la ubique.

Terminado cuando el hallazgo existe, cada afirmación lleva su número de fuente, cada fuente tiene enlace o ruta y fecha, y el ticket está cerrado con el enlace.

## 4. Cierre

Contale a la persona la respuesta corta, lo que no se encontró, y que el siguiente paso es `/rumbo:trazar` para pasarlo al mapa.
