# El flujo

Regla compartida por `preparar` y `reconocer`. Son las líneas que le dicen a Claude qué comando de `rumbo` sugerir según lo que pide la persona: `preparar` las pone en el CLAUDE.md de usuario y `reconocer` en el índice de la carpeta. Se copian tal cual; cambiar el flujo es cambiar este archivo.

```markdown
- Recién instalado, o para revisar la instalación: `/rumbo:preparar`.
- Carpeta nueva, desordenada o sin índice: `/rumbo:reconocer` la arma o la ordena.
- Idea nueva o pedido difuso ("ayudame a pensar esto"): `/rumbo:trazar` lo convierte en un mapa de preguntas. Con un mapa en curso, lo pone al día y dice qué sigue.
- Decisión pendiente del mapa: `/rumbo:preguntar` la resuelve en rondas con respuesta recomendada, o arma un cuestionario para quien sabe.
- Dato que falta (una norma, un proveedor, cómo lo hacen otros): `/rumbo:explorar` lo averigua con fuentes.
- Ver si una idea cierra (una pantalla, un circuito, una planilla): `/rumbo:maqueta` arma un borrador descartable.
- Mapa despejado: `/rumbo:plano` escribe el pedido final para quien hace el trabajo.
```
