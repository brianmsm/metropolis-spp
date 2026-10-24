# Metropolis SPP — Quarto Reveal.js

**Metropolis SPP** es una variante académica de [Metropolis](https://github.com/brianmsm/metropolis) (a su vez fork de [shafayetShafee/metropolis](https://github.com/shafayetShafee/metropolis)). Conservará la base y los recursos del tema original y añadirá un estilo reutilizable de diapositivas para docencia: Fira Sans, títulos oscuros, portadas magenta, turquesa para comparaciones y componentes claros para tablas, código y diagramas.

**Formato:** `metropolis-spp-revealjs` · **Versión:** `0.1.0` · **Licencia:** MIT.

**Vista previa:** [PDF de demostración, 10 láminas](docs/metropolis-spp-demo.pdf) · [fuente editable Quarto](template.qmd).

## Instalar y utilizar

**Desde un ZIP local** (válido también antes de publicar la extensión en GitHub):

```bash
quarto add /ruta/a/metropolis-spp-v0.1.0.zip
```

En esta máquina, el archivo comprobado está en `/home/brian/Documents/Github/metropolis-spp/_site/metropolis-spp-v0.1.0.zip`.

**Cuando el repositorio público esté disponible**, también podrás instalarlo desde la carpeta de tu proyecto Quarto:

```bash
quarto add brianmsm/metropolis-spp
```

Usar en el encabezado de cualquier presentación:

```yaml
---
title: "Mi presentación"
format:
  metropolis-spp-revealjs:
    width: 1280
    height: 720
---
```

El comando `quarto use template brianmsm/metropolis-spp` crea un ejemplo inicial. Para renderizarlo directamente desde este repositorio:

```bash
quarto render template.qmd
```

El ejemplo es independiente de R y de los datos del curso; sus fragmentos de código son solo ilustrativos.

## Componentes disponibles

Se usan como clases en bloques de Quarto o HTML:

| Componente | Clase | Finalidad |
|---|---|---|
| Portada temática | `.spp-section-slide` | Introducir un bloque importante |
| Pregunta de portada | `.spp-section-question` | Pregunta breve de apertura |
| Mensaje principal | `.spp-checkpoint` | Conclusión breve, no un párrafo |
| Pregunta al alumnado | `.spp-question` | Anticipar una decisión |
| Dos o tres tarjetas | `.spp-cards` / `.spp-cards-3` + `.spp-card` | Comparación |
| Color semántico | `.spp-card-pink` / `.spp-card-teal` | General/énfasis vs específico |
| Secuencia de tres pasos | `.spp-flow`, `.spp-flow-node`, `.spp-flow-arrow` | Mostrar mecanismos |
| Cuatro métricas | `.spp-metrics` | Conteos con denominador claro |
| Dos columnas | `.spp-compare` | Restricciones y diferencias |
| Procedencia | `.spp-source` | Fuente o carácter hipotético |
| Etiqueta de contexto | `.spp-kicker` | Contextualizar sin decorar |

Hay equivalentes heredados sin prefijo (`.cards`, `.card`, `.checkpoint`, etc.) para facilitar la adaptación desde S01/S02. En material nuevo es preferible usar clases `.spp-*`. El formato también incorpora estilos compartidos de encabezados, tablas, código, fórmulas, SVG, citas y número de lámina.

La [demo](template.qmd) contiene ejemplos mínimos. El estilo reutilizable se concentra en [`spp.scss`](_extensions/metropolis-spp/spp.scss), sin copiar hojas CSS enteras de las sesiones.

## Diseño y alcance

- **Uso:** clases y portadas académicas, preferiblemente 16:9 de 1280×720.
- **Paleta:** magenta `#be2161`, turquesa `#118c94` y tinta `#243a42`.
- **No incluidos:** diagramas o filtros de casos concretos (`#s02-asimetria`, `#s02-serie-d`), análisis estadísticos ni resultados.
- **Extensibilidad:** conservar `estilos.css` local para ajustes de una clase sin afectar otras presentaciones.
- **No obliga a actualizar:** las sesiones S01/S02 existentes siguen utilizando sus estilos y formatos actuales hasta que se acepte una migración específica.

## Origen, atribución y licencia

Esta es una **extensión independiente**, no un segundo fork en la red de GitHub.

- **Tema inicial:** [shafayetShafee/metropolis](https://github.com/shafayetShafee/metropolis), inspirado en Metropolis de Beamer y en CSS de Vince Hodges.
- **Base específica:** [brianmsm/metropolis](https://github.com/brianmsm/metropolis) en el commit `6728c302339bde543e7ce23ffc63393c0df163f5`.
- **Código reutilizado sin cambios:** `metropolis.scss`, `metropolis.lua`, `asset/` y `resources/` dentro de la extensión.
- **Nueva identidad visual:** `spp.scss` y manifiesto `_extension.yml`, desarrollados a partir de las correcciones docentes de las sesiones 01 y 02 del curso Modelos Bifactor con R.
- **Licencia:** MIT; se conservan las atribuciones y permisos del original en [LICENSE](LICENSE).

Los cambios y límites de compatibilidad están documentados en [Origen y compatibilidad](docs/ORIGEN_Y_COMPATIBILIDAD.md).
