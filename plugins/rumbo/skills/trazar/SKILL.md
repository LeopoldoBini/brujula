---
name: trazar
description: Convierte una idea confusa en un mapa del trabajo, con las preguntas que hay que resolver y en qué orden. También retoma un mapa ya empezado.
disable-model-invocation: true
---

Trazar la hoja de ruta de un trabajo envuelto en **niebla**: la idea llegó, pero el camino hasta el **destino** todavía no se ve. Este skill no hace el trabajo; dibuja el camino como un mapa de **tickets** (preguntas cuya respuesta es una decisión o un dato) y lo mantiene al día a medida que se resuelven. Las ganas de ponerse a hacer la cosa son la señal de que se llegó al borde del mapa: ahí toca el plano, no hacerla.

Leé primero, siempre:

- `${CLAUDE_PLUGIN_ROOT}/reglas/carpeta.md`: dónde vive el mapa y qué escribe cada skill.
- `${CLAUDE_PLUGIN_ROOT}/reglas/tickets.md`: la forma de un ticket, el frente y el modo (archivos o GitHub, con su freno).
- `${CLAUDE_PLUGIN_ROOT}/reglas/rondas.md`: cómo se pregunta.
- `${CLAUDE_PLUGIN_ROOT}/reglas/analogias.md`: cómo se explica cada concepto la primera vez.
- `_rumbo.md` y `CLAUDE.md` de la carpeta. Si no existe `_rumbo.md`, pedile a la persona que corra `/rumbo:reconocer` primero y terminá acá.

Hablale en español rioplatense, de vos, en mensajes cortos, sin raya larga.

**Abrir o retomar.** Si la persona trae una idea nueva, seguí en "Abrir". Si nombra un trabajo que ya tiene `MAPA.md`, o llama al skill sin decir nada y hay mapas en curso, seguí en "Retomar" (con más de un mapa en curso, preguntale cuál).

## Abrir

### 1. Nombrar el destino

El destino fija el alcance; se acuerda antes que nada. En la primera ronda (según `rondas.md`) va siempre esta pregunta: **dónde termina este mapa**.

- **En un plano**: un pedido escrito para que otro (una persona o un agente) haga el trabajo. Recomendado cuando al final alguien tiene que construir o cambiar algo.
- **En algo más chico**: una decisión tomada, una comparación de opciones, un cuestionario respondido. Recomendado cuando lo que falta es decidir, no encargar.

En la misma ronda: qué problema hay hoy y a quién le duele, quién pidió el trabajo, y un nombre corto para el tema (con la forma de "Nombres que viajan" de `carpeta.md`).

Terminado cuando el destino entra en una o dos líneas y la persona las aprobó.

### 2. Recorrer el frente a lo ancho

Más rondas, esta vez **a lo ancho**: abarcá todo el terreno (quiénes intervienen, qué datos hay, qué reglas mandan, qué tiene que pasar para que esté bien) sin profundizar en ninguna rama. Cada asunto abierto cae en uno de tres lugares:

- **Ticket**, si la pregunta ya se puede formular con precisión, aunque todavía no se pueda contestar. Elegí su `resuelve`: `preguntar` si lo decide la persona, `explorar` si es un dato que está afuera, `maqueta` si hace falta ver algo concreto para reaccionar, `cuestionario` si lo sabe otra persona.
- **Niebla**, si se intuye que va a haber que decidirlo pero todavía no se puede preguntar con precisión. La niebla no se trocea en tickets por adelantado.
- **Fuera de alcance**, si queda más allá del destino.

Si no aparece niebla y todo se resuelve en una charla, el mapa sobra: decíselo y preguntale cómo quiere seguir.

Terminado cuando cada asunto que salió está en uno de los tres lugares, y hay al menos un ticket en el frente.

### 3. Escribir el mapa

1. `trabajos/<tema>/MAPA.md` con esta forma:

   ```markdown
   Estado: en curso. <resumen en una línea>

   # <Nombre del trabajo>

   ## Destino

   <Una o dos líneas: dónde termina el mapa.>
   Termina en: <plano | la cosa más chica acordada>

   ## Notas

   <Quién lo pidió, para quién es, plazos, restricciones y preferencias que valen para todo el trabajo.>

   ## Decisiones hasta ahora

   ## Todavía en niebla

   - <lo que se intuye, tan suelto o tan preciso como se vea hoy>

   ## Fuera de alcance

   - <qué, y por qué queda afuera>
   ```

   El mapa es un índice: los tickets abiertos no se listan (están en `tickets/`) y las decisiones se resumen en una línea con enlace al ticket que las guarda.
2. Los tickets, según el modo de `_rumbo.md` y la forma de `tickets.md`, numerados en el orden en que conviene resolverlos. Primero creá todos; después completá los `espera`.
3. La fila del trabajo en la tabla de trabajos de `CLAUDE.md` (si la tabla no existe, se crea con esta fila).

Terminado cuando el mapa, cada ticket y la fila de `CLAUDE.md` existen, y cada `espera` apunta a un ticket que existe.

### 4. Cierre

Mostrale el frente, cada ticket por su pregunta y con el skill que lo resuelve (`/rumbo:preguntar`, `/rumbo:explorar`, `/rumbo:maqueta`; un cuestionario también se arma con `/rumbo:preguntar`), y recomendá por cuál empezar. En esta sesión no se resuelve ningún ticket.

## Retomar

1. **Leer.** El `MAPA.md` entero; de los tickets, solo los encabezados (`resuelve`, `estado`, `espera`) y el título. Abrí entero solo cada ticket cerrado que todavía no figura en el mapa.
2. **Anotar.** Por cada ticket cerrado que falta, una línea en "Decisiones hasta ahora": `- [<pregunta>](tickets/<archivo>): <la respuesta en una línea>`. Los cerrados como fuera de alcance van a "Fuera de alcance", no a decisiones.
3. **Despejar niebla.** Con lo que ya se decidió, lo que ahora se puede preguntar con precisión pasa a ticket nuevo y se borra de la niebla. Lo que una respuesta dejó del otro lado del destino va a fuera de alcance, y si era un ticket abierto se cierra así. Los tickets que una decisión volvió inútiles o distintos se corrigen o se cierran, contándole a la persona por qué. Si una respuesta anotó preguntas que surgieron, cada una pasa a ticket o a niebla.
4. **Ver si se llegó.** Con el frente y la niebla vacíos, el camino está despejado:
   - Si termina en plano, el siguiente paso es `/rumbo:plano`.
   - Si termina en algo más chico, mostrale a la persona que el destino está cumplido y, con su sí, pasá el estado a `cerrado`.
5. **Estado.** Reescribí la primera línea del mapa con el estado y el resumen al día.

Terminado cuando cada ticket cerrado figura en el mapa, la niebla no tiene nada que ya se pueda preguntar con precisión, y la persona sabe cuál es el próximo ticket (por su pregunta y con su skill) o que el camino está despejado.
