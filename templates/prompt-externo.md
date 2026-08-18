# Bloque de prompt externo

Versión comprimida de la identidad, para pegar en herramientas que **no pueden leer el brand book**: Midjourney, ChatGPT, Gemini, Canva IA, Gamma, Napkin, Adobe Express.

Rellena los campos y guárdalo junto al brand book. Es el archivo que el usuario copiará más veces — mantenlo corto y denso.

---

## Plantilla general

```
Estoy creando [contenido / diseño] para [MARCA], [qué es en una frase].
Slogan: "[slogan]".

IDENTIDAD VISUAL (obligatoria, no la cambies):
- Tipografía: [Display] para títulos, [Body] para texto
- Paleta: #HEX (base oscura), #HEX (primario), #HEX (secundario), #HEX (acento), #HEX (fondo claro)
- Estilo: [3-5 adjetivos] — nunca genérico

TONO DE VOZ: [tensiones del tono]. Trato de [tú/usted]. [Regla de emojis].
Estructura habitual: [patrón narrativo de la marca].
Frase ancla: "[mensaje clave principal]".

AUDIENCIA: [buyer persona en una línea, con su dolor principal].

NO HACER:
- No inventes testimonios, cifras de clientes ni funcionalidades. [Fase del producto].
- No uses: [palabras prohibidas].
- Evita: [elementos visuales que no encajan].
- Nada genérico que pudiera servir para cualquier otra marca del sector.

Ahora, con esto en mente: [describe aquí lo que necesitas]
```

---

## Variante para generación de imágenes

Más corta, porque los generadores de imagen ignoran el texto largo:

```
[SUJETO hiperespecífico], [acción y entorno], [estilo artístico],
[composición y cámara], paleta [#HEX, #HEX, #HEX], [iluminación]
--ar [ratio]

Negative: [qué no encaja con la marca], bad anatomy, extra fingers,
watermark, signature, texto ilegible
```

### Versión JSON (para consistencia entre varias piezas)
Mantén constantes los bloques `style` y `generation`; cambia solo `prompt` y `details`:

```json
{
  "prompt": "",
  "details": { "subject": {}, "action": "", "location": {}, "mood": "" },
  "style": {
    "art_style": "",
    "lighting": "",
    "color_palette": "#HEX, #HEX, #HEX",
    "camera": { "perspective": "", "focus": "" }
  },
  "generation": { "size": "1024x1024", "n": 1, "format": "png" },
  "negative_prompt": ""
}
```

---

## Variante para texto (blog, post, email)

```
Escribe [formato] para [MARCA] dirigido a [buyer persona].
Tema: [tema] — pertenece al pilar "[pilar]".

TONO: [tensiones]. Trato de [tú/usted]. [Emojis].
ESTRUCTURA: usa el framework [PAS / AIDA / 4P / BAB / Storytelling].

PROHIBIDO (son marcas de texto generado por IA):
- "No solo... sino que", "Desde... hasta"
- Titulares Con Mayúscula En Cada Palabra
- Las palabras "emocionante", "aprendizaje", "memorable", "revolucionario"
- Exceso de emojis, guiones largos donde va un paréntesis
- Cadenas de frases cortas del mismo ritmo
- [palabras prohibidas propias de la marca]

Además: sé crítico conmigo si lo que te pido no es buena idea.
No inventes datos, cifras ni testimonios.
```

> La última instrucción ("sé crítico") contrarresta la **AI sycophancy**: por defecto, la IA rara vez te contradice aunque le pidas algo que no funciona.

---

## Recordatorio

Este bloque es un **resumen**, no la fuente de verdad. Si hay conflicto entre lo que dice aquí y el brand book, gana el brand book. Cuando cambie la identidad, actualiza los dos.
