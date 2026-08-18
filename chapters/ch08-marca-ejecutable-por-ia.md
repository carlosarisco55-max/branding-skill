# Ch08 — Marca ejecutable por IA

El capítulo puente. Convierte los cuatro ejes del brand book en algo que una máquina puede aplicar sin reinterpretarlo: datos estructurados, prompts reutilizables y reglas de exclusión.

> **Generar imágenes únicas es fácil. Generar imágenes que parezcan de la misma marca y tengan consistencia es el verdadero desafío.**

Ese es el problema que resuelve este capítulo. Y responde a la pregunta de diagnóstico del ch01: *¿podríamos explicarle a una IA cómo debe hablar y crear para nuestra marca?*

---

## 1. El prompt de estilo base

La técnica más simple y la más eficaz. **Define tu estilo visual en una sola frase, con códigos HEX incluidos, y pégala en todos tus prompts.**

Ejemplo del temario:
> `, ilustración minimalista con paleta de colores corporativos [azul #003366, naranja #FF6600], líneas limpias`

Estructura recomendada:

```
, [medio/técnica] + [descriptor de estilo] + paleta [HEX, HEX, HEX]
  + [tratamiento de luz] + [regla de composición]
```

Reglas:
- Va **siempre al final** del prompt, después de describir el sujeto
- **Nunca se improvisa**: se escribe una vez, se guarda en `brand.json` y se copia siempre igual
- Si cambias una palabra, cambias la marca

---

## 2. Los cinco componentes de un prompt de imagen

| Componente | Regla | Ejemplo |
|---|---|---|
| **El sujeto** | Sé hiperespecífico. No es "un perro", es "un corgi galés con gafas de sol y una pajarita roja" | — |
| **La acción y el entorno** | Qué hace y dónde. Da vida y contexto | "bebiendo un café en una terraza parisina en un día lluvioso" |
| **El estilo artístico** | **El componente más importante para marketing.** Determina atmósfera y personalidad | Fotografía hiperrealista, ilustración de acuarela, 3D isométrico, cartoon de los 90, cianotipia, pixel art |
| **La composición y la cámara** | El toque de director. Controla cómo se ve la escena | Primer plano, plano cenital, plano holandés, macro, teleobjetivo, iluminación cinematográfica, luz de neón |
| **Los parámetros técnicos** | Principalmente el aspect ratio | 16:9 blogs · 1:1 o 9:16 redes |

---

## 3. Prompts en JSON: la marca como datos

JSON (*JavaScript Object Notation*) es un formato de texto ligero para datos estructurados: una lista ordenada donde cada cosa tiene un nombre y un valor.

### Por qué sirve para branding
| Ventaja | Qué resuelve |
|---|---|
| **Claridad** | La IA entiende mejor cada parte de la instrucción |
| **Precisión** | Menos riesgo de que ignore detalles |
| **Automatización** | Generas variaciones cambiando **solo un campo** |
| **Consistencia** | Si usas siempre la misma estructura, las imágenes tienen el mismo *look & feel* |

> JSON organiza la información en bloques claros para mayor control; el prompt narrativo es más natural para humanos, pero menos preciso para automatización.

### Ejemplo comparado

**Narrativo:**
> Genera una imagen cuadrada de 1024×1024 que muestre un paisaje de montaña al amanecer con un lago en primer plano, en estilo pintura al óleo. La paleta debe incluir tonos de azul, naranja y verde, con iluminación suave y cálida. Añade niebla ligera sobre el agua y aves volando. No deben aparecer personas ni construcciones modernas.

**JSON:**
```json
{
  "type": "image_generation",
  "prompt": "Paisaje de montaña al amanecer con un lago en primer plano",
  "size": "1024x1024",
  "style": "pintura al óleo",
  "color_palette": ["azul", "naranja", "verde"],
  "lighting": "suave y cálido",
  "additional_details": "Niebla ligera sobre el agua y aves volando",
  "negative_prompt": "Personas, construcciones modernas"
}
```

