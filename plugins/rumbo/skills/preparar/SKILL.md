---
name: preparar
description: Lo primero después de instalar. Revisa qué tenés instalado, te ofrece sacar lo que se superpone con rumbo y le enseña a tu Claude cuándo sugerirte cada comando.
disable-model-invocation: true
---

Dejar la instalación de `rumbo` lista. Los comandos de `rumbo` corren solo cuando la persona los escribe, así que su Claude no sabe que existen: este skill le deja escrito, en sus instrucciones generales, cuándo sugerir cada uno. De paso detecta instaladas otras herramientas que hacen lo mismo, porque dos instructivos para el mismo trámite hacen que el asistente trabaje un día de una forma y otro día de otra.

Leé primero:

- `${CLAUDE_PLUGIN_ROOT}/reglas/flujo.md`: las líneas que van en el bloque.
- `${CLAUDE_PLUGIN_ROOT}/reglas/rondas.md`: cómo se pregunta.
- `${CLAUDE_PLUGIN_ROOT}/reglas/analogias.md`: cómo se explica cada concepto. Todavía no hay `_rumbo.md`, así que cada concepto técnico se explica la primera vez.

Hablale en español rioplatense, de vos, en mensajes cortos, sin raya larga. Este skill toca solo dos cosas, y cada una con su sí: el bloque de `rumbo` en el CLAUDE.md de usuario, y lo superpuesto que la persona acepte sacar.

## 1. Mirar

- **Sistema operativo**: el de tu entorno.
- **Carpeta de configuración**: la de la variable `CLAUDE_CONFIG_DIR` si está definida (`echo $CLAUDE_CONFIG_DIR`; en Windows, `$env:CLAUDE_CONFIG_DIR`); si no, `~/.claude` (en Windows, `%USERPROFILE%\.claude`). Todo lo que sigue se busca ahí.
- **CLAUDE.md de usuario**: `<configuración>/CLAUDE.md`. Si existe, leelo: cuántas líneas tiene y si ya trae un bloque entre `<!-- rumbo:inicio -->` y `<!-- rumbo:fin -->`.
- **Plugins**: `claude plugin list --json`. De cada uno habilitado, mirá los nombres y las descripciones de sus skills (`<installPath>/skills/*/SKILL.md`).
- **Skills sueltos**: cada `<configuración>/skills/*/SKILL.md`, con su nombre y descripción.

Un plugin o skill es **superpuesto** cuando hace el mismo trabajo que un comando de `rumbo`. Los conocidos:

| Instalado | Se superpone con |
|---|---|
| plugin `mattpocock-skills` (`grilling`, `grill-me`, `wayfinder`, `research`, `prototype`, `to-spec`, `to-questionnaire`) | `preguntar`, `trazar`, `explorar`, `maqueta`, `plano` |
| skill `icm-architect` | `reconocer` |

Otros cuentan si su descripción promete lo mismo: ordenar una carpeta de trabajo, entrevistar sobre un plan, convertir una idea en un mapa de tareas, investigar con fuentes, armar un prototipo descartable, escribir una especificación o un cuestionario.

Terminado cuando sabés el sistema, la ruta del CLAUDE.md de usuario y su estado, y tenés la lista de superpuestos (o sabés que no hay).

## 2. Diagnóstico y ronda

Dale el diagnóstico en tres o cuatro líneas: sistema, estado de sus instrucciones generales (el CLAUDE.md de usuario, con su analogía), y qué hay superpuesto y con qué comando choca.

Después, una ronda según `rondas.md`:

- **Una pregunta por cada superpuesto**: sacarlo o quedárselo. Recomendá sacarlo, con la imagen de los dos instructivos para el mismo trámite. Si el plugin trae también skills que no se superponen, nombralos: se van con él. Incluí el comando exacto:
  - Plugin: `claude plugin uninstall <id> --scope <scope>`, con el `id` y el `scope` que dio la lista.
  - Skill suelto: se archiva, no se borra. Mac o Linux: `mkdir -p <configuración>/skills-archivados && mv <configuración>/skills/<nombre> <configuración>/skills-archivados/`. Windows (PowerShell): `New-Item -ItemType Directory -Force <configuración>\skills-archivados; Move-Item <configuración>\skills\<nombre> <configuración>\skills-archivados\`.
- **El bloque**: mostralo entero, tal como va a quedar, y preguntá si lo escribís. Recomendá que sí. Decí que va al final del archivo, que lo demás no se toca, y que se quita borrando lo que hay entre las dos marcas.

El bloque es esto, con las líneas de `flujo.md` copiadas tal cual donde dice:

```markdown
<!-- rumbo:inicio -->
## rumbo

Plugin instalado: un método para pasar de un pedido difuso a un pedido claro. Sus comandos corren solo si la persona los escribe. Cuando lo que pide encaja en una de estas líneas, sugerile el comando en una línea y esperá a que lo escriba:

<las líneas de flujo.md>
<!-- rumbo:fin -->
```

Si el bloque ya está y es igual, no hay pregunta: decíselo en el diagnóstico. Si está distinto (vino de otra versión), la pregunta es reemplazarlo.

Terminado cuando la persona contestó cada pregunta de la ronda.

## 3. Aplicar

Solo lo que aceptó:

- Cada superpuesto que aceptó sacar: corré su comando y verificá que ya no figure (`claude plugin list --json`, o que la carpeta esté en `skills-archivados`).
- El bloque: si el archivo no existe, crealo con el bloque solo. Si existe sin bloque, sumalo al final, separado por una línea en blanco. Si ya tenía bloque, reemplazá lo que hay entre las marcas, marcas incluidas. El resto del archivo queda byte por byte como estaba.

Releé el archivo y comprobá que hay exactamente un `<!-- rumbo:inicio -->` y un `<!-- rumbo:fin -->`.

Terminado cuando cada sí quedó aplicado y verificado, y cada no quedó sin tocar.

## 4. Cierre

En pocas líneas: qué quedó instalado, qué se sacó y qué cambió en sus instrucciones generales. Si se sacó algo o se escribió el bloque, los cambios se ven al cerrar y volver a abrir Claude Code. El siguiente paso: abrir Claude Code en su carpeta de trabajo y escribir `/rumbo:reconocer`.
