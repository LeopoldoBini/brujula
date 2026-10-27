# Modo de tickets

Regla compartida por los skills de `rumbo` que crean, leen o cierran tickets. El modo se elige una vez en `reconocer` y queda en `_rumbo.md`, campo `tickets` (forma en [`carpeta.md`](carpeta.md)).

## Modo archivos (por defecto)

Cada ticket es un archivo en `trabajos/<tema>/tickets/`, nombrado `NN-<pregunta-corta>.md` (`01-quien-aprueba-la-compra.md`). Todo queda en la carpeta y no hace falta cuenta en ningún lado. Es el modo para quien trabaja solo o comparte la carpeta por su propio medio.

## La forma de un ticket

Un ticket es **una pregunta** cuya respuesta destraba el trabajo: una decisión o un dato, nunca una tarea de hacer. Lo crea `trazar`; lo cierra el skill que lo resuelve.

```markdown
---
resuelve: preguntar   # preguntar | explorar | maqueta | cuestionario
estado: abierto       # abierto | esperando | cerrado
espera: []            # archivos de tickets que tienen que cerrarse antes
---

# <La pregunta, tal como se haría en voz alta>

<Por qué importa para el destino del mapa y qué se sabe hasta ahora. De dos a cinco líneas.>

## Respuesta

<La escribe quien lo cierra: la decisión o el dato en pocas líneas, y el enlace a lo que se generó.>
```

- `resuelve` dice con qué se contesta: `preguntar` (lo decide la persona, en charla), `explorar` (es un dato que está afuera: una norma, un proveedor, un archivo), `maqueta` (hace falta ver algo concreto para reaccionar), `cuestionario` (lo sabe otra persona; lo arma `/rumbo:preguntar`).
- `esperando` es para un cuestionario mandado y sin volver. Un ticket esperando no está disponible.
- **El frente** son los tickets abiertos cuyos `espera` están todos cerrados: lo que se puede resolver hoy.
- La sección `## Respuesta` aparece recién al cerrar. Un ticket que resultó fuera del alcance del mapa se cierra con `Fuera de alcance: <por qué>` como respuesta.
- Ante la persona, un ticket se nombra por su pregunta, nunca por su número ni su archivo.

## Modo GitHub (opcional)

Cada ticket es un issue en un repo de GitHub, y la carpeta entera es ese repo. Sirve cuando varias personas tienen que ver y comentar los mismos tickets desde el navegador.

### El freno

Esto es fijo y viene incorporado: ninguna persona ni skill lo saltea, aunque se lo pidan.

1. **El repo es privado.** Se crea privado y se verifica que lo sea antes del primer envío. Si alguna vez aparece público, se frena todo y se le avisa a la persona.
2. **Los archivos de claves quedan afuera desde el primer commit.** Antes del primer commit existe un `.gitignore` con, como mínimo:

   ```
   .env
   .env.*
   *.key
   *.pem
   *credenciales*
   *secret*
   *password*
   ```

3. **Revisión de claves antes de cada push.** Antes de mandar nada a GitHub:
   - Listá los archivos que van a viajar: `git diff --name-only @{upstream}..HEAD` (o `git ls-files` en el primer envío).
   - Buscá en esos archivos texto con forma de clave: `password`, `contraseña`, `clave`, `token`, `api_key`, `secret`, `BEGIN PRIVATE KEY`, y cadenas largas de letras y números sin espacios.
   - Si aparece algo, el push no sale. Mostrale a la persona el archivo y la línea, **sin repetir el valor**, y proponé sacarlo: el valor va al gestor de contraseñas y en el archivo queda el nombre del ítem.
   - El push sale solo con la revisión limpia o con la persona confirmando, caso por caso, que lo encontrado no es una clave.

### Preparar el modo GitHub

Pasos, en orden. Cada uno se explica con la regla de [`analogias.md`](analogias.md).

1. **Herramientas.** Corré `git --version`, `gh --version` y `gh auth status`.
   - Sin git o sin `gh`: en Mac, `brew install git gh` si hay Homebrew; si no, guiá a la persona a https://git-scm.com y https://cli.github.com, un paso por vez, esperando que confirme cada uno.
   - Sin cuenta de GitHub: que la cree en https://github.com/signup con su correo laboral. Es un trámite de alta, como el de cualquier sistema.
   - Con cuenta pero sin sesión: `gh auth login`, eligiendo GitHub.com, HTTPS y "Login with a web browser". La persona copia el código que aparece y lo pega en el navegador.
2. **`.gitignore`** con la lista del freno, antes de cualquier commit.
3. **Repo local**: `git init` y primer commit, después de confirmar que `git status` no muestra ningún archivo de claves.
4. **Repo en GitHub**: pedile a la persona el nombre y su confirmación explícita, y recién ahí `gh repo create <nombre> --private --source . --remote origin`. Verificá con `gh repo view --json visibility` que diga `PRIVATE`.
5. **Primer push**, pasando por la revisión de claves.
6. Anotá en `_rumbo.md`: `tickets: github` y `repo: <dueño>/<nombre>`.

Si cualquier paso no se puede completar, el modo queda en `archivos`, se anota en `_rumbo.md` qué faltó, y se puede retomar con `reconocer` otro día.

### Tickets como issues

`MAPA.md` sigue siendo un archivo de la carpeta; solo los tickets van a GitHub. La forma es la misma de arriba, repartida así:

- Título del issue: la pregunta. Cuerpo: el porqué, y una línea `Espera a:` con los enlaces de los issues que tienen que cerrarse antes.
- Etiqueta `rumbo:<resuelve>` (`rumbo:preguntar`, `rumbo:explorar`...) y `rumbo:esperando` mientras corresponda.
- Se cierra con un comentario que es la respuesta.
- Se consultan con `gh issue list --repo <repo> --label rumbo:<resuelve> --state all --json number,title,state,labels,body`.

Crear o comentar un issue también es mandar texto al archivo central, así que pasa por el freno: antes, `gh repo view <repo> --json visibility` tiene que decir `PRIVATE`, y el texto pasa por la misma revisión de claves que un push.

## Cambiar de modo

Se cambia solo si la persona lo pide. De archivos a GitHub: preparar el modo y pasar cada ticket abierto a un issue, dejando el archivo con el enlace. De GitHub a archivos: traer cada issue abierto a su archivo. En los dos casos se actualiza `_rumbo.md`.