Mismo resultado, pero el segundo es **reproducible y parametrizable**: cambias `"style"` y tienes la variante, sin reescribir nada más.

### Estructura completa recomendada
```json
{
  "prompt": "descripción del sujeto y la acción",
  "details": {
    "subject": { "age": "", "gender": "", "clothing": "" },
    "action": "",
    "location": { "setting": "", "weather": "", "decor": "" },
    "mood": ""
  },
  "style": {
    "art_style": "",
    "lighting": "",
    "color_palette": "",
    "camera": { "perspective": "", "focus": "" }
  },
  "generation": { "size": "1024x1024", "n": 1, "format": "png" }
}
```

Los bloques `style` y `generation` **son constantes de marca**: se copian igual en cada pieza. Solo cambian `prompt` y `details`.

> ⚠️ **Cuidado con la consistencia de personas.** Cambiar `"ethnicity"` o `"gender"` en el bloque `subject` genera una persona distinta con el mismo escenario. Es útil para producir variedad representativa de forma deliberada — pero revísalo: si generas siempre el mismo perfil demográfico por defecto, estás perpetuando un sesgo sin haberlo decidido.

---

## 4. El negative prompt: el "qué NO encaja" ejecutable

Un **negative prompt** es la instrucción de qué **no** debe aparecer. No es lo que quieres ver (ese es el prompt positivo), sino lo que quieres evitar.

| Problema sin negative prompt | Cómo lo soluciona |
|---|---|
| Distorsiones anatómicas (manos deformes, dedos extra) | `bad anatomy, extra fingers` |
| Artefactos visuales (textos ilegibles, firmas, marcas de agua) | `no signature, no watermark` |
| Deriva de marca (elementos que no son tuyos) | Los `doNot` de tu ch05 |

**Aquí está la conexión clave**: las *"reglas visuales básicas: qué encaja y qué no encaja con la marca"* del brand book (punto 9 del prompt de guía visual, ch05) **son literalmente tu negative prompt permanente**. Se escriben una vez y se reutilizan siempre.

Ejemplo:
```
"negative_prompt": "bad anatomy, extra fingers, watermark, signature,
 degradados chillones, stock fotográfico genérico, iconos de línea fina,
 fondos blancos vacíos, personas sonriendo a cámara tipo banco de imágenes"
```

---

## 5. El contrato `brand.json`

El entregable que hace que esta skill alimente a las demás. Estructura completa:

```json
{
  "$schema": "branding-skill/v1",
  "name": "",
  "tagline": "",
  "language": "es",
  "stage": "prelaunch | growth | established",

  "strategy": {
    "mission": "",
    "vision": "",
    "values": [{ "name": "", "tradeoff": "" }],
    "valueProposition": "",
    "positioning": "",
    "whatWeAreNot": []
  },

  "archetype": {
    "primary": "",
    "secondary": "",
    "rationale": "",
    "ratio": "80/20"
  },

  "voice": {
    "tone": [],
    "person": "tú | usted | nosotros",
    "emoji": "",
    "keyMessages": [],
    "allowedWords": [],
    "bannedWords": [],
    "slogan": ""
  },

  "visual": {
    "colors": {
      "base": "#000000",
      "primary": "#000000",
      "secondary": "#000000",
      "accent": "#000000",
      "surface": "#000000"
    },
    "typography": {
      "display": { "family": "", "weights": [], "source": "" },
      "body": { "family": "", "weights": [], "source": "" },
      "fallback": ""
    },
    "style": [],
    "keyVisual": "",
    "doNot": []
  },

  "audience": {
    "primaryPersona": { "name": "", "role": "", "pains": [], "quote": "" },
    "secondaryPersonas": []
  },

  "content": {
    "pillars": [{ "name": "", "subtopics": [] }],
    "channels": [{ "name": "", "objective": "", "tone": "", "frequency": "", "kpi": "" }]
  },

  "aiDirectives": {
    "styleprompt": "",
    "negativePrompt": "",
    "aspectRatios": { "blog": "16:9", "social": "1:1", "stories": "9:16" }
  }
}
```

