# Crecer

Regla compartida por `reconocer` y la prueba de la caminata. Son las líneas de "Cómo crece esta carpeta" del índice: le dicen a cualquier sesión de Claude, corra o no un comando de `rumbo`, que la carpeta aprende con cada cosa que se atiende. Van en el índice porque es lo único que toda sesión lee sola. Se copian tal cual; cambiar cómo crece una carpeta es cambiar este archivo.

```markdown
- **Antes de atender algo**, buscalo en "Qué sabe hacer esta carpeta". Si figura, seguí ese procedimiento; si la fila lleva a un cajón, seguí por su `LEEME.md`.
- **Al terminar algo que la carpeta no conocía**, ofrecé guardarlo sin esperar a que te lo pidan: el procedimiento (cuándo se usa, qué hace falta, los pasos, qué revisa la persona), la herramienta si se usó una, y su fila en "Qué sabe hacer esta carpeta".
- **Si lo que llegó es de otro tipo** que lo que esta carpeta atiende, proponé darle su propio cajón: una carpeta con su `LEEME.md`, y lo que había pasa a otro. Este índice dice qué cajón es para qué asunto, y ahí frena; `_rumbo.md`, `trabajos/` y `_archivo/` quedan en la raíz.
- **Antes de crear un cajón con datos sensibles**, preguntá quién más ve esta carpeta: lo que no todos deben ver va en una carpeta aparte, y acá queda solo su nombre y dónde está.
- **Mostrá antes de tocar**: qué se guarda o se mueve y dónde, y esperá el sí.
- **Si la carpeta queda incómoda** (lo mismo en dos lugares, una carpeta con dos asuntos, este índice creciendo), proponé reordenarla.
- Dónde va cada clase de cosa: `_rumbo.md`, "Dónde va cada cosa nueva".
```

Lo que se guarda sigue los criterios de [`carpeta.md`](carpeta.md) y toma el lugar que le da la forma ([`formas.md`](formas.md)); lo que se mueve, "Mover sin romper".
