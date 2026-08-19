# Modo B — Ejecución

Para cuando la identidad **ya está decidida**. No se re-discute: se aplica.

Tres situaciones entran aquí:
- **B1 — Formalizar**: existe la identidad pero está dispersa (en la cabeza, en un PDF, en el código). Hay que consolidarla en los entregables.
- **B2 — Producir**: hay que crear algo concreto (landing, post, carrusel, presentación) respetando la identidad existente.
- **B3 — Auditar**: comprobar si lo que existe es coherente y detectar dónde se rompe.

---

## Regla que gobierna todo el modo B

> **Nunca inventes identidad.**

Si falta un dato —no hay tipografía definida, no hay arquetipo, la paleta solo tiene un color— **pregunta**. No rellenes con un valor plausible, aunque sea razonable y encaje bien.

Una marca a medias declarada es recuperable. Una marca a medias **inventada** contamina todo lo que se construya encima, porque nadie recordará qué decidió el equipo y qué decidió la IA.

**Excepción única**: valores derivados mecánicamente de otros ya decididos (por ejemplo, calcular un `--color-primary-hover` un 10% más oscuro que el primario). Eso es cálculo, no invención — pero decláralo como derivado.

---

## B1 — Formalizar identidad existente

### Paso 1: recolectar
Busca en el proyecto y en lo que aporte el usuario:

| Fuente | Qué extraer |
|---|---|
| Código (`tailwind.config`, CSS, variables) | Paleta y tipografía **reales en producción** |
| `assets/`, `public/` | Logo, versiones, favicon |
| Brand book, PDF, presentación | Estrategia, valores, buyer personas |
| Web o app en vivo | Tono real, no el declarado |
| Redes sociales | Tono real por canal, pilares implícitos |

### Paso 2: detectar contradicciones
**Este paso es obligatorio y es el que más valor aporta.**

Es normal que las fuentes no coincidan: el brand book dice una tipografía y el código usa otra; la presentación tiene una paleta y la landing otra. **No elijas en silencio.** Presenta la contradicción y pregunta cuál es la fuente de verdad.

Criterios de desempate útiles cuando el usuario duda:
- **Lo más reciente** suele ganar, pero no siempre
- **Lo presentado/aprobado formalmente** pesa más que un borrador
- **Lo que está en producción** refleja la realidad, aunque no sea lo deseado
- **Lo generado por IA sin revisar** pesa menos que lo decidido por una persona

> Señal de alerta: si un documento de marca contiene frases en primera persona explicando limitaciones técnicas ("mi entorno no tiene esa fuente instalada"), es un borrador de IA sin revisar. No es fuente de verdad.

### Paso 3: completar huecos
Recorre los 4 ejes y lista qué falta. Los huecos habituales:
- Arquetipo (casi nunca está definido)
- Palabras prohibidas
- Negative prompt / reglas de qué no encaja
- Emoción objetivo por touchpoint

Para cada hueco: pregunta o marca explícitamente como **pendiente** en el entregable. Un `"archetype": null` honesto vale más que uno inventado.