### Cómo lo consumen las otras skills
| Skill | Qué lee |
|---|---|
| `ui-ux-pro-max` | `archetype`, `visual.style`, `audience` → decide dirección de UI |
| `frontend-design` | `visual.colors`, `visual.typography` → dirige la ejecución |
| `ui-styling` | `design-tokens.css` generado desde `visual` |
| Generadores de imagen | `aiDirectives.styleprompt` + `negativePrompt` |
| Producción de contenido | `voice`, `content.pillars`, `content.channels` |

---

## 6. Design tokens CSS

De `brand.json` sale directamente el archivo de tokens. Plantilla en [`templates/design-tokens.css`](../templates/design-tokens.css).

```css
:root {
  --color-base: #060910;
  --color-primary: #6938EF;
  --color-secondary: #899CFF;
  --color-accent: #42D9C8;
  --color-surface: #C8E8FF;

  --font-display: 'Manrope', -apple-system, system-ui, sans-serif;
  --font-body: 'Inter', -apple-system, system-ui, sans-serif;
}
```

Regla de oro: **el CSS del proyecto nunca lleva un HEX literal.** Siempre `var(--color-primary)`. Así, un cambio de marca es un cambio de una línea, no una búsqueda global.

---

## 7. Límites: lo que la IA no resuelve

El temario es explícito, y estas advertencias forman parte del método:

| Riesgo | Qué implica para la marca |
|---|---|
| **Alucinación** | La IA inventa datos, fuentes y hechos con total seguridad. Optimiza para sonar convincente, no para ser veraz. **Verifica siempre la información crítica** |
| **Lenguaje robótico** | Textos gramaticalmente perfectos pero planos, predecibles o llenos de clichés. Requiere toque humano y experiencia personal |
| **Falta de coherencia a largo plazo** | La IA puede contradecirse o cambiar el tono entre un post, una serie de imágenes o clips de vídeo si no se le guía de forma muy precisa **en cada petición**. Por eso existe el `brand.json` |
| **AI sycophancy** | La IA rara vez te contradirá cuando le pidas algo que no es buena idea. **Pídele explícitamente que sea crítica con lo que le propones** |
| **Sesgos ocultos** | Los modelos heredan y amplifican sesgos sociales, de género y culturales presentes en sus datos de entrenamiento. Sin revisión, se perpetúan estereotipos |
| **Copyright** | La legislación sobre propiedad intelectual del contenido generado con IA está en desarrollo. Área gris con riesgos legales y éticos |
| **Garbage in, garbage out** | La calidad del resultado es directamente proporcional a la calidad del prompt y de la información facilitada |

### El AI slop y por qué le importa a una marca

La degradación del contenido creado con IA — *"AI slop"* — es contenido de baja calidad que satura las plataformas sin verificación ni valor creativo.

El contexto que lo explica es la **"enshittification"**: las plataformas mueren en tres fases (buenas con los usuarios para crecer → abusan de los usuarios para vender anunciantes → abusan de los anunciantes para quedarse el valor). Eso creó la demanda de contenido infinito; la IA proporcionó la munición barata. El algoritmo premia frecuencia y retención, no calidad.

**Consecuencia estratégica para el branding:**

> Vuestra única defensa es la **autenticidad radical y la coherencia**. Si parece hecho por una máquina para un algoritmo, será ignorado como ruido de fondo.

Es decir: en un entorno saturado de contenido genérico, una identidad de marca fuerte y consistente deja de ser un lujo estético y pasa a ser **la única ventaja competitiva defendible** en comunicación. Ese es el argumento que justifica todo este brand book.

---

**Volver a**: [SKILL.md](../SKILL.md) · **Checklists**: [anti-ai-slop](../checklists/anti-ai-slop.md)
