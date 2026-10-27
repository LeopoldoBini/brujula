# brújula

Un método de trabajo con IA para gente de gestión y administración. Sirve para pasar de un pedido difuso ("hay que ordenar las compras") a un pedido claro que otra persona, o un agente, puede tomar y hacer sin volver a preguntar.

## El plugin `rumbo`

El recorrido completo, de izquierda a derecha:

```
preparar (una vez)  ->  reconocer  ->  trazar  ->  plano
                                           |
                                           +-- cada pregunta del mapa se resuelve con
                                               preguntar, explorar o maqueta, y se vuelve a trazar
```

| Skill | Qué hace |
|---|---|
| `/rumbo:preparar` | Lo primero después de instalar: revisa lo que ya tenés, te ofrece sacar lo que se superpone y le enseña a tu Claude cuándo sugerirte cada comando |
| `/rumbo:reconocer` | Arma tu carpeta de trabajo, o la revisa y la ordena |
| `/rumbo:trazar` | Convierte una idea confusa en un mapa: qué hay que resolver y en qué orden. Llamado de nuevo, pasa al mapa lo resuelto y te dice qué sigue |
| `/rumbo:preguntar` | Te hace las preguntas justas, cada una con una respuesta recomendada, y deja las decisiones escritas. También arma un cuestionario para otra persona |
| `/rumbo:explorar` | Averigua un dato que hace falta y lo deja escrito con sus fuentes |
| `/rumbo:maqueta` | Arma un borrador descartable (pantalla, circuito o planilla) para ver si la idea cierra |
| `/rumbo:plano` | Escribe el pedido final para quien lo va a hacer, con criterios para saber cuándo está terminado |

El recorrido termina en el plano: hacer el trabajo queda afuera de esta versión.

Ningún skill se activa solo: corren únicamente cuando los llamás por su nombre. `/rumbo:preparar` deja escrito en tus instrucciones generales cuándo conviene cada uno, así tu Claude te lo sugiere.

## Instalar

En la terminal:

```
claude plugin marketplace add LeopoldoBini/brujula
claude plugin install rumbo@brujula
```

Cerrá y volvé a abrir Claude Code, y escribí `/rumbo:preparar`. Después, abrí Claude Code en tu carpeta de trabajo y escribí `/rumbo:reconocer`.

Si preferís que lo instale tu Claude, pegale el texto de [`INSTALAR-PROMPT.txt`](INSTALAR-PROMPT.txt).

## Licencia

MIT. Ver `plugins/rumbo/LICENSE` y `plugins/rumbo/AVISOS-DE-TERCEROS.md`.