**Logo — tratar los dos casos con el mismo nivel de cuidado, ninguno se queda como referencia suelta:**
- **Si el proyecto ya tiene logo** (en `assets/`, `public/`, o aportado por el usuario): **cópialo tal cual** a `brand/logo/`. Es el logo real de la marca — no se rediseña, se importa completo (todas las versiones que existan: claro, oscuro, favicon...).
- **Si no tiene y la verificación externa confirma que no existe en ningún sitio**: **genéralo** — ver [checklist de validación, "Si aún no hay logo"](../checklists/validacion-logo.md#si-aún-no-hay-logo-generarlo-no-solo-dejarlo-pendiente).
- **En ambos casos**: monta una vista previa (HTML, fondo claro/oscuro, tamaño normal y 16-32px) y tómale una captura de pantalla real antes de darlo por cerrado — no asumas que se ve bien solo porque el archivo existe.

### Paso 4: generar entregables
`BRAND.md` → `brand.json` → `design-tokens.css` → bloque de prompt externo.
Plantillas en [`templates/`](../templates/).

---

## B2 — Producir con la identidad

### Antes de generar nada
Carga `brand.json`. Si no existe, ejecuta B1 primero — producir sin contrato de marca es exactamente lo que esta skill existe para evitar.

### Para contenido escrito
1. Aplica `voice.tone`, `voice.person`, `voice.emoji`
2. Usa un framework de copy de ch04 según el formato (PAS para email, AIDA para anuncio, 4P para landing, Storytelling para redes)
3. Si es texto largo, usa el **Método Lego** de ch04 — nunca one-shot
4. Verifica que el tema pertenece a un `content.pillars`
5. **Pasa el [checklist anti-AI-slop](../checklists/anti-ai-slop.md)** — no negociable
6. Comprueba que no aparece ninguna `voice.bannedWords`

### Para imágenes
1. Toma `aiDirectives.styleprompt` **literalmente**, sin reescribirlo
2. Construye el prompt con los 5 componentes de ch08 (sujeto, acción/entorno, estilo, composición/cámara, técnicos)
3. Añade `aiDirectives.negativePrompt` siempre
4. Usa el aspect ratio del canal según `aiDirectives.aspectRatios`
5. Si generas varias piezas, usa JSON para que solo cambien `prompt` y `details`

### Para interfaz (web, app, landing)
1. Genera o carga `design-tokens.css`
2. **Ningún HEX literal en el CSS** — siempre `var(--color-*)`
3. Verifica contraste WCAG AA de las combinaciones reales
4. Pasa el relevo a `ui-ux-pro-max` → `frontend-design` → `ui-styling` con el `brand.json` como entrada

### Para presentaciones y documentos
Aplica paleta y tipografía reales. Si la herramienta no dispone de la tipografía de marca, **decláralo** en vez de sustituir en silencio: "esta presentación usa X porque Manrope no está disponible aquí".

---

## B3 — Auditar coherencia

Diagnóstico en cuatro capas, usando el IKIGAI de [ch06](../chapters/ch06-experiencia-marca.md) como marco.

### Capa 1 — Estrategia
- [ ] ¿La misión sirve igual para un competidor?
- [ ] ¿Los valores implican alguna renuncia real?
- [ ] ¿Está escrito qué NO son?
- [ ] ¿La propuesta de valor del BMC y la del brand book son la misma frase?

### Capa 2 — Verbal
- [ ] ¿Hay arquetipo definido y documentado?
- [ ] ¿El tono es el mismo en web, redes y email? (leer 3 piezas reales de canales distintos)
- [ ] ¿Existen palabras prohibidas? ¿Se respetan?
- [ ] ¿Los textos publicados contienen TICS de IA?

### Capa 3 — Visual
- [ ] ¿La paleta del brand book coincide con la del código en producción?
- [ ] ¿La tipografía declarada es la que realmente carga?
- [ ] ¿El logo pasa las 8 preguntas del [checklist](../checklists/validacion-logo.md)?
- [ ] ¿Se reconocería una pieza como suya **sin logo**?

### Capa 4 — Experiencia y contenido
- [ ] ¿Cada touchpoint tiene una emoción objetivo distinta?
- [ ] ¿Los pilares de contenido hablan del producto? *(fallo muy frecuente)*
- [ ] ¿El mapa de canales incluye Paid y Earned, o solo Owned?
- [ ] ¿Hay canales en todas las fases (atraer/convertir/activar/fidelizar)?

### Formato del informe
Para cada hallazgo:
```
[Severidad: crítico | importante | menor]
Qué encontré:      (con la evidencia concreta: archivo, línea, captura, cita)
Por qué es problema: (contra qué regla del método va)
Cómo se corrige:    (acción concreta, no "revisar")
```

Ordena por severidad. **Crítico** = rompe la coherencia de marca visible para el cliente (paleta distinta entre web y redes, tono contradictorio). **Menor** = deuda de documentación.

No conviertas la auditoría en una lista de 40 puntos. Cinco hallazgos accionables valen más que cuarenta observaciones.
