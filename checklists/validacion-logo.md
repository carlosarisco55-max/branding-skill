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

## Si aún no hay logo

**No es bloqueante.** El logo es el último paso de la identidad visual, no el primero. Se puede cerrar el brand book completo con el logo pendiente, y de hecho es mejor así: el brief para diseñarlo sale de tener el arquetipo, la paleta, la tipografía y el estilo ya decididos.

Brief mínimo para encargarlo (o generarlo):
- Arquetipo principal y secundario
- Emoción objetivo
- Paleta con HEX
- Tipografía de marca
- 3–5 adjetivos de estilo visual
- Lista `doNot`
- Los 3 competidores de los que hay que diferenciarse
