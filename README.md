# brújula

Un método de trabajo con IA para gente de gestión y administración. Sirve para pasar de un pedido difuso ("hay que ordenar las compras") a un pedido claro que otra persona, o un agente, puede tomar y hacer sin volver a preguntar.

## El plugin `rumbo`

El recorrido completo, de izquierda a derecha:

```
reconocer  ->  trazar  ->  plano
                 |
                 +-- cada pregunta del mapa se resuelve con
                     preguntar, explorar o maqueta, y se vuelve a trazar
```

| Skill | Qué hace |
|---|---|
| `/rumbo:reconocer` | Arma tu carpeta de trabajo, o la revisa y la ordena |
| `/rumbo:trazar` | Convierte una idea confusa en un mapa: qué hay que resolver y en qué orden. Llamado de nuevo, pasa al mapa lo resuelto y te dice qué sigue |
| `/rumbo:preguntar` | Te hace las preguntas justas, cada una con una respuesta recomendada, y deja las decisiones escritas. También arma un cuestionario para otra persona |
| `/rumbo:explorar` | Averigua un dato que hace falta y lo deja escrito con sus fuentes |
| `/rumbo:maqueta` | Arma un borrador descartable (pantalla, circuito o planilla) para ver si la idea cierra |
| `/rumbo:plano` | Escribe el pedido final para quien lo va a hacer, con criterios para saber cuándo está terminado |

El recorrido termina en el plano: hacer el trabajo queda afuera de esta versión.

Ningún skill se activa solo: corren únicamente cuando los llamás por su nombre.

## Instalar

En Claude Code:

```
/plugin marketplace add <ruta-o-repo-de-brujula>
/plugin install rumbo@brujula
```

Después, abrí Claude Code en tu carpeta de trabajo y escribí `/rumbo:reconocer`.

## Licencia

MIT. Ver `plugins/rumbo/LICENSE` y `plugins/rumbo/AVISOS-DE-TERCEROS.md`.
