---
name: reconocer
description: Puerta de entrada. Arma tu carpeta de trabajo si está vacía, o la revisa y la ordena si ya tiene cosas, con la forma de lo que vos hacés.
disable-model-invocation: true
---

Reconocer el terreno antes de caminarlo. La carpeta donde se abrió la sesión es el espacio de trabajo de una persona de gestión; este skill la deja lista para que su asistente la use: con su índice, sus ajustes y **la forma de lo que esa persona hace**, que cualquiera camina sin memoria.

Leé primero, siempre, las reglas compartidas:

- `${CLAUDE_PLUGIN_ROOT}/reglas/carpeta.md`: el núcleo fijo, los criterios y la prueba de la caminata. Es la vara de todo este skill.
- `${CLAUDE_PLUGIN_ROOT}/reglas/formas.md`: las formas que puede tomar la parte propia y la pregunta que elige entre ellas.
- `${CLAUDE_PLUGIN_ROOT}/reglas/crecer.md` y `${CLAUDE_PLUGIN_ROOT}/reglas/flujo.md`: las líneas de "Cómo crece esta carpeta" y "Cómo se trabaja acá" del índice.
- `${CLAUDE_PLUGIN_ROOT}/reglas/analogias.md`: cómo se explica cada concepto técnico la primera vez.

Hablale a la persona en español rioplatense, de vos, en mensajes cortos, sin raya larga. La forma se elige y se anota sin nombrársela: ella habla de su trabajo, vos de sus carpetas.

## 1. Mirar

Recorré la carpeta: el árbol completo hasta tres niveles (sin entrar a `.git`), y leé `CLAUDE.md` y `_rumbo.md` si existen. De los demás archivos alcanza con nombre, tamaño y fecha; abrí solo los que no se entienden por el nombre.

Clasificá la carpeta en uno de dos casos:

- **Nueva**: vacía, o con pocos archivos sueltos y ninguna forma. Seguí en 2A.
- **Con historia**: tiene carpetas propias o mucho material, o ya tiene `_rumbo.md` o un `CLAUDE.md` (aunque no haya nada más: alguien ya la armó o la editó). Seguí en 2B.

Terminado cuando podés describir en dos líneas qué hay en la carpeta y a qué caso pertenece.

## 2A. Armar (carpeta nueva)

Una sola ronda de preguntas, numeradas. Donde haya una opción mejor, va tu recomendación para que alcance con un "sí"; las preguntas abiertas van sin recomendación:

1. De qué se trata este espacio: el área, el tema o el puesto.
2. Qué es lo que se repite: dos o tres cosas que le llegan o que hace seguido, y una contada de punta a punta.
3. Si tiene ahora un trabajo concreto entre manos, y cuál.
4. El modo de tickets (ver paso 3), solo si `_rumbo.md` no lo tiene ya.

Con la respuesta 2, elegí la forma según `formas.md`. Si no alcanza para elegir, una pregunta más, en sus palabras. La carpeta arranca con **una** forma: la de lo que más le llega. Si nombró cosas de otro tipo, quedan anotadas en `_rumbo.md` como lo que también hace; su cajón aparece el día que atienda la primera. Después escribí, según `carpeta.md`:

- `_rumbo.md`, con `forma` y la tabla "Dónde va cada cosa nueva": una fila por cada clase de cosa que nombró, con el lugar que le da la forma y un nombre de su oficina.
- `CLAUDE.md`, con "Cómo crece esta carpeta" y "Cómo se trabaja acá" copiadas sin retocar.

En `_rumbo.md` copiá también los comentarios del modelo: son los que dicen qué valores admite cada campo. Un archivo que ya existe nunca se reemplaza: se completa conservando lo que tiene, y antes de guardar se le muestra a la persona qué cambia y se espera su sí.

Si había archivos sueltos, ubicalos con el mismo criterio que en 2B (mostrando la lista antes de mover). Las carpetas se crean solo si les toca algún archivo hoy: en una carpeta vacía, la forma queda anotada en la tabla y se va armando con cada cosa que se atiende. El trabajo que nombró la persona queda anotado en `CLAUDE.md` como próximo paso, y su carpeta la crea `trazar`.

Terminado cuando existen `CLAUDE.md` y `_rumbo.md` con lo que dijo la persona, `_rumbo.md` dice la forma y dónde va cada cosa que nombró, y no hay carpetas vacías.

## 2B. Revisar (carpeta con historia)

