# Ch05 — Identidad visual (cómo se ve la marca)

Tercer eje. La identidad visual es el conjunto de decisiones gráficas que hacen que una marca sea **reconocible, coherente y diferenciable** en todos sus puntos de contacto. Es cómo la marca traduce visualmente su personalidad, su propuesta de valor y su promesa.

Se deriva del arquetipo (ch03). No se decide por gusto personal ni por lo que está de moda.

---

## Los seis elementos

| Elemento | Qué es |
|---|---|
| **Logo** | El signo principal. Reconocible, legible y adaptable a distintos formatos |
| **Paleta de colores** | Los colores transmiten personalidad y emoción. Una marca premium, una divertida y una tecnológica no usan el color igual |
| **Tipografías** | La elección tipográfica comunica: autoridad, cercanía, modernidad, artesanía, elegancia, dinamismo |
| **Estilo visual** | El tipo de imágenes, ilustraciones, composiciones, iconos, texturas o recursos gráficos que usará la marca |
| **Key visual** | La imagen o sistema gráfico principal de una campaña o marca. Lo que ayuda a reconocer visualmente la comunicación |
| **Aplicaciones** | Cómo se ve la marca en redes, web, packaging, presentaciones, cartelería, email, anuncios |

---

## Paleta de colores

### Estructura mínima
Toda paleta necesita **roles**, no solo colores. Un HEX sin rol es una decoración; con rol es un sistema.

| Rol | Función | Cuántos |
|---|---|---|
| **Base oscura** | Texto principal, fondos oscuros, contraste máximo | 1 |
| **Primario** | Acciones, CTAs, acento de marca | 1 |
| **Secundario** | Estados hover, apoyo del primario | 1 |
| **Acento** | Destacados, iconografía, contraste de temperatura | 1–2 |
| **Fondo claro** | Superficies claras, fondos suaves | 1 |
| **Neutros** | Bordes, texto secundario, deshabilitados | 2–4 |

### Reglas
- **Siempre con HEX.** "Un azul corporativo" no es una decisión. `#003366` sí.
- **Proporción 60/30/10**: 60% neutro/fondo, 30% color de apoyo, 10% primario. El primario destaca porque es escaso.
- **Contraste verificable**: texto sobre fondo debe cumplir WCAG AA (4.5:1 texto normal, 3:1 texto grande). Si el primario no pasa contra blanco, necesitas una variante oscura para texto.
- **Nunca definir un color solo para modo oscuro**: define la paleta clara completa y redefine solo lo que cambia.

