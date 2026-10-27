---
name: plano
description: Junta el mapa, las decisiones, los hallazgos y las maquetas en el pedido que le pasás a otro (persona o agente) para que haga el trabajo sin volver a preguntarte.
disable-model-invocation: true
---

Escribir el **plano** de un trabajo: el pliego que recibe quien lo va a hacer, una persona o un agente, para hacerlo sin tener que preguntar. Dice qué hacer, para quién, qué queda afuera y cuándo está terminado. Es síntesis de lo que ya está decidido: no reabre decisiones ni entrevista sobre el tema. Hacer el trabajo queda fuera de `rumbo`.

Leé primero, siempre:

- `${CLAUDE_PLUGIN_ROOT}/reglas/carpeta.md`, `${CLAUDE_PLUGIN_ROOT}/reglas/tickets.md` y `${CLAUDE_PLUGIN_ROOT}/reglas/analogias.md`.
- `_rumbo.md` de la carpeta.

Hablale en español rioplatense, de vos, en mensajes cortos, sin raya larga.

## 1. Juntar

Ubicá el trabajo (el que nombró la persona, o preguntale entre los que tienen mapa). Leé el `MAPA.md`, cada ticket cerrado con su respuesta, cada hallazgo y el veredicto de cada maqueta.

Fijate si el camino está despejado:

- Si el mapa termina en algo más chico que un plano, decíselo y preguntale si igual lo quiere.
- Si quedan tickets abiertos o niebla, o hay tickets cerrados que no figuran en el mapa, nombralos por su pregunta y preguntale: resolverlos primero (recomendado) o escribir el plano igual, con eso como supuesto declarado.

Si el mapa todavía no dice quién lo va a hacer, una pregunta: una persona (qué rol, qué sabe del tema), un agente, o todavía no se sabe. De eso depende cuánto contexto lleva el plano.

Terminado cuando leíste todo lo del trabajo y sabés para quién se escribe y qué entra como supuesto.

## 2. Escribir

`trabajos/<tema>/PLANO.md`. El plano viaja solo: quien lo recibe puede no tener la carpeta, así que cada decisión se escribe entera, con el enlace a su ticket como respaldo. Usá las palabras del trabajo tal como quedaron en los tickets.

```markdown
# <Qué se va a hacer>

**Para:** <quién lo hace> **De:** <la persona> **Fecha:** <AAAA-MM-DD>

## El problema

<Lo que pasa hoy, contado desde quien lo sufre.>

## Qué hay que hacer

<La solución, contada desde quien la va a usar. Sin cómo construirla, salvo que una decisión lo haya fijado.>

## Para quién

1. Como <rol>, quiero <algo>, para <beneficio>.
2. ...

## Decisiones tomadas

- <la decisión, entera> ([ticket](tickets/<archivo>))

## Qué queda afuera

- <qué, y por qué>

## Cuándo está terminado

1. <criterio>. Se comprueba: <qué se mira y quién lo mira>.
2. ...

## Lo que no está decidido

- <supuesto declarado, y a quién preguntarle; omitir la sección si no hay>

## Material de apoyo

- [<hallazgo o maqueta>](<ruta>): <para qué sirve al hacer el trabajo>
```

"Para quién" es largo: un renglón por cada rol y cada cosa que necesita, cubriendo todo lo decidido. Cada **criterio de terminado** pasa la prueba de la recepción de obra: alguien distinto de quien hizo el trabajo puede decir sí o no mirando algo concreto (un documento, un registro, un caso de prueba recorrido de punta a punta). "Que funcione bien" no pasa; "un pedido urgente cargado a las 10 figura en farmacia antes de las 11" sí. Si lo recibe un agente, cada criterio dice quién lo comprueba: el agente, o la persona después.

Terminado cuando cada ticket cerrado está reflejado en alguna sección, cada criterio dice cómo se comprueba, y lo abierto figura en "Lo que no está decidido".

## 3. Leerlo como quien lo recibe

Releelo como alguien sin la carpeta y sin memoria. Cada vez que tendría que preguntar algo, la respuesta va al plano. Después mostráselo a la persona y corregí lo que pida.

Terminado cuando la persona lo aprobó.

## 4. Cierre

Si el plano salió sin supuestos, proponele pasar el `MAPA.md` a `Estado: cerrado. Plano entregado el <fecha>`. Si lleva supuestos, el mapa sigue `en curso` y la propuesta es `Estado: en curso. Borrador de plano el <fecha>, con <n> supuestos`. Con su sí, escribí esa línea. El envío lo hace ella, por el medio que use. Decile dónde está el plano.
