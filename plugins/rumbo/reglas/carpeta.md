# La carpeta

Regla compartida por todos los skills de `rumbo`. La carpeta de trabajo de la persona **es el sistema**: lo que no quedó escrito en un archivo no existe para la próxima sesión. Cada skill lee de acá y escribe acá, en el lugar que esta regla le asigna.

La imagen que guía todo: una **biblioteca**. Hay un catálogo chico que dice dónde está cada cosa y casi no guarda nada, y estantes donde vive el contenido. Quien llega sin memoria abre el catálogo y en dos pasos está en el estante correcto.

## La forma

```
<carpeta>/
├─ CLAUDE.md          el índice: qué es esto y dónde está cada cosa
├─ _rumbo.md          ajustes del método para esta persona
├─ referencia/        lo estable: procedimientos, modelos, glosario, contactos
├─ trabajos/
│  └─ <tema>/         un trabajo con principio y fin
│     ├─ MAPA.md      el recorrido del trabajo (lo escribe trazar)
│     ├─ tickets/     una pregunta por archivo (modo archivos)
│     ├─ hallazgos/   lo que trajo explorar
│     ├─ maquetas/    lo que armó maqueta
│     └─ PLANO.md     el pedido final para otro (lo escribe plano)
└─ _archivo/          lo que ya no se usa, guardado en vez de borrado
```

Cada carpeta se crea **cuando hace falta**, el día que llega su primer archivo. Una carpeta vacía "por las dudas" es ruido: confunde a quien llega y no carga nada.

## Dónde escribe cada skill

| Skill | Escribe en |
|---|---|
| `reconocer` | `CLAUDE.md`, `_rumbo.md`, la forma de la carpeta |
| `trazar` | `trabajos/<tema>/MAPA.md` y sus tickets; suma la fila del trabajo en `CLAUDE.md` |
| `preguntar` | la respuesta, dentro del ticket que resolvió |
| `explorar` | `trabajos/<tema>/hallazgos/<pregunta>.md`, enlazado desde el ticket |
| `maqueta` | `trabajos/<tema>/maquetas/`, enlazado desde el ticket |
| `plano` | `trabajos/<tema>/PLANO.md` |

Un skill escribe solo en su lugar. Si necesita cambiar algo de otro lugar, se lo propone a la persona.

## El índice: `CLAUDE.md`

El catálogo de la biblioteca. El nombre lo pone Claude Code, que lo lee solo al abrir la carpeta; ante la persona se llama "el índice". Contesta tres cosas y nada más: qué es esta carpeta, dónde vive cada cosa, adónde ir para cada tarea. Menos de 60 líneas. Rutea, no guarda contenido: si crece, está absorbiendo algo que va en un estante; se muda el contenido y queda el enlace.

```markdown
# <Nombre del espacio>

<Una o dos líneas: de qué se trata y para quién trabaja.>

## Dónde está cada cosa

| Carpeta o archivo | Qué guarda |
|---|---|
| `_rumbo.md` | ajustes del método: modo de tickets, conceptos que ya conoce |
| `referencia/` | <lo estable de este espacio, en palabras de la persona> |
| `trabajos/` | un trabajo por carpeta; su estado está en la primera línea de su `MAPA.md` |

## Trabajos

| Trabajo | Para qué |
|---|---|
| [<tema>](trabajos/<tema>/MAPA.md) | <una línea> |

## Cómo se trabaja acá

Se arranca con `/rumbo:reconocer`; un trabajo nuevo se abre con `/rumbo:trazar`.
```

Las filas se escriben solo para lo que existe. La tabla de trabajos aparece con el primer trabajo.

## Los ajustes: `_rumbo.md`

Lo que el método sabe de esta persona. Lo leen todos los skills al arrancar.

```markdown
---
tickets: archivos        # archivos | github
repo:                    # solo en modo github: dueño/nombre del repo privado
ya_conoce: []            # conceptos que no hace falta volver a explicar
---

# Ajustes de rumbo

<Cómo prefiere trabajar la persona con el método, y las propuestas que ya rechazó.>
```

Solo guarda cómo se trabaja, nunca datos del trabajo: un umbral, un plazo o un proveedor viven en `referencia/` o en su trabajo. `tickets` se pregunta una sola vez, en `reconocer`, y desde ahí se respeta. Cómo funciona cada modo: [`tickets.md`](tickets.md). `ya_conoce` lo mantiene la regla de [`analogias.md`](analogias.md).

## Criterios

1. **Un dato, un lugar.** Cada dato vive en un solo archivo; los demás lo enlazan. Si dos archivos dicen cosas distintas, se le muestra a la persona y se deja uno solo, el que ella elija.
2. **Manda el más cercano.** Para dónde está cada cosa, manda `CLAUDE.md`. Para un trabajo, manda su `MAPA.md`. Para las preferencias, `_rumbo.md`.
3. **Lo estable separado de lo de cada vez.** Un procedimiento, una planilla modelo, un glosario: `referencia/`. Lo que nace de un trabajo puntual: su carpeta en `trabajos/`.
4. **Una carpeta, un asunto.** Si para describir una carpeta hace falta un "y además", son dos.
5. **El estado se lee en los archivos.** La primera línea de cada `MAPA.md` es `Estado: <valor>. <resumen en una línea>`, con valor `por empezar`, `en curso`, `en espera` o `cerrado`. Un trabajo cerrado se queda donde está, con su estado escrito.
6. **Nombres que viajan.** Minúsculas, palabras separadas por guion, sin tildes, eñes ni espacios: `pedido-insumos-marzo`. Si el orden es por fecha, la fecha va adelante como `AAAA-MM-DD`. Si el orden importa, número de dos cifras adelante: `01-`, `02-`. Los archivos que mandan van en mayúsculas: `CLAUDE.md`, `MAPA.md`, `PLANO.md`.
7. **Todo resultado se puede editar a mano.** Texto plano (Markdown), legible sin programas especiales. La persona puede corregir cualquier archivo y el próximo paso lee lo que ella dejó.
8. **Las claves viven en el gestor de contraseñas.** En la carpeta va el nombre del ítem donde está la clave, nunca la clave. Un archivo con claves que no se puede sacar (por ejemplo `.env`) queda fuera de cualquier repo, según [`tickets.md`](tickets.md).
9. **Se archiva, no se borra.** Lo que ya no sirve va a `_archivo/`. Borrar es decisión de la persona, archivo por archivo.

## Mover sin romper

Antes de mover o renombrar un archivo:

1. Buscá qué otros archivos de la carpeta lo nombran (su nombre, con y sin ruta). Cada enlace encontrado se actualiza en el mismo cambio.
2. Fijate si en el destino ya existe un archivo con el mismo nombre, sin distinguir mayúsculas: en Mac y Windows `mapa.md` y `MAPA.md` son el mismo y uno pisa al otro.
3. Mostrale a la persona la lista `de → a → por qué → quién lo nombra` y esperá su sí.

## La prueba de la caminata

Una carpeta está bien armada cuando alguien sin memoria la camina así:

- Abre `CLAUDE.md` y, con a lo sumo dos lecturas más, sabe dónde está y adónde ir.
- Cada carpeta de primer nivel figura en `CLAUDE.md`, y todo lo que `CLAUDE.md` nombra existe.
- El estado de cada trabajo se lee en la primera línea de su `MAPA.md`.
- Ningún dato está en dos lugares, y ninguna clave está escrita en un archivo.
