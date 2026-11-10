# Instalar rumbo en la app de escritorio de Claude

Seis pasos, unos cinco minutos, sin terminal. Se hace una sola vez: después rumbo queda disponible en todas tus carpetas.

Lo que hay que tocar está marcado en naranja. Las capturas son de la app en Mac.

## 1. Abrí los plugins

En la barra de la izquierda, entrá a **Personalización**. Arriba, elegí **Plugins** y tocá **Agregar**.

Si en la barra no está **Personalización**, estás en Code: tocá el ícono del globo de diálogo, arriba a la izquierda, al lado de `</>`.

![Personalización, Plugins y el botón Agregar](img/instalar-app/01-personalizar-plugins.png)

## 2. Sumá el catálogo de rumbo

En el menú que se abre, elegí **Agregar marketplace**.

![Menú de Agregar](img/instalar-app/02-menu-agregar.png)

Después, **Agregar desde un repositorio**.

![Agregar desde un repositorio](img/instalar-app/03-agregar-marketplace.png)

En el campo, pegá esto y apretá Enter:

```
LeopoldoBini/brujula
```

![El nombre pegado en el campo](img/instalar-app/04a-buscar-repositorio.png)

Abajo tiene que decir "Se agregará https://github.com/LeopoldoBini/brujula". Tocá **Sincronizar**.

![Botón Sincronizar](img/instalar-app/04-campo-repositorio.png)

## 3. Buscá Rumbo

Si aparece "No hay nada nuevo para agregar desde esta fuente por ahora", es normal: tocá **Descubrir**.

![Aviso de nada nuevo y la pestaña Descubrir](img/instalar-app/05a-nada-nuevo.png)

Rumbo está en **Plugins nuevos**, más abajo en la página. Tocá su nombre para abrirlo.

![Rumbo en Plugins nuevos](img/instalar-app/05b-rumbo-en-descubrir.png)

## 4. Agregalo

Tocá **Agregar**.

![Ficha de Rumbo con el botón Agregar](img/instalar-app/05-rumbo-instalar.png)

La app avisa "Rumbo está instalado y listo para usar" y el interruptor queda prendido.

![Rumbo instalado](img/instalar-app/05c-rumbo-instalado.png)

## 5. Abrí una sesión en Code

Arriba a la izquierda, pasá a **Code** (el ícono `</>`). Abajo del cuadro de texto, tocá **Elige una carpeta** y elegí la carpeta donde trabajás: ahí queda su nombre.

![Pestaña Code y la carpeta elegida](img/instalar-app/06-code-sesion-nueva.png)

## 6. Corré preparar

Escribí `/rumbo:preparar` completo y apretá Enter dos veces: la primera lo elige de la lista, la segunda lo manda. Con solo `/rumbo` aparecen los siete comandos y el primero ya viene marcado: un Enter apurado elige ese, que no es preparar.

![Los siete comandos de rumbo](img/instalar-app/07-menu-barra-rumbo.png)

preparar mira lo que ya tenés instalado. Tarda un minuto. Si la app te pide permiso para correr un comando, aceptalo: hasta que contestes sus preguntas, solo mira.

![preparar trabajando](img/instalar-app/08a-preparar-trabajando.png)

Después te hace unas preguntas, cada una con su respuesta recomendada: si sacar alguna herramienta que choca con rumbo, y si le deja escrito a tu Claude cuándo sugerirte cada comando. Contestá todas en un mensaje, por ejemplo `1 sí, 2 no, 3 sí`. No cambia nada que no hayas aceptado.

![Una de las preguntas de preparar](img/instalar-app/08b-preparar-pregunta.png)

## Listo

El siguiente paso: una sesión nueva en Code sobre tu carpeta de trabajo (la nueva ya toma lo que dejó preparar), y `/rumbo:reconocer`.

## Si algo no sale

| Si ves | Hacé |
|---|---|
| "Este marketplace ya está agregado" | Ya lo tenías: seguí desde el paso 3. |
| Rumbo no está en Descubrir | Esperá unos segundos y volvé a tocar **Descubrir**. |
| `/rumbo` no muestra los comandos | La sesión estaba abierta desde antes de instalar: abrí una sesión nueva en Code. |
