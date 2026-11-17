# La carpeta

Regla compartida por todos los skills de `rumbo`. La carpeta de trabajo de la persona **es el sistema**: lo que no quedó escrito en un archivo no existe para la próxima sesión. Cada skill lee de acá y escribe acá, en el lugar que esta regla le asigna.

La imagen que guía todo: una **biblioteca**. Hay un catálogo chico que dice dónde está cada cosa y casi no guarda nada, y estantes donde vive el contenido. Quien llega sin memoria abre el catálogo y en dos pasos está en el estante correcto.

## El núcleo y la parte propia

```
<carpeta>/
├─ CLAUDE.md          el índice: qué es esto, dónde está cada cosa, qué sabe hacer
├─ _rumbo.md          ajustes del método y dónde va cada cosa nueva
├─ trabajos/
│  └─ <tema>/         un trabajo con principio y fin
│     ├─ MAPA.md      el recorrido del trabajo (lo escribe trazar)
│     ├─ tickets/     una pregunta por archivo (modo archivos)
│     ├─ hallazgos/   lo que trajo explorar
│     ├─ maquetas/    lo que armó maqueta
│     ├─ cuestionarios/  lo que preguntar le manda a otra persona
│     └─ PLANO.md     el pedido final (lo escribe plano)
├─ _archivo/          lo que ya no se usa, guardado en vez de borrado
└─ <lo propio>        la parte propia: procedimientos, fichas, herramientas, lo que la persona haga
```

**El núcleo es fijo**: el índice, `_rumbo.md`, `trabajos/` y `_archivo/` se llaman y se arman igual en toda carpeta, porque los skills los buscan ahí. **La parte propia es libre**: toma la forma de lo que la persona hace, según [`formas.md`](formas.md), con los nombres que ella usa. Qué forma tiene y dónde va cada cosa nueva queda escrito en `_rumbo.md`.

Cada carpeta se crea **cuando hace falta**, el día que llega su primer archivo. Una carpeta vacía "por las dudas" es ruido: confunde a quien llega y no carga nada.

## Dónde escribe cada skill

| Skill | Escribe en |
|---|---|
| `preparar` | el bloque de `rumbo` en el CLAUDE.md de usuario, fuera de la carpeta |
| `reconocer` | `CLAUDE.md`, `_rumbo.md`, y la parte propia cuando la ordena |
| `trazar` | `trabajos/<tema>/MAPA.md` y sus tickets; suma la fila del trabajo en `CLAUDE.md` |
| `preguntar` | la respuesta, dentro del ticket que resolvió; un cuestionario, en `trabajos/<tema>/cuestionarios/<para-quien>.md` |
| `explorar` | `trabajos/<tema>/hallazgos/<pregunta>.md`, enlazado desde el ticket |
| `maqueta` | `trabajos/<tema>/maquetas/`, enlazado desde el ticket |
| `plano` | `trabajos/<tema>/PLANO.md` |

Un skill escribe solo en su lugar. Si necesita cambiar algo de otro lugar, se lo propone a la persona. La parte propia crece también fuera de los skills, en cualquier sesión, siguiendo "Cómo crece esta carpeta" del índice.

## El índice: `CLAUDE.md`

El catálogo de la biblioteca. El nombre lo pone Claude Code, que lo lee solo al abrir la carpeta; ante la persona se llama "el índice". Contesta tres cosas y nada más: qué es esta carpeta, dónde vive cada cosa, adónde ir para cada tarea. Menos de 60 líneas. Rutea, no guarda contenido: si crece, está absorbiendo algo que va en un estante; se muda el contenido y queda el enlace.

```markdown
# <Nombre del espacio>

<Una o dos líneas: de qué se trata y para quién trabaja.>

## Dónde está cada cosa

| Carpeta o archivo | Qué guarda |
|---|---|
| `_rumbo.md` | ajustes del método y dónde va cada cosa nueva |
| `<carpeta propia>/` | <qué guarda, en palabras de la persona> |
| `trabajos/` | un trabajo por carpeta; su estado está en la primera línea de su `MAPA.md` |

## Qué sabe hacer esta carpeta

| Cuando llega | Se atiende con |
|---|---|
| <el caso, como lo diría la persona> | [<procedimiento>](<ruta>) |

## Trabajos

| Trabajo | Para qué |
|---|---|
| [<tema>](trabajos/<tema>/MAPA.md) | <una línea> |

## Cómo crece esta carpeta

<las líneas de crecer.md, tal cual>

## Cómo se trabaja acá

<las líneas de flujo.md, tal cual>
```

