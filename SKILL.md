---
name: branding
description: "Construye o ejecuta la identidad de marca completa de un proyecto — estrategia (misión/visión/valores, DAFO/CAME, BMC, buyer persona), arquetipo de marca, identidad verbal (tono, mensajes, palabras prohibidas), identidad visual (paleta HEX, tipografía, logo, estilo) y experiencia (touchpoints, pilares de contenido, mapa de canales). Produce un brand book en markdown, un brand.json estructurado y design tokens CSS que después consumen ui-ux-pro-max, frontend-design y ui-styling. Úsalo al arrancar cualquier marca, landing, app, blog o campaña nueva, al auditar si una marca existente es coherente, o antes de generar contenido/diseño para que la IA respete la identidad. Basado en el Módulo 5 del Máster en Marketing Digital e IA Generativa (Inesdi, Eva Romeu y Marc Mora) y validado sobre el caso Contening."
---

<!-- argument-hint: [nombre de marca, "auditar", "solo visual", o número de capítulo] -->

# Branding: de la estrategia a la identidad ejecutable

**Fuente teórica**: Módulo 5 "Generación de contenidos de marketing con IA generativa" — Eva Romeu y Marc Mora (byBarber Agency), Inesdi 2026, Máster en Marketing Digital e IA Generativa.
**Caso aplicado de referencia**: Contening (ver `ejemplo-contening.md`).

---

## Regla de oro

> Si quitamos el logo, ¿se nos reconoce?

Una marca no es un logotipo ni una paleta. Es el conjunto de sentimientos y experiencias que la audiencia crea a partir del producto o servicio. El branding solo funciona con **sencillez, personalidad y consistencia**.

Y el test moderno de esa regla, el que da sentido a esta skill:

> ¿Podríamos explicarle a una IA cómo debe hablar y crear para nuestra marca?

Si la respuesta es no, la marca no está definida — está intuida. El entregable `brand.json` de esta skill existe precisamente para convertir ese "no" en "sí".

---

## Los 4 ejes del brand book

Toda marca se construye sobre estos cuatro ejes. Ninguno es opcional, y el orden importa: cada uno se deriva del anterior.

| Eje | Pregunta | Capítulo |
|---|---|---|
| **1. Base estratégica** (ADN) | ¿Quiénes somos y qué prometemos? | [ch01](chapters/ch01-base-estrategica.md), [ch02](chapters/ch02-analisis-estrategico.md) |
| **2. Identidad verbal** | ¿Cómo habla la marca? | [ch03](chapters/ch03-arquetipos.md), [ch04](chapters/ch04-identidad-verbal.md) |
| **3. Identidad visual** | ¿Cómo se ve la marca? | [ch05](chapters/ch05-identidad-visual.md) |
| **4. Experiencia de marca** | ¿Cómo se vive la marca? | [ch06](chapters/ch06-experiencia-marca.md), [ch07](chapters/ch07-pilares-y-canales.md) |

El **arquetipo de marca** (ch03) es la bisagra: se decide al final del eje 1 y determina simultáneamente el eje 2 y el eje 3. Sin arquetipo definido, tono y estilo visual acaban desconectados.

---

## Cómo funciona esta skill: dos modos

Al invocarla, **lo primero es detectar en qué situación está el proyecto**:

```
¿Existe ya identidad de marca definida?
├── Busca: brand.json, BRAND.md, brandbook, design-tokens, tailwind.config,
│          paleta en CSS/variables, guía de estilo, logo en assets
│
├── NO hay nada, o solo hay un nombre        → MODO A: Descubrimiento
├── Hay material disperso o incompleto       → MODO A parcial (solo los ejes que falten)
└── Hay identidad completa y documentada     → MODO B: Ejecución
```

### MODO A — Descubrimiento
La marca no sabe todavía qué quiere (visual, verbal o estratégicamente). Se construye desde cero mediante preguntas guiadas, eje por eje.
→ Sigue [`workflows/modo-a-descubrimiento.md`](workflows/modo-a-descubrimiento.md)

### MODO B — Ejecución
La identidad ya está decidida. No se re-discute: se aplica, se traduce a entregables y se usa para producir.
→ Sigue [`workflows/modo-b-ejecucion.md`](workflows/modo-b-ejecucion.md)

**Nunca inventes identidad en Modo B.** Si en modo ejecución falta un dato (por ejemplo, no hay tipografía definida), pregunta — no rellenes con un valor plausible. Una marca inventada a medias es peor que una marca incompleta declarada.

---

## Entregables

| Archivo | Qué es | Quién lo consume |
|---|---|---|
| `BRAND.md` | Brand book legible: los 4 ejes documentados | Personas del equipo |
| `brand.json` | La marca como datos estructurados | `ui-ux-pro-max`, `frontend-design`, `ui-styling`, generadores de imagen |
| `design-tokens.css` | Paleta y tipografía como variables CSS | El código del proyecto |
| Bloque de prompt externo | Identidad comprimida para pegar fuera | Midjourney, ChatGPT, Canva, Gamma |

