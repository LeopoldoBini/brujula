# brújula

Un método de trabajo con IA para gente de gestión y administración. Sirve para dos cosas: que tu carpeta de trabajo le enseñe a tu Claude lo que vos hacés, y pasar de un pedido difuso ("hay que ordenar las compras") a un pedido claro que otra persona, o un agente, puede tomar y hacer sin volver a preguntar.

## El plugin `rumbo`

### Tu carpeta es tu asistente

Claude no se acuerda de nada: cada vez que abrís una sesión, lee tu carpeta. Lo que está escrito ahí es lo que sabe hacer. `/rumbo:reconocer` arma la carpeta con la forma de tu trabajo (no hay una estructura única: se ordena distinto si atendés casos, si llevás clientes o si armás un informe todas las semanas), y de ahí en más la carpeta crece sola:

```
reconocer (una vez)  ->  "Atendamos esto: ..."  ->  Claude ofrece dejarlo escrito  ->  "Atendamos tal cosa"
                          la primera vez, juntos     procedimiento, herramienta          de ahí en más, ya sabe
                                                     y su línea en el índice
```

No hace falta ningún comando para eso: son frases. El índice de la carpeta le dice a Claude que busque primero si ya sabe atender lo que llega, que ofrezca guardar lo nuevo, y que no guarde ni mueva nada sin mostrarte qué y dónde. Si un día atendés algo de otro tipo, te propone abrirle su propio cajón, y la carpeta de siempre queda como centro de comando.

### De la idea confusa al pedido claro

Para lo que no es un caso sino un proyecto, el recorrido completo, de izquierda a derecha:

```
preparar (una vez)  ->  reconocer  ->  trazar  ->  plano
                                           |
                                           +-- cada pregunta del mapa se resuelve con
                                               preguntar, explorar o maqueta, y se vuelve a trazar
```

| Skill | Qué hace |
|---|---|
| `/rumbo:preparar` | Lo primero después de instalar: revisa lo que ya tenés, te ofrece sacar lo que se superpone y le enseña a tu Claude cuándo sugerirte cada comando |
| `/rumbo:reconocer` | Arma tu carpeta de trabajo con la forma de lo que hacés, o la revisa y la ordena |
| `/rumbo:trazar` | Convierte una idea confusa en un mapa: qué hay que resolver y en qué orden. Llamado de nuevo, pasa al mapa lo resuelto y te dice qué sigue |
| `/rumbo:preguntar` | Te hace las preguntas justas, cada una con una respuesta recomendada, y deja las decisiones escritas. También arma un cuestionario para otra persona |
| `/rumbo:explorar` | Averigua un dato que hace falta y lo deja escrito con sus fuentes |
| `/rumbo:maqueta` | Arma un borrador descartable (pantalla, circuito o planilla) para ver si la idea cierra |
| `/rumbo:plano` | Escribe el pedido final para quien lo va a hacer, con criterios para saber cuándo está terminado |

El recorrido termina en el plano. El plano puede ser para otra persona, para un agente, o para tu propio Claude en tu carpeta: en ese caso lo hace ahí mismo y la carpeta se queda con el procedimiento.

Ningún skill se activa solo: corren únicamente cuando los llamás por su nombre. `/rumbo:preparar` deja escrito en tus instrucciones generales cuándo conviene cada uno, así tu Claude te lo sugiere.

## Instalar

**En la app de escritorio de Claude** (sin terminal): seguí el [paso a paso con capturas](docs/instalar-en-la-app.md). En corto: **Personalización** > **Plugins** > **Agregar** > **Agregar marketplace** > **Agregar desde un repositorio**, pegá `LeopoldoBini/brujula` y tocá **Sincronizar**; en **Descubrir**, abrí **Rumbo** y tocá **Agregar**; en **Code**, una sesión nueva y `/rumbo:preparar`.

**En la terminal**:

```
claude plugin marketplace add LeopoldoBini/brujula
claude plugin install rumbo@brujula --scope user
```

Cerrá y volvé a abrir Claude Code, y escribí `/rumbo:preparar`. Si preferís que lo instale tu Claude, pegale el texto de [`INSTALAR-PROMPT.txt`](INSTALAR-PROMPT.txt) (solo sirve en la terminal).

Después, en los dos casos: una sesión nueva sobre tu carpeta de trabajo, y `/rumbo:reconocer`.

### Si ya tenías rumbo

rumbo no se actualiza solo. En la terminal:

```
claude plugin marketplace update brujula
claude plugin update rumbo@brujula
```

En la app de escritorio, abrí Rumbo en **Personalización** > **Plugins** y actualizalo; si no cambia, quitalo y volvé a agregarlo. Después, en una sesión nueva, corré otra vez `/rumbo:preparar` y, sobre tu carpeta, `/rumbo:reconocer`: te muestra qué le falta a la carpeta y no cambia nada sin tu sí.

## Licencia

MIT. Ver `plugins/rumbo/LICENSE` y `plugins/rumbo/AVISOS-DE-TERCEROS.md`.