Las filas se escriben solo para lo que existe. "Qué sabe hacer esta carpeta" aparece con el primer procedimiento y la tabla de trabajos con el primer trabajo. Si el índice se acerca a las 60 líneas, "Qué sabe hacer" se agrupa: cada fila lleva a una carpeta con su propio `LEEME.md`. "Cómo crece esta carpeta" lleva las líneas de [`crecer.md`](crecer.md) y "Cómo se trabaja acá" las de [`flujo.md`](flujo.md), copiadas sin retocar: el índice es lo único que toda sesión lee sola, así que ahí va lo que el asistente tiene que hacer sin que se lo pidan.

## Cajones

Cuando la persona atiende asuntos de distinto tipo, la raíz pasa a ser un **centro de comando**: se abre siempre la misma carpeta y cada tipo de trabajo vive en su **cajón**, una carpeta de primer nivel con su forma. Cuándo aparece un cajón y cómo se elige su forma: "Componer" de [`formas.md`](formas.md).

```
<carpeta>/
├─ CLAUDE.md       el índice: qué cajón es para qué asunto
├─ _rumbo.md       la forma de la raíz y la de cada cajón
├─ trabajos/
├─ _archivo/
├─ soporte/        un cajón
│  ├─ LEEME.md     su índice chico: qué guarda y qué sabe hacer
│  └─ ...
└─ clientes/       otro cajón, con otra forma
   └─ LEEME.md
```

- **El núcleo queda en la raíz, una sola vez.** `_rumbo.md`, `trabajos/` y `_archivo/` no se repiten por cajón: los skills los buscan arriba. Un trabajo que es de un cajón lo dice en las notas de su mapa.
- **El índice de la raíz nombra, el del cajón cuenta.** En "Qué sabe hacer esta carpeta" de la raíz hay una fila por cajón: el asunto, y el enlace a su `LEEME.md`. Lo de adentro (sus carpetas, su propia tabla "Qué sabe hacer") vive en el `LEEME.md` del cajón. Así se llega a cualquier procedimiento en dos lecturas después del índice.
- **Pasar a cajones es una mudanza**: se hace con "Mover sin romper" y el sí de la persona.
- **Una carpeta compartida es un solo nivel de acceso**: quien ve la carpeta ve todos sus cajones. Antes de crear un cajón con datos sensibles (sueldos, salud, datos de personas, claves de un cliente), preguntale quién más ve esta carpeta. Si no todos deben verlo, ese cajón va en una carpeta aparte, y el índice de la raíz lo nombra y dice dónde está, sin contenerlo.

## Los ajustes: `_rumbo.md`

Lo que el método sabe de esta persona y de esta carpeta. Lo leen todos los skills al arrancar, y cualquier sesión antes de guardar algo.

```markdown
---
tickets: archivos        # archivos | github
repo:                    # solo en modo github: dueño/nombre del repo privado
forma: []                # la forma de la raíz, de formas.md; varias si se componen
cajones: {}              # con centro de comando, la forma de cada cajón: `soporte: [paraguas]`
ya_conoce: []            # conceptos que no hace falta volver a explicar
---

# Ajustes de rumbo

<Cómo prefiere trabajar la persona con el método, y las propuestas que ya rechazó.>

## Dónde va cada cosa nueva

Lo que se repite acá: <en palabras de la persona>.

| Cosa nueva | Dónde va | Cómo se nombra |
|---|---|---|
| <cómo se atiende un tipo de caso> | `<carpeta>/` | `<ejemplo-de-nombre>.md` |
| <una herramienta que usa el asistente> | `<carpeta>/` | |
```

Dos partes. Arriba, cómo se trabaja: `tickets` se pregunta una sola vez, en `reconocer` ([`tickets.md`](tickets.md)); `ya_conoce` lo mantiene [`analogias.md`](analogias.md). Abajo, dónde va lo nuevo: una fila por cada clase de cosa que la persona nombró o que ya se guardó, con el lugar que le da la forma. Una clase de cosa que la tabla no tiene se le propone a la persona y, con su sí, suma su fila. Los datos del trabajo (un umbral, un plazo, un proveedor) viven en la parte propia o en su trabajo, nunca acá.

## Criterios

