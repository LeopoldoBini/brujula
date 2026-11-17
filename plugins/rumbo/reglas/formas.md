# Las formas

Regla que leen `reconocer` y cualquier skill que tenga que decidir dónde vive algo fuera de `trabajos/`. El núcleo de la carpeta es fijo ([`carpeta.md`](carpeta.md)); **la parte propia toma la forma de lo que la persona hace**. Acá están las seis formas y cómo se elige.

Las formas son tuyas. La persona cuenta su trabajo con sus palabras y ve carpetas con los nombres de su oficina; el nombre de la forma queda en `_rumbo.md`, campo `forma`.

## La pregunta que elige

**Qué es lo que se repite.** Pedile dos o tres cosas que le llegan o que hace seguido, y que te cuente una de punta a punta: dónde arranca, dónde frena a revisar, qué sale al final. Sus pausas son los pasos; lo que "siempre va igual" es lo fijo; lo que cambia cada vez es lo de cada vez.

| Lo que se repite es... | Forma | `forma:` |
|---|---|---|
| una corrida: los mismos pasos y cada vez un resultado nuevo (el informe del lunes, un tipo de caso que se atiende siempre igual) | Línea de producción | `linea` |
| varias líneas distintas que comparten lo fijo (varios tipos de caso, varios informes) | Paraguas | `paraguas` |
| una ficha que junta cosas con el tiempo (un cliente, un proveedor, un expediente) | Biblioteca de fichas | `fichas` |
| el conocimiento mismo (un manual, la normativa, cómo decide el área) | Cuerpo de conocimiento | `conocimiento` |
| una organización: áreas, procesos, datos y quién le pasa qué a quién | Mapa de la organización | `mapa-organizacion` |
| algo que se va a modificar (un sistema, una base, un juego de documentos) y hay que saber qué mueve cada cambio | Mapa de un sistema | `mapa-sistema` |

Los árboles de abajo son ejemplos: los nombres salen de la persona. Un `LEEME.md` es el cartel de una carpeta donde se trabaja (criterio 10 de `carpeta.md`).

## 1. Línea de producción

**En chico es un solo archivo**, el procedimiento: cuándo se usa, qué hace falta, los pasos y qué revisa la persona. Así arranca casi siempre. Crece a carpeta cuando un paso junta material propio:

```
informe-semanal/
├─ LEEME.md       la línea en una pantalla: pasos, qué entra, qué sale, qué se revisa
├─ base/          lo fijo: el modelo del informe, el tono, las reglas
├─ 01-juntar/     un paso: su LEEME.md y lo que dejó cada corrida, con la fecha adelante
├─ 02-redactar/
└─ 03-revisar/
```

- Lo que deja un paso es lo que lee el siguiente, y la persona puede corregirlo en el medio.
- Los cortes van donde la persona frena a revisar. Corregir temprano es lo más barato.
- En qué anda una corrida se ve mirando qué dejó cada paso.

Vigilá: un paso que hace dos cosas (son dos); un `LEEME.md` que copia lo de `base/` (se enlaza).

## 2. Paraguas

Varias líneas bajo un mismo techo. Es la forma de quien atiende casos de varios tipos:

```
├─ base/              lo fijo que comparten todas: reglas, tono, contactos
├─ procedimientos/    una línea de un archivo por tipo de caso
├─ herramientas/      lo que el asistente usa para atenderlos
└─ informe-mensual/   una línea que ya creció a carpeta
```

- El índice rutea por caso ("Qué sabe hacer esta carpeta") y ahí frena.
- Cada línea se entiende sola; lo único compartido es `base/`.

Vigilá: lo fijo copiado adentro de cada línea; el índice contando el detalle de una.

## 3. Biblioteca de fichas

Nada "termina": las fichas se crean, juntan cosas y se consultan.

```
├─ clientes/
│  ├─ LEEME.md         qué lleva una ficha y qué estados tiene
│  ├─ acme/            todas las fichas con la misma forma por dentro
│  └─ perez-hnos/
└─ _modelos/cliente/   la ficha en blanco: toda ficha nace copiándola
```

- El modelo es la regla: lo que tiene el modelo, lo tienen todas.
- El estado va en la primera línea del archivo principal de cada ficha, con pocos valores (`alta`, `activo`, `archivado`).
- Una ficha puede llevar adentro una línea o notas propias.

Vigilá: fichas que se apartan del modelo (se emparejan); fichas a medio crear (se completan o se archivan).

## 4. Cuerpo de conocimiento

Lo que se produce es conocimiento que se consulta.

