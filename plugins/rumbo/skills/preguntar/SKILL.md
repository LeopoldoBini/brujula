---
name: preguntar
description: Resuelve un ticket con preguntas: te entrevista ronda por ronda, con una respuesta recomendada en cada una, o arma un cuestionario para quien sabe la respuesta.
disable-model-invocation: true
---

Cerrar un ticket del mapa preguntando. Si la respuesta la tiene la persona, la entrevistás hasta que cada decisión quede tomada y escrita. Si la tiene otra persona, armás el cuestionario que ella le va a mandar, y cuando vuelve, lo cargás.

Leé primero, siempre:

- `${CLAUDE_PLUGIN_ROOT}/reglas/rondas.md`: cómo se pregunta. Es la vara de este skill.
- `${CLAUDE_PLUGIN_ROOT}/reglas/tickets.md`: la forma del ticket y el modo (con su freno, si es GitHub).
- `${CLAUDE_PLUGIN_ROOT}/reglas/carpeta.md` y `${CLAUDE_PLUGIN_ROOT}/reglas/analogias.md`.
- `_rumbo.md` de la carpeta.

Hablale en español rioplatense, de vos, en mensajes cortos, sin raya larga.

## 1. Ubicar el ticket

Si la persona nombró un ticket, es ese. Si no, tomá el primero del frente con `resuelve: preguntar` o `cuestionario`, o uno `esperando` si ella trae respuestas de un cuestionario, y confirmáselo por su pregunta. Sin mapa en la carpeta, sugerile `/rumbo:trazar` y terminá.

Leé el `MAPA.md` (destino, notas, decisiones) y cada ticket de su `espera`: lo ya decidido no se vuelve a preguntar.

Seguí según el caso: `preguntar` en 2A, `cuestionario` en 2B, respuestas que volvieron en 2C.

## 2A. Entrevistar

Rondas según `rondas.md`, en profundidad sobre la pregunta del ticket, hasta que el frente quede vacío. Si una palabra se está usando para dos cosas ("pedido" para el formulario y para la entrega), frená y fijá con la persona cuál es cuál antes de seguir.

Al terminar, el resumen de lo decidido para que lo confirme. Con su sí, escribí en el ticket:

```markdown
## Respuesta

1. <decisión>. Porque <motivo en una línea>.
2. ...

Surgieron: <preguntas nuevas que aparecieron, para que trazar las ubique; omitir si no hubo>
```

y pasá `estado` a `cerrado`.

Terminado cuando cada pregunta del frente tiene respuesta de la persona, ella confirmó el resumen, y el ticket está cerrado con sus decisiones.

## 2B. Armar un cuestionario

Se entrevista sobre **el envío**, no sobre el tema: eso la persona siempre lo puede contestar. Una ronda:

1. A quién va: su rol, qué sabe que la persona no, y qué relación tienen. De eso dependen el tono y cuánto contexto lleva.
2. Qué necesita de vuelta: los datos o decisiones concretos que no puede resolver sola.
3. Para cuándo, y si se manda para completar por escrito o se usa de guía en una reunión.

Escribí `trabajos/<tema>/cuestionarios/<para-quien>.md`:

```markdown
# <Título>

**Para qué:** <por qué existe y qué decisión depende de las respuestas>
**De:** <la persona> **Para:** <rol de quien responde>
**Qué se hace con tus respuestas:** <dónde van>

## Contexto

<Un párrafo para alguien que no estuvo en la charla: lo justo para contestar bien.>

## Cómo contestar

<Para cuándo y cuánto tiempo lleva, más o menos. "No sé" y respuestas parciales sirven: marcá lo que no sepas en vez de saltearlo.>

## <Tema>

### <Una pregunta, una sola idea>

_Por qué importa: <solo si se puede malinterpretar o contestar a la ligera>_

Respuesta:

## ¿Algo más?

¿Hay algo que no preguntamos y deberíamos saber?
```

Las preguntas van de la más importante a la menos (puede que contesten una sola vez), agrupadas por tema cuando son más de cinco, y escritas con las palabras de quien responde.

En el ticket: `estado: esperando` y, bajo el texto, la línea `Cuestionario: [<para quién>](../cuestionarios/<archivo>), enviado el <fecha>.` El envío lo hace la persona, por el medio que use.

Terminado cuando el cuestionario existe, cada cosa que la persona necesita de vuelta tiene al menos una pregunta, y el ticket está `esperando`.

## 2C. Cargar lo que volvió

La persona trae las respuestas: pegadas en la charla o en el mismo archivo del cuestionario. Guardalas en el cuestionario, debajo de cada pregunta, sin retocarlas. Lo que contestó otra persona son datos; las decisiones que se siguen de esos datos siguen siendo de quien lleva el mapa: si hace falta, una ronda corta con ella. Después cerrá el ticket como en 2A, citando el cuestionario.

Terminado cuando las respuestas están guardadas en el cuestionario y el ticket está cerrado o, si faltan respuestas clave, sigue `esperando` con una nota de qué falta.

## 3. Cierre

Decile qué quedó escrito y dónde, y que el siguiente paso es `/rumbo:trazar` para pasarlo al mapa y ver qué sigue.