### Del arquetipo al color
Ver tabla de derivación en [ch03](ch03-arquetipos.md#derivación-del-arquetipo-al-tono-y-al-color).

---

## Tipografía

### Estructura mínima
```
Display / titulares  → la que da personalidad
Texto / cuerpo       → la que se lee sin cansar
(Mono)               → solo si hay código o datos
```

Puede ser **la misma familia** en ambos roles, variando solo el peso — es una decisión válida y frecuente en marcas tecnológicas (ej. Inter en todo, peso 800 en titulares).

### Reglas
- **Nombre exacto y fuente de instalación.** "Una sans moderna" no vale. "Manrope, vía Google Fonts" o "Inter Variable, vía `@fontsource-variable/inter`" sí.
- **Siempre con fallback stack.** La tipografía puede no cargar; define qué pasa entonces.
- **Máximo 2 familias.** Tres o más fragmentan la identidad.
- **Documenta los pesos usados**, no solo la familia. Una marca que usa Inter 400/600/800 es distinta de una que usa Inter 300/400.

> ⚠️ **Trampa frecuente**: si generas mockups o PDFs con una IA que no tiene tu tipografía instalada, sustituirá por otra sin avisar. El brand book debe declarar la tipografía **real**, no la que apareció en el mockup. Verifica siempre contra el código, no contra la imagen.

---

## Logo: checklist de validación

Un buen logo debe funcionar en todos los canales. Ocho preguntas de control:

1. ¿Se entiende en pequeño?
2. ¿Funciona como avatar de Instagram o favicon?
3. ¿Tiene versión horizontal y vertical?
4. ¿Funciona en blanco y negro?
5. ¿Encaja con el arquetipo de marca?
6. ¿Transmite la emoción que queremos provocar?
7. ¿Es coherente con el tono verbal?
8. ¿Se diferencia de la competencia?

Versión ampliada: [`checklists/validacion-logo.md`](../checklists/validacion-logo.md).

### Versiones mínimas a producir
- Principal (horizontal)
- Compacta / vertical
- Isotipo solo (avatar, favicon)
- Sobre fondo claro / sobre fondo oscuro
- Monocromo (blanco y negro)

---

## Estilo visual y key visual

El **estilo visual** define el mundo gráfico: fotografía vs ilustración, nivel de realismo, tratamiento de color, texturas, iconografía, uso de espacio.

El **key visual** es el elemento reconocible que se repite. Puede ser un motivo gráfico, un tratamiento de imagen, una forma o una composición. Es lo que permite responder que sí a la pregunta clave:

> ¿Cómo se ve una pieza "de marca" **sin logo**?

Si la respuesta es "no se sabría que es nuestra", falta key visual.

---

## De la estrategia a la identidad visual con IA

El curso define un flujo de tres pasos. **Requisito previo**: subir a la IA todos los documentos de marca ya trabajados. Cuanta más información tenga sobre la marca, más útil será la respuesta.

Frase de encuadre recomendada antes de nada:
> *"Queremos crear una primera guía visual para una marca de [sector], coherente con la estrategia definida y aplicable a redes sociales, web y materiales comerciales. No hagas nada de momento, analiza únicamente los documentos que te subiré."*

### Paso 1 — Propuesta visual
> Actúa como director creativo especializado en branding para marcas de **[sector]**. He subido la información previa de nuestra marca. A partir de esa información, ayúdanos a definir una guía visual de marca. Desarrolla de forma clara y concreta:
> 1. La esencia visual de la marca en 3 a 5 conceptos
> 2. Una propuesta de logo o estilo de logo
> 3. Una paleta de colores principal y secundaria **con códigos HEX**
> 4. Tipografía principal y secundaria, explicando su uso
> 5. El estilo visual general de la marca
> 6. El estilo fotográfico
> 7. Una propuesta de packaging *(si aplica)*
> 8. Una propuesta de aplicación en redes sociales, web y otros canales
> 9. **Reglas visuales básicas: qué encaja y qué no encaja con la marca**
>
> No queremos una respuesta muy teórica. Queremos una propuesta clara, visual y fácil de convertir en una presentación de 10 diapositivas.

El punto 9 es el más importante: es lo que después se convierte en el `negative_prompt` del ch08.

### Paso 2 — Estructura de presentación
Diez diapositivas: portada · esencia visual · logo · paleta · tipografías · estilo visual/moodboard · fotografía · packaging · aplicaciones · reglas de uso.
Para cada una: título, contenido, texto breve y **sugerencia visual** de qué debería verse.

### Paso 3 — Imágenes de referencia
> A partir de la identidad visual definida, genera imágenes de referencia: portada de marca, moodboard visual, packaging *(si aplica)* y aplicación en redes/web. El estilo debe ser coherente con el arquetipo, la personalidad verbal y la identidad visual definida. La marca debe parecer cuidada, coherente y con una estética clara. **Evita soluciones genéricas o visualmente incoherentes.**

---

## Cómo se documenta

```json
"visual": {
  "colors": {
    "base": "#060910",
    "primary": "#6938EF",
    "secondary": "#899CFF",
    "accent": "#42D9C8",
    "surface": "#C8E8FF"
  },
  "typography": {
    "display": { "family": "Manrope", "weights": [700, 800], "source": "Google Fonts" },
    "body": { "family": "Inter", "weights": [400, 600], "source": "Google Fonts" },
    "fallback": "-apple-system, BlinkMacSystemFont, system-ui, sans-serif"
  },
  "style": ["moderno", "profesional", "confiable", "cercano"],
  "keyVisual": "...",
  "doNot": ["degradados chillones", "stock fotográfico genérico", "iconos de línea fina"]
}
```

El array `doNot` alimenta directamente el negative prompt de [ch08](ch08-marca-ejecutable-por-ia.md).

---

**Siguiente**: [ch06 — Experiencia de marca](ch06-experiencia-marca.md).