1. **Un dato, un lugar.** Cada dato vive en un solo archivo; los demás lo enlazan. Si dos archivos dicen cosas distintas, se le muestra a la persona y se deja uno solo, el que ella elija.
2. **Manda el más cercano.** Para dónde está cada cosa, manda `CLAUDE.md`. Para un trabajo, manda su `MAPA.md`. Para las preferencias y dónde va lo nuevo, `_rumbo.md`.
3. **Lo fijo separado de lo de cada vez.** Lo que vale siempre (un procedimiento, un modelo, las reglas, un glosario) vive aparte de lo que sale de cada caso o de cada corrida. Lo que nace de un trabajo puntual: su carpeta en `trabajos/`.
4. **Una carpeta, un asunto.** Si para describir una carpeta hace falta un "y además", son dos.
5. **El estado se lee en los archivos.** La primera línea de cada `MAPA.md` es `Estado: <valor>. <resumen en una línea>`, con valor `por empezar`, `en curso`, `en espera` o `cerrado`. Un trabajo cerrado se queda donde está, con su estado escrito.
6. **Nombres que viajan.** Minúsculas, palabras separadas por guion, sin tildes, eñes ni espacios: `pedido-insumos-marzo`. Si el orden es por fecha, la fecha va adelante como `AAAA-MM-DD`. Si el orden importa, número de dos cifras adelante: `01-`, `02-`. Los archivos que mandan van en mayúsculas: `CLAUDE.md`, `MAPA.md`, `PLANO.md`, `LEEME.md`.
7. **Todo resultado se puede editar a mano.** Texto plano (Markdown), legible sin programas especiales. La persona puede corregir cualquier archivo y el próximo paso lee lo que ella dejó.
8. **Las claves viven en el gestor de contraseñas.** En la carpeta va el nombre del ítem donde está la clave, nunca la clave. Un archivo con claves que no se puede sacar (por ejemplo `.env`) queda fuera de cualquier repo, según [`tickets.md`](tickets.md).
9. **Se archiva, no se borra.** Lo que ya no sirve va a `_archivo/`. Borrar es decisión de la persona, archivo por archivo.
10. **Cada carpeta dice para qué es.** Mientras guarda una sola clase de archivos, alcanza su fila en el índice. Cuando ahí se trabaja (tiene pasos, reglas propias o fichas), lleva un `LEEME.md`: para qué es, qué lee, qué deja y qué revisa la persona.
11. **Lo nuevo nace copiando un modelo.** Una clase de cosa con modelo en `_modelos/` se crea copiándolo, así todas salen con la misma forma.
12. **Se lee lo que el paso necesita.** Para atender algo: el índice, el procedimiento y lo que ese procedimiento nombra.

## Mover sin romper

Antes de mover o renombrar un archivo:

1. Buscá qué otros archivos de la carpeta lo nombran (su nombre, con y sin ruta). Cada enlace encontrado se actualiza en el mismo cambio.
2. Fijate si en el destino ya existe un archivo con el mismo nombre, sin distinguir mayúsculas: en Mac y Windows `mapa.md` y `MAPA.md` son el mismo y uno pisa al otro.
3. Mostrale a la persona la lista `de → a → por qué → quién lo nombra` y esperá su sí.

Una herramienta que se muda puede dejar de encontrar sus archivos: después de moverla, correla en modo de solo mirar y comprobá que lee lo mismo que antes.

## La prueba de la caminata

Una carpeta está bien armada cuando alguien sin memoria la camina así:

- Abre `CLAUDE.md` y, con a lo sumo dos lecturas más, sabe dónde está y adónde ir.
- Cada carpeta de primer nivel figura en `CLAUDE.md`, y todo lo que `CLAUDE.md` nombra existe.
- Cada fila de "Qué sabe hacer esta carpeta" lleva a un procedimiento que dice cuándo se usa, qué hace falta, los pasos y qué revisa la persona.
- `_rumbo.md` dice la forma y dónde va cada cosa nueva, y lo que hay en la parte propia está donde esa tabla dice.
- Con cajones: cada uno figura en el índice con su asunto, tiene su `LEEME.md`, y desde el índice se llega a cualquier procedimiento en dos lecturas.
- "Cómo crece esta carpeta" dice lo mismo que [`crecer.md`](crecer.md), y "Cómo se trabaja acá" lo mismo que [`flujo.md`](flujo.md).
- El estado de cada trabajo se lee en la primera línea de su `MAPA.md`.
- Ningún dato está en dos lugares, y ninguna clave está escrita en un archivo.
