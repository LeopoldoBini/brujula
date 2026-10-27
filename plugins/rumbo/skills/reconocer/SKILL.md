---
name: reconocer
description: Puerta de entrada. Arma tu carpeta de trabajo si está vacía, o la revisa y la ordena si ya tiene cosas.
disable-model-invocation: true
---

Reconocer el terreno antes de caminarlo. La carpeta donde se abrió la sesión es el espacio de trabajo de una persona de gestión; este skill la deja lista para el resto de `rumbo`: con su índice, sus ajustes y una forma que cualquiera camina sin memoria.

Leé primero, siempre, las reglas compartidas:

- `${CLAUDE_PLUGIN_ROOT}/reglas/carpeta.md`: la forma de la carpeta, los criterios y la prueba de la caminata. Es la vara de todo este skill.
- `${CLAUDE_PLUGIN_ROOT}/reglas/flujo.md`: las líneas de "Cómo se trabaja acá" en el índice.
- `${CLAUDE_PLUGIN_ROOT}/reglas/analogias.md`: cómo se explica cada concepto técnico la primera vez.

Hablale a la persona en español rioplatense, de vos, en mensajes cortos, sin raya larga.

## 1. Mirar

Recorré la carpeta: el árbol completo hasta tres niveles (sin entrar a `.git`), y leé `CLAUDE.md` y `_rumbo.md` si existen. De los demás archivos alcanza con nombre, tamaño y fecha; abrí solo los que no se entienden por el nombre.

Clasificá la carpeta en uno de dos casos:

- **Nueva**: vacía, o con pocos archivos sueltos y ninguna forma. Seguí en 2A.
- **Con historia**: tiene carpetas propias o mucho material. Seguí en 2B.

Terminado cuando podés describir en dos líneas qué hay en la carpeta y a qué caso pertenece.

## 2A. Armar (carpeta nueva)

Una sola ronda de preguntas, numeradas. Donde haya una opción mejor, va tu recomendación para que alcance con un "sí"; las preguntas abiertas van sin recomendación:

1. De qué se trata este espacio: el área, el tema o el puesto.
2. Si tiene ahora un trabajo concreto entre manos, y cuál.
3. El modo de tickets (ver paso 3), solo si `_rumbo.md` no lo tiene ya.

Con las respuestas, escribí `_rumbo.md` y `CLAUDE.md` según `carpeta.md`. Si había archivos sueltos, ubicalos con el mismo criterio que en 2B (mostrando la lista antes de mover). Las carpetas se crean solo si les toca algún archivo hoy; el trabajo que nombró la persona queda anotado en `CLAUDE.md` como próximo paso, y su carpeta la crea `trazar`.

Terminado cuando existen `CLAUDE.md` y `_rumbo.md` con lo que dijo la persona, y no hay carpetas vacías.

## 2B. Revisar (carpeta con historia)

1. **Inventario.** Cada archivo o carpeta de primer nivel, y lo que haya adentro que no se entienda por el nombre, en uno de estos papeles: *índice* (`CLAUDE.md` o lo que hace de índice), *referencia* (estable), *trabajo* (de un asunto puntual), *viejo* (sin uso, duplicado o reemplazado), *clave* (tiene contraseñas, tokens o datos de acceso). Leé lo suficiente para clasificar con fundamento, no por el nombre solo.
2. **Contraste.** Pasá la carpeta por cada criterio de `carpeta.md` y por la prueba de la caminata. Cada incumplimiento es un hallazgo.
3. **Devolución.** Mostrale a la persona, en este orden:
   - Lo urgente primero, con su propio título: cualquier archivo con claves. Nombrá el archivo y qué tipo de dato tiene, **nunca el valor**, y proponé pasarlo al gestor de contraseñas.
   - Qué falta (por ejemplo, el índice o los ajustes).
   - Qué arreglar: la lista `de → a → por qué → quién lo nombra`, armada con "Mover sin romper" de `carpeta.md`. Lo *viejo* va a `_archivo/`.
   - Lo que ya está bien, en una línea.

   Preguntá si arregla todo, una parte o nada. Si `_rumbo.md` no tiene el modo de tickets, sumá esa pregunta (paso 3) en la misma ronda.
4. **Arreglo.** Aplicá solo lo aceptado: mové, actualizá los enlaces encontrados, escribí lo que faltaba. Los archivos con claves no se mueven ni se editan sin que la persona diga qué hacer con cada uno.

Lo que se resolvió queda resuelto en los archivos mismos: un duplicado resuelto es un solo archivo vigente, sin nota aparte. A `_rumbo.md` va solo lo que la persona rechazó, para no volver a proponerlo.

Terminado cuando cada hallazgo de la devolución quedó arreglado o rechazado, y cada rechazo está anotado en `_rumbo.md`.

## 3. Modo de tickets

Se pregunta una sola vez en la vida de la carpeta: si `_rumbo.md` ya tiene `tickets`, no se vuelve a preguntar. Leé `${CLAUDE_PLUGIN_ROOT}/reglas/tickets.md` y planteá la pregunta así: archivos (recomendado, todo queda en la carpeta) o GitHub (para cuando varias personas comentan los mismos tickets desde el navegador), explicando GitHub con su analogía.

- **Archivos**: `tickets: archivos` en `_rumbo.md`.
- **GitHub**: seguí "Preparar el modo GitHub" de `tickets.md` completo, con el freno incluido. Si la persona no tiene git, `gh` o cuenta, la guiás paso por paso y esperás su confirmación en cada uno.

Terminado cuando `_rumbo.md` dice el modo, y en modo GitHub el repo existe, es privado y el primer envío pasó la revisión de claves.

## 4. Cierre

1. Caminá la carpeta como alguien sin memoria, con la prueba de `carpeta.md`. Lo que falle, arreglalo antes de cerrar.
2. Dale a la persona el árbol final en pocas líneas, qué cambió, y el siguiente paso: `/rumbo:trazar` para abrir un trabajo nuevo.

Terminado cuando la prueba de la caminata pasa entera y la persona tiene el árbol y el siguiente paso.
