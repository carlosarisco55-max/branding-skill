# Checklist de validación de logo

Las 8 preguntas del temario, con criterio de verificación para cada una.

> Un buen logo debe funcionar en todos los canales.

| # | Pregunta | Cómo verificarlo | ✅ |
|---|---|---|---|
| 1 | **¿Se entiende en pequeño?** | Redúcelo a 16×16 px y a 32×32 px. Si el nombre deja de leerse, necesitas una versión isotipo | ☐ |
| 2 | **¿Funciona como avatar de Instagram o favicon?** | Recórtalo en círculo. ¿Se corta algo esencial? ¿Hay márgenes suficientes? | ☐ |
| 3 | **¿Tiene versión horizontal y vertical?** | Necesarias para cabecera web (horizontal) y perfiles/app (vertical o cuadrada) | ☐ |
| 4 | **¿Funciona en blanco y negro?** | Conviértelo a escala de grises. Si el contraste dependía del color, se pierde legibilidad | ☐ |
| 5 | **¿Encaja con el arquetipo de marca?** | Compáralo con `archetype.primary`. Un Gobernante con logo redondeado y colorido no cuadra | ☐ |
| 6 | **¿Transmite la emoción que queremos provocar?** | Compáralo con la emoción objetivo del touchpoint de descubrimiento (ch06) | ☐ |
| 7 | **¿Es coherente con el tono verbal?** | Si el tono es cercano y de tuteo, un logo rígido y corporativo contradice | ☐ |
| 8 | **¿Se diferencia de la competencia?** | Ponlo junto a 3 logos de competidores. Si a distancia se confunden, no diferencia | ☐ |

---

## Verificaciones técnicas adicionales

| Comprobación | Por qué |
|---|---|
| ☐ Existe en **SVG** | Escala sin pérdida; imprescindible para web |
| ☐ Existe en PNG con **fondo transparente** | Para superponer sobre fondos variables |
| ☐ Versión para **fondo claro** y para **fondo oscuro** | Un logo oscuro desaparece en dark mode |
| ☐ **Área de respeto** definida | Espacio mínimo libre alrededor, para que no se ahogue |
| ☐ **Tamaño mínimo** documentado | Por debajo de X px no debe usarse |
| ☐ Usos prohibidos documentados | Deformar, rotar, cambiar color, añadir sombra, sobre fondo con poco contraste |

---

## Versiones mínimas a producir

```
logo-principal.svg          horizontal, fondo claro
logo-principal-dark.svg     horizontal, fondo oscuro
logo-vertical.svg           apilado
isotipo.svg                 solo la marca gráfica
favicon.svg + .png          16, 32, 180 (apple-touch)
logo-mono.svg               blanco y negro
```

---

## Si aún no hay logo: generarlo, no solo dejarlo pendiente

**Regla**: si la [verificación externa (FASE 6bis)](../workflows/modo-a-descubrimiento.md#fase-6bis--verificación-externa-obligatoria-antes-de-cerrar) confirma que no existe ningún logo previo en ningún sitio, **no te limites a documentarlo como pendiente — genera uno real**. Un brand book con "logo: pendiente" no es una identidad completa.

### Por qué SVG generado por código, no imagen de IA

Se evaluó conectar una API de generación de imágenes (Gemini, Leonardo, generadores de logo con IA) y se descartó como método por defecto:

- Los generadores de imagen producen **raster con artefactos**, no vectores limpios — fallan los checks "funciona en blanco y negro" y "se entiende en pequeño" de esta misma tabla
- Herramientas gratuitas de logo con SVG real: **Logolivery estaba anunciado como gratis+SVG pero la empresa está liquidada** (verificar antes de recomendar, cambia con el tiempo); SVGMaker tiene API pero créditos limitados; Kleap/Logo.com son gratis pero sin API, no automatizables desde una skill
- Generar el SVG **directamente como código**, a partir de los datos ya decididos (`archetype`, `visual.colors`, `visual.style`), es gratis, ilimitado, reproducible, y cumple mejor el checklist que cualquiera de las alternativas de arriba

*(Antes de usar cualquiera de las opciones de arriba, vuelve a verificar que siguen existiendo — este tipo de herramientas cambia rápido. Ver [[feedback_verificar_a_fondo_siempre]].)*

### Cómo generarlo (método por defecto)

1. **Deriva el concepto de un mensaje clave o de la propuesta de valor**, no de un icono genérico del sector. Ej.: dos líneas de negocio → dos formas geométricas superpuestas; "transparencia" → formas con opacidad/superposición visible; "velocidad" → diagonales o flechas.
2. **Traduce el arquetipo a geometría**: Gobernante/Sabio → formas simétricas, ángulos rectos, orden; Explorador/Rebelde → asimetría, diagonales; Cuidador/Amante → esquinas redondeadas, superposición cálida; Bufón/Creador → formas más libres, menos simétricas.
3. **Usa los HEX exactos de `visual.colors`**, nunca aproximaciones.
4. Construye como SVG con `viewBox`, formas simples (`rect`, `circle`, `path`) — evita degradados complejos o efectos que no escalen bien a 16px.
5. **Produce el set completo**: isotipo (fondo claro), isotipo (fondo oscuro o mono), horizontal con wordmark (claro y oscuro), favicon a 32px.
6. **Verifica visualmente de verdad** antes de darlo por bueno: renderiza los SVG en una página HTML simple y tómale una captura de pantalla (navegador/Playwright) — no asumas que el código se ve bien solo porque es válido. Prueba explícitamente el tamaño mínimo (16px).
7. Pasa la tabla de las 8 preguntas de arriba contra el resultado real, no contra la intención.

### Brief si se prefiere encargarlo a una persona diseñadora en vez de generarlo
- Arquetipo principal y secundario
- Emoción objetivo
- Paleta con HEX
- Tipografía de marca
- 3–5 adjetivos de estilo visual
- Lista `doNot`
- Los 3 competidores de los que hay que diferenciarse
