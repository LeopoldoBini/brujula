# brújula

Un método de trabajo con IA para gente de gestión y administración. Sirve para pasar de un pedido difuso ("hay que ordenar las compras") a un pedido claro que otra persona, o un agente, puede tomar y hacer sin volver a preguntar.

## El plugin `rumbo`

El recorrido completo, de izquierda a derecha:

```
reconocer  ->  trazar  ->  plano
               (usa preguntar, explorar y maqueta)
```

| Skill | Qué hace | Estado |
|---|---|---|
| `/rumbo:reconocer` | Arma tu carpeta de trabajo, o la revisa y la ordena | disponible |
| `/rumbo:trazar` | Dibuja el mapa de un trabajo: qué hay que decidir y en qué orden | próximamente |
| `/rumbo:preguntar` | Te hace las preguntas justas para cerrar una decisión | próximamente |
| `/rumbo:explorar` | Investiga un dato que hace falta para decidir | próximamente |
| `/rumbo:maqueta` | Arma un borrador rápido para reaccionar sobre algo concreto | próximamente |
| `/rumbo:plano` | Escribe el pedido final para quien lo va a hacer | próximamente |

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