Plantillas en [`templates/`](templates/). El `brand.json` usa claves en inglés a propósito, para encajar con las skills de diseño y con CSS; el contenido va en el idioma de la marca.

---

## Cinco reglas vinculantes

Estas no son recomendaciones. Si el trabajo las incumple, hay que corregirlo antes de continuar.

1. **El arquetipo es obligatorio.** Principal + secundario, decididos con el test de ch03. Es lo que evita que el tono y el diseño vayan por caminos distintos.

2. **Los pilares de contenido NO hablan del producto.** Un pilar es una temática sobre la que la marca tiene autoridad y que le interesa al buyer persona. "Producto", "Casos de uso" o "Nuestras funcionalidades" **no son pilares** — son contenido comercial que se inserta *dentro* de un pilar. Si un pilar propuesto describe el producto, recházalo y reformúlalo.

3. **Ningún texto sale sin pasar el filtro anti-AI-slop.** Ver [`checklists/anti-ai-slop.md`](checklists/anti-ai-slop.md). La IA propone, el criterio humano dispone.

4. **No se inventan datos de marca.** Ni testimonios, ni cifras de clientes, ni social proof, ni funcionalidades que no existen. Si la marca es pre-lanzamiento, se dice.

5. **Toda decisión visual lleva su HEX y su nombre exacto de tipografía.** "Un azul corporativo" no es una decisión, es una intención. `#003366` sí lo es.

---

## Índice de capítulos

| # | Título | Frameworks clave |
|---|---|---|
| [ch01](chapters/ch01-base-estrategica.md) | Base estratégica (ADN) | Misión/visión/valores, propuesta de valor, posicionamiento, 3 fórmulas de elevator pitch |
| [ch02](chapters/ch02-analisis-estrategico.md) | Análisis estratégico | PESTEL → DAFO → CAME, Business Model Canvas, target vs buyer persona, benchmarking (7 KPIs) |
| [ch03](chapters/ch03-arquetipos.md) | Arquetipo de marca | 12 arquetipos de Jung, test de 24 preguntas, derivación a tono y visual |
| [ch04](chapters/ch04-identidad-verbal.md) | Identidad verbal | Tono de voz, storytelling, mensajes clave, palabras permitidas/prohibidas, slogan, 6 frameworks de copy |
| [ch05](chapters/ch05-identidad-visual.md) | Identidad visual | Logo, paleta, tipografía, estilo visual, key visual, aplicaciones, checklist de logo |
| [ch06](chapters/ch06-experiencia-marca.md) | Experiencia de marca | Touchpoints, IKIGAI del branding, emociones por punto de contacto |
| [ch07](chapters/ch07-pilares-y-canales.md) | Pilares y canales | Pilares de contenido, modelo POEM, mapa de canales, reutilización en cascada |
| [ch08](chapters/ch08-marca-ejecutable-por-ia.md) | Marca ejecutable por IA | Prompt de estilo base, `brand.json`, negative prompt, consistencia visual |

## Índice temático

- **Arquetipo / personalidad de marca** → ch03
- **Benchmarking / competencia** → ch02
- **Buyer persona / target** → ch02
- **Business Model Canvas** → ch02
- **Calendario editorial** → ch07
- **Colores / paleta / HEX** → ch05, ch08
- **DAFO / CAME / PESTEL** → ch02
- **Design tokens / CSS** → ch08, `templates/design-tokens.css`
- **Elevator pitch** → ch01
- **IKIGAI del branding** → ch06
- **Logo** → ch05, `checklists/validacion-logo.md`
- **Mensajes clave / message house** → ch04
- **Misión, visión, valores** → ch01
- **Palabras prohibidas / TICS de IA** → ch04, `checklists/anti-ai-slop.md`
- **Pilares de contenido** → ch07
- **POEM (paid/owned/earned)** → ch07
- **Posicionamiento / propuesta de valor** → ch01
- **Prompts para generar imágenes de marca** → ch08
- **Slogan / claim / naming** → ch04
- **Tipografía** → ch05
- **Tono de voz** → ch04
- **Touchpoints** → ch06

---

## Conexión con otras skills

Esta skill produce; otras consumen. Orden recomendado en un proyecto nuevo:

```
/branding  →  brand.json + design-tokens.css
     ↓
ui-ux-pro-max      (decidir dirección de UI a partir del arquetipo y la paleta)
     ↓
frontend-design    (dirigir la ejecución visual)
     ↓
ui-styling         (construir componentes con los tokens)
```

Para producción de contenido (posts, blogs, carruseles, vídeo), `/branding` aporta el `brand.json` y las reglas de tono; la producción en sí es otro dominio.
