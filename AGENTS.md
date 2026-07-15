# Skill de documentación DAX para Contoso Bikes

## Propósito
Esta skill define cómo documentar medidas, cálculos y expresiones DAX en este proyecto. Debe aplicarse siempre que se creen, modifiquen o revisen medidas en la carpeta de definición del modelo semántico.

## Reglas obligatorias
1. Idioma: toda la documentación debe escribirse en español.
2. Comentarios de DAX: usar comentarios TMDL con `///` justo encima de la medida o expresión.
3. Enfoque: explicar el propósito de negocio y el contexto de uso, no repetir la sintaxis DAX línea a línea.
4. Alcance: indicar si el cálculo depende de tablas, columnas, filtros, segmentaciones, parámetros o otras medidas.
5. Brevedad: priorizar una explicación corta, clara y útil, normalmente de una o dos frases.
6. Terminología: usar términos del negocio y del modelo del proyecto: albarán, venta neta, cliente, canal, fecha, margen, volumen, etc.
7. Si la medida usa parámetros como `param_Formato`, `SELECTEDVALUE`, `CALCULATE`, `DIVIDE` u otras funciones relevantes, mencionar esa dependencia cuando aporte contexto.
8. Mantener coherencia con la estructura actual del modelo: las medidas del proyecto se agrupan en la tabla `_Medidas` y deben conservar nombres legibles y comprensibles.
9. Evitar comentarios genéricos como “calcula un valor” o “retorna un resultado”; preferir explicaciones accionables para analistas y usuarios del modelo.
10. Si el cálculo es complejo, documentar el objetivo principal y, solo si aplica, una nota breve sobre supuestos o consideraciones de negocio.

## Plantilla recomendada
```tmdl
/// [Objetivo de negocio del cálculo].
/// Contexto: [tabla, columna, segmentación o periodo afectado].
/// Dependencias: [medidas, parámetros o filtros relevantes].
/// Nota: [consideración especial si aplica].
```

## Ejemplos del proyecto
- `/// Importe neto vendido según líneas de albarán.`
- `/// Porcentaje de margen bruto sobre ventas netas.`
- `/// Ventas netas del canal online.`

## Criterio de calidad
Antes de dar por válida una documentación de DAX, verificar que:
- sea comprensible sin leer el código completo;
- refleje el significado de negocio;
- sea consistente con el idioma y la terminología del proyecto;
- no sea redundante ni excesivamente técnica.
