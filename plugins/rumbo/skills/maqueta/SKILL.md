---
name: maqueta
description: Arma una maqueta descartable (una pantalla, un circuito que se puede recorrer, una planilla de ejemplo) para ver si una idea cierra antes de pedirla.
disable-model-invocation: true
---

Resolver un ticket de tipo `maqueta`: hacer algo tosco y concreto para que la persona reaccione. Una **maqueta** es de cartón: contesta una pregunta y después queda como evidencia. Nunca es el producto, nunca se conecta a nada real y nunca se usa para trabajar.

Leé primero, siempre:

- `${CLAUDE_PLUGIN_ROOT}/reglas/tickets.md`: la forma del ticket y el modo (con su freno, si es GitHub).
- `${CLAUDE_PLUGIN_ROOT}/reglas/carpeta.md` y `${CLAUDE_PLUGIN_ROOT}/reglas/analogias.md`.
- `_rumbo.md` de la carpeta.

Hablale en español rioplatense, de vos, en mensajes cortos, sin raya larga.

## 1. La pregunta y la forma

Si la persona nombró un ticket, es ese; si no, el primero del frente con `resuelve: maqueta`. Sin mapa, sugerile `/rumbo:trazar` y terminá. Leé el `MAPA.md` y el ticket.

Escribí la pregunta que la maqueta contesta en un párrafo; va arriba de todo, a la vista, en la maqueta misma. La pregunta elige la forma:

- **Pantalla**: "cómo se vería" un formulario, un tablero, un aviso. Un archivo HTML con tres variantes **distintas en estructura** (otra organización de la información, otra acción principal; no otro color), y una barra fija abajo para pasar de una a otra con botones y con las flechas del teclado.
- **Circuito**: "cómo andaría" un proceso: quién hace qué, en qué orden, qué pasa si algo falla. Un archivo HTML con los pasos y responsables dibujados, el estado del caso siempre a la vista (en qué paso está, quién lo tiene, qué ya pasó), botones para cada acción posible y pestañas con recorridos guiados: el caso normal, uno difícil, y uno que no debería poder pasar (saltear una aprobación, por ejemplo). Cada recorrido arranca de cero.
- **Planilla**: "qué datos" hacen falta. Un CSV con las columnas propuestas y de ocho a quince filas de ejemplo que incluyan los casos raros. Guardalo en UTF-8 con BOM y separado por punto y coma, que es como Excel en español lo abre bien con doble clic.

Si la pregunta admite dos formas, preguntale cuál le sirve más.

## 2. Armar

- Un solo archivo en `trabajos/<tema>/maquetas/`, nombrado `maqueta-<qué>.html` o `.csv`, que se abre con doble clic: sin instalar nada, sin internet, todo adentro.
- Arriba dice MAQUETA y la pregunta. Las palabras son las de la persona y su trabajo, nunca las de un sistema.
- Datos inventados y verosímiles, marcados como inventados. Ningún dato real de pacientes ni de personas.
- No guarda nada ni manda nada: lo que pasa en la maqueta vive mientras está abierta.
- Prolija y sobria (buena letra, aire, un color de acento) pero sin pulir de más: el objetivo es aprender rápido.

Abrila para la persona (`open <archivo>` en Mac, `start <archivo>` en Windows) y pedile que la recorra y reaccione. Lo valioso es el "esto no debería poder pasar" o el "yo pensaba que acá venía otra cosa": son fallas de la idea, que es lo que se busca. Si pide cambios, se cambian en la misma maqueta.

Terminado cuando la persona la recorrió y dijo qué le sirve, qué no y qué cambiaría.

## 3. Veredicto

En el ticket, `## Respuesta` con el veredicto (qué variante o qué versión del circuito, qué se descartó y por qué, qué cambió de la idea), el enlace a la maqueta y, si aparecieron, las preguntas nuevas como `Surgieron: ...`. `estado: cerrado`. La maqueta se queda en su carpeta como evidencia de por qué se decidió así.

Terminado cuando el ticket está cerrado con un veredicto que la persona confirmó.

## 4. Cierre

Decile qué quedó escrito y que el siguiente paso es `/rumbo:trazar` para pasarlo al mapa.
