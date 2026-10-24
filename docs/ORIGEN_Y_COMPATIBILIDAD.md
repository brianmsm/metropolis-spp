# Extracción de estilos y compatibilidad

## Procedencia

Extensión base `brianmsm/metropolis`, revisión Git `6728c302339bde543e7ce23ffc63393c0df163f5`, a su vez derivada de `shafayetShafee/metropolis`.

Sus recursos, filtro Lua y SCSS originales se copiaron **sin alterar sus bytes**. La nueva capa SPP está en `spp.scss`, de forma que las futuras actualizaciones se puedan comparar con la base sin fusionar cientos de cambios ajenos.

La identidad docente proviene de revisar:

- `styles/bifactor.css`
- `sesion_01/estilos.css`
- `sesion_02/estilos.css`

del repositorio `Cursos-SPP/curso-modelos-bifactor-R`.

## Patrones seleccionados

Se identificaron componentes reutilizables: paleta, encabezados, portadas magenta, tarjetas, tablas, bloques de código R, cajas de conclusiones, indicadores y flujos explicativos. La nueva capa **no copia exactamente** los estilos de ninguna sesión: combina patrones comunes, utilizando tamaños y contrastes pensados para presentaciones 1280×720.

## Excluido deliberadamente

- Selectores específicos `#s02-*`, diagramas y parámetros de modelos bifactor.
- Clases administrativas de S01 (inscripción, Zoom, certificado) sin sentido para otros cursos.
- Código JavaScript específico de S02 para distribuir referencias entre varias láminas.
- Cifras, scripts R, semillas, resultados, archivos de datos o bibliografía de los cursos.

## Matriz mínima de calidad

1. Renderizar la demo sin paquetes R ni datos privados.
2. Comprobar en Chromium portada, secciones, flujos, tarjetas, tabla, código, ecuaciones y bibliografía.
3. Producir PDF 16:9 con DeckTape, comparar páginas y revisar muestras reales.
4. **Antes de migrar un curso existente**, probar copias temporales de S01/S02; mantener los CSS locales en un primer paso para identificar diferencias.
5. No modificar ni hacer push a los proyectos de origen durante estas pruebas.

**No afirmar equivalencia píxel a píxel entre formatos:** integrar una capa SPP nueva puede cambiar tamaños, espaciados y estilos heredados. Requerirá ajustes específicos por sesión cuando se migre.

## Verificación de la versión 0.1.0 (24 de octubre de 2026)

- Quarto **1.10.19**: `template.qmd` renderizado sin advertencias y sin datos o paquetes R externos.
- DeckTape **3.16.1** con Chromium: **10/10 páginas** 16:9, texto presente en todas; PDF de revisión [incluido aquí](metropolis-spp-demo.pdf).
- Instalación desde ZIP local en proyecto limpio: `quarto add` instala el formato `metropolis-spp-revealjs` y permite renderizar un documento externo.
- `quarto use template` desde ZIP local: copia la plantilla, las referencias y la extensión; la plantilla exportada renderiza sin advertencias.
- **S01 y S02:** renderizados sobre copias temporales que utilizan el nuevo formato **manteniendo el CSS local**. Ambos terminaron sin advertencias. Revisión puntual en Chromium de las láminas de modelo bifactor, índices robustos y filtros diagnósticos: estructura y datos conservados, pero existen diferencias menores de espaciado y tipografía (no equivalencia exacta).
- Los **9 archivos originales** (SCSS, Lua, assets y CSS/JS de recursos) comprobados contra el fork son idénticos byte a byte; la nueva licencia incluida en el paquete conserva la atribución MIT.
- No se modificaron las fuentes de `brianmsm/metropolis` ni `Cursos-SPP/curso-modelos-bifactor-R` durante el desarrollo.

Estas verificaciones son una **prueba de compatibilidad inicial**, no una migración aprobada de S01/S02 ni un análisis exhaustivo del comportamiento en versiones futuras de Quarto.