1. **Inventario.** Cada archivo o carpeta de primer nivel, y lo que haya adentro que no se entienda por el nombre, en uno de estos papeles: *índice* (`CLAUDE.md` o lo que hace de índice), *fijo* (vale siempre: un procedimiento, un modelo, reglas, una herramienta), *de cada vez* (salió de un caso o de una corrida), *trabajo* (de un asunto puntual, con principio y fin), *viejo* (sin uso, duplicado o reemplazado), *clave* (tiene contraseñas, tokens o datos de acceso). Leé lo suficiente para clasificar con fundamento, no por el nombre solo.
2. **La forma que ya tiene.** Una carpeta con historia casi siempre esconde una forma que creció sin esqueleto. Mirando el inventario, contestá para vos qué es lo que se repite acá y qué forma de `formas.md` le corresponde, y confirmalo con la persona en una pregunta, en sus palabras ("¿esto es una carpeta por cliente, y adentro siempre lo mismo?"). Se ordena hacia esa forma; cambiarla por otra se propone solo si la que tiene no carga el trabajo. Si adentro conviven asuntos de distinto tipo, lo que esconde son cajones: cada asunto es un cajón con su propia forma y la raíz queda como `paraguas` ("Cajones" de `carpeta.md`, con su pregunta de quién más ve la carpeta). Una carpeta armada con una versión anterior de `rumbo` (tiene `referencia/`, o su índice no tiene "Cómo crece esta carpeta") se trata igual que cualquier otra con historia: lo que le falta va a "Qué falta" de la devolución, y nada de lo que tiene se toca sin el sí.
3. **Contraste.** Pasá la carpeta por cada criterio de `carpeta.md` y por la prueba de la caminata. Cada incumplimiento es un hallazgo.
4. **Devolución.** Mostrale a la persona, en este orden:
   - Lo urgente primero, con su propio título: cualquier archivo con claves. Nombrá el archivo y qué tipo de dato tiene, **nunca el valor**, y proponé pasarlo al gestor de contraseñas.
   - Qué falta (por ejemplo, el índice, los ajustes, o un procedimiento que se usa y no figura en "Qué sabe hacer esta carpeta").
   - Qué arreglar: la lista `de → a → por qué → quién lo nombra`, armada con "Mover sin romper" de `carpeta.md`. Lo *viejo* va a `_archivo/`.
   - Lo que ya está bien, en una línea.

   Preguntá si arregla todo, una parte o nada. Si `_rumbo.md` no tiene el modo de tickets, sumá esa pregunta (paso 3) en la misma ronda.
5. **Arreglo.** Aplicá solo lo aceptado: mové, actualizá los enlaces encontrados, escribí lo que faltaba. `_rumbo.md` queda con la forma confirmada (y la de cada cajón, si los hay) y la tabla "Dónde va cada cosa nueva" al día. Los archivos con claves no se mueven ni se editan sin que la persona diga qué hacer con cada uno.

Lo que se resolvió queda resuelto en los archivos mismos: un duplicado resuelto es un solo archivo vigente, sin nota aparte. A `_rumbo.md` va además lo que la persona rechazó, para no volver a proponerlo.

Terminado cuando cada hallazgo de la devolución quedó arreglado o rechazado, cada rechazo está anotado en `_rumbo.md`, y `_rumbo.md` dice la forma que la persona confirmó.

## 3. Modo de tickets

Se pregunta una sola vez en la vida de la carpeta: si `_rumbo.md` ya tiene `tickets`, no se vuelve a preguntar. Leé `${CLAUDE_PLUGIN_ROOT}/reglas/tickets.md` y planteá la pregunta así: archivos (recomendado, todo queda en la carpeta) o GitHub (para cuando varias personas comentan los mismos tickets desde el navegador), explicando GitHub con su analogía.

- **Archivos**: `tickets: archivos` en `_rumbo.md`.
- **GitHub**: seguí "Preparar el modo GitHub" de `tickets.md` completo, con el freno incluido. Si la persona no tiene git, `gh` o cuenta, la guiás paso por paso y esperás su confirmación en cada uno.

Terminado cuando `_rumbo.md` dice el modo, y en modo GitHub el repo existe, es privado y el primer envío pasó la revisión de claves.

## 4. Cierre

1. Caminá la carpeta como alguien sin memoria, con la prueba de `carpeta.md`. Lo que falle y la persona todavía no vio, mostráselo y esperá su sí antes de arreglarlo. Lo que ya rechazó y quedó anotado en `_rumbo.md` no cuenta como falla y no se toca.
2. Dale a la persona el árbol final en pocas líneas, qué cambió, y los dos caminos que siguen: para algo que le llega y se repite, abrir una sesión acá y decir "atendamos esto"; para una idea grande o confusa, `/rumbo:trazar`.

Terminado cuando cada falla de la caminata quedó arreglada con su sí o rechazada y anotada, y la persona tiene el árbol y el siguiente paso.
