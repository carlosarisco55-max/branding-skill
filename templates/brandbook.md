# [NOMBRE DE MARCA] — Brand Book

> [Tagline / slogan]

**Actualizado**: [fecha] · **Fase**: [pre-lanzamiento / crecimiento / consolidada]
**Fuente de verdad**: este documento. Si algo lo contradice (una presentación antigua, un PDF, el código), gana este archivo — o se actualiza aquí.

---

## 1. Qué es [Marca]

[Un párrafo. Qué hace, para quién, y por qué existe. Sin adjetivos de más.]

**Elevator pitch**
> [30–60 segundos. Fórmula 1, 2 o 3 de ch01.]

---

## 2. Base estratégica

### Misión
[Para qué existe hoy.]

### Visión
[Dónde quiere estar en 5–10 años.]

### Valores
Cada valor incluye la renuncia que implica. Un valor que no descarta nada no es un valor.

**[Valor 1]**: [qué implica renunciar]
**[Valor 2]**: [qué implica renunciar]
**[Valor 3]**: [qué implica renunciar]

### Propuesta de valor
[Qué ofrece de único frente a la competencia. Una frase.]

### Posicionamiento
[El lugar que quiere ocupar en la mente del cliente.]

### Qué NO somos
- [ ]
- [ ]

---

## 3. Arquetipo de marca

| | Arquetipo | Peso |
|---|---|---|
| **Principal** | [nombre] | 80% |
| **Secundario** | [nombre] | 20% |

**Por qué**: [justificación desde la estrategia. Obligatorio.]

**Frente a la competencia**: [con qué arquetipos se identifican los competidores y por qué este nos diferencia.]

---

## 4. Identidad verbal

### Tono de voz
Formulado en tensiones, no en adjetivos sueltos:

- [Adjetivo], pero no [exceso] → [qué significa en la práctica]
- [Adjetivo], pero no [exceso] → [qué significa en la práctica]
- [Adjetivo], pero no [exceso] → [qué significa en la práctica]

### Estilo
- **Trato**: [tuteo / usted]
- **Emojis**: [regla concreta por canal]
- **Anglicismos**: [permitidos / evitar / cuáles]
- **Idioma por defecto**: [ ]

### Mensajes clave
| Mensaje | Razón para creer |
|---|---|
| | |
| | |
| | |

### Palabras permitidas
`palabra` · `palabra` · `palabra`

### Palabras prohibidas
`palabra` · `palabra` · `palabra`
*Más los TICS de IA — ver [checklist anti-AI-slop](../checklists/anti-ai-slop.md).*

### Slogan
**Seleccionado**: [ ]
*Descartados*: [ ] · [ ]

---

## 5. Identidad visual

### Paleta

| Rol | HEX | Uso |
|---|---|---|
| Base oscura | `#` | |
| Primario | `#` | |
| Secundario | `#` | |
| Acento | `#` | |
| Fondo claro | `#` | |

*Proporción 60/30/10. Contraste verificado WCAG AA.*

### Tipografía
- **Display / titulares**: [Familia], pesos [ ], vía [fuente]
- **Texto / cuerpo**: [Familia], pesos [ ], vía [fuente]
- **Fallback**: `-apple-system, BlinkMacSystemFont, system-ui, sans-serif`

### Estilo visual
[3–5 adjetivos] · [descripción del mundo gráfico: fotografía o ilustración, tratamiento, texturas, iconografía]

### Key visual
[El elemento reconocible que se repite. Lo que hace que una pieza se identifique **sin logo**.]

### Qué NO encaja
- [ ]
- [ ]
- [ ]

### Logo
[Versiones disponibles, tamaño mínimo, área de respeto, usos prohibidos. Si no hay logo todavía, decirlo — no es bloqueante.]

---

## 6. Audiencia

### Target
[Segmentación cuantitativa que delimita el mercado.]

### Buyer persona principal — [Nombre]
**[Edad] · [Rol] · [Ubicación]**

[Biografía breve.]

**Puntos de dolor**: · · ·
**Motivos de compra**: · · ·
**Objetivos**: · · ·
**Canales**: · · ·
**Cómo nos encuentra**: [ ]
**Percepción de la marca**: [ ]

> *"[Cita textual que resume su frustración. Es el elemento más reutilizable de toda la ficha: aparece reformulada en carruseles, blogs y anuncios.]"*

### Buyer personas secundarios
[1–2, en formato reducido.]

---

## 7. Contenido y canales

### Pilares de contenido
Recordatorio: **ningún pilar habla del producto.**

**1. [Pilar]** — subtemas: · ·
**2. [Pilar]** — subtemas: · ·
**3. [Pilar]** — subtemas: · ·

### Mapa de canales

| Canal | Tipo | Objetivo | Fase | Pilares | Tono | Frecuencia | KPI |
|---|---|---|---|---|---|---|---|
| | owned/paid/earned | | atraer/convertir/activar/fidelizar | | | | |

---

## 8. Experiencia de marca

### Promesa
[Qué garantiza la marca en cada interacción.]

### Touchpoints

| Touchpoint | Fase | Emoción objetivo | CTA | Fricción a eliminar |
|---|---|---|---|---|
| | | | | |

---

## 9. Uso con IA

### Prompt de estilo base
Pégalo **literalmente** al final de cualquier prompt de imagen:

```
, [medio] [estilo], paleta [#HEX, #HEX, #HEX], [luz], [composición]
```

### Negative prompt
```
[qué no encaja con la marca] + bad anatomy, extra fingers, watermark, signature
```

### Aspect ratios
Blog `16:9` · Redes `1:1` · Stories `9:16`

### Bloque para herramientas externas
Ver [`prompt-externo.md`](prompt-externo.md) — versión comprimida para pegar en Midjourney, ChatGPT, Canva o Gamma, donde no se puede leer este documento.

---

## 10. Reglas innegociables

1. Ningún texto sale sin pasar el [checklist anti-AI-slop](../checklists/anti-ai-slop.md)
2. No se inventan datos, testimonios ni funcionalidades
3. Ningún HEX literal en el código: siempre `var(--color-*)`
4. Los pilares de contenido no hablan del producto
5. Si falta un dato de marca, se pregunta — no se rellena

---

## Archivos relacionados

| Archivo | Para qué |
|---|---|
| `brand.json` | Contrato legible por máquina; lo consumen las skills de diseño |
| `design-tokens.css` | Variables CSS para el código |
| `prompt-externo.md` | Bloque para herramientas de IA externas |