```
├─ fuentes/      el material crudo: normas, minutas, correos. Se guarda como llegó
└─ manual/
   ├─ LEEME.md   qué hay, por capas
   ├─ esencial/  lo que se lee siempre
   └─ temas/     lo que se lee según la consulta
```

- Una nota, una idea. Las notas se enlazan entre sí y cada afirmación dice de qué fuente salió.
- Se lee por capas: lo esencial, después el tema de la consulta, la fuente cruda al final.

Vigilá: notas que copian la fuente en vez de decir qué significa; lo esencial engordando.

## 5. Mapa de la organización

El tema es una empresa o un equipo: quién hace qué y qué dato va adónde.

```
├─ areas/
│  └─ compras/
│     ├─ compras.md   la tarjeta del área: qué le entra, qué hace, qué entrega, con quién se toca
│     ├─ procesos/    una tarjeta por proceso: dueño, cada cuánto, cuánto vale, cuánto duele, qué usa y qué deja
│     └─ datos/       una tarjeta por planilla, sistema o registro
└─ patrones/          lo que se repite entre áreas
```

- Pocos tipos de tarjeta, definidos una vez. Los enlaces entre tarjetas dibujan el mapa.
- Se arma con la gente del área: cada reunión termina en tarjetas.
- Un patrón se anota cuando apareció en tres áreas por separado.

Vigilá: tipos de tarjeta que se multiplican; tarjetas escritas de oído.

## 6. Mapa de un sistema

El tema es algo que alguien va a tocar. El mapa contesta "qué es esto" y "qué más se mueve si lo cambio".

```
<el sistema>/
└─ mapa/
   ├─ LEEME.md       el catálogo del mapa
   ├─ cosas/         una tarjeta por cosa: qué es, dónde está, con qué se confunde
   ├─ movimientos/   una tarjeta por proceso real: qué cosas toca y en qué orden
   └─ efectos.md     si cambiás X, abrí estas tarjetas
```

- El sistema manda. Cada tarjeta cita dónde está lo que describe: el archivo, la pantalla, la tabla.
- Cada tarjeta dice qué toca y qué parece que toca pero no.
- Lo que no se comprobó contra el sistema va marcado como sin verificar.

Vigilá: tarjetas que repiten lo que el sistema ya dice; "verificado" sin cita.

## Componer: el centro de comando

Una persona hace cosas de distinto tipo. Su carpeta sigue siendo una sola, que abre siempre: la raíz pasa a ser un **centro de comando** y cada tipo de trabajo vive en su **cajón**, con la forma que le sirve. Cómo se arma (dónde queda el núcleo, qué dice cada índice, quién puede ver qué) está en "Cajones" de [`carpeta.md`](carpeta.md).

- **Se arranca con una forma, sin cajones.** El segundo cajón aparece el día que la persona atiende algo de otro tipo: otra cosa es lo que se repite. Ahí se le propone pasar lo que había a un cajón, abrir otro para lo nuevo, y dejar la raíz como centro de comando.
- **La forma de cada cajón se elige igual que la de la raíz**: por lo que se repite ahí adentro. Un cajón puede ser una línea, otro una biblioteca de fichas, otro un paraguas chico.
- **Cada nivel tiene su catálogo chico**: el índice en la raíz, un `LEEME.md` en cada cajón. El de arriba dice para qué asunto es cada cajón, enlaza hacia abajo y ahí frena.
- **"Centro de comando" es cómo se le cuenta a la persona, no un valor.** En `_rumbo.md` la raíz queda `forma: [paraguas]` y cada cajón va en `cajones` con uno de los seis valores.

Las formas también se anidan adentro de un cajón: fichas que llevan una línea, un paraguas cuya `base/` es un cuerpo de conocimiento.

## Guardas

- **Lo mínimo que carga el trabajo.** Se crea lo que hoy recibe un archivo. Lo demás queda anotado en "Dónde va cada cosa nueva" de `_rumbo.md`, para el día que llegue.
- **Una forma se confirma a la tercera.** La primera vez de algo es un archivo. Cuando la misma clase de cosa apareció tres veces, se saca su modelo a `_modelos/` y las tres se emparejan.
- **La escalera.** Primero se atiende charlando; lo que vuelve se escribe como procedimiento; una herramienta se arma cuando el procedimiento ya se repitió y un paso es mecánico.
- **Si todo entra en un procedimiento**, la carpeta es el índice más ese archivo.
- **Un sistema para que lo usen otros** (clientes, toda la empresa a la vez) es un trabajo para `/rumbo:trazar` con destino en un plano. Las formas ordenan la carpeta de quien trabaja con su asistente.
