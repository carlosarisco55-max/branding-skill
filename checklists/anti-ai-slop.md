# Checklist anti-AI-slop

**Puerta de salida obligatoria.** Ningún texto de marca se entrega sin pasar por aquí.

Basado en la lista de TICS y las reglas de criterio del Módulo 5 (Eva Romeu / Marc Mora, Inesdi).

---

## Los TICS: señales de texto generado por IA

Busca y elimina:

- [ ] **"No solo... sino que"** — y sus variantes ("no solo X, también Y")
- [ ] **"Desde... hasta"** como estructura de frase
- [ ] **Titulares Con Mayúscula En Cada Palabra**
- [ ] Las palabras **"emocionante"**, **"aprendizaje"**, **"memorable"**
- [ ] **Exceso de emojis** (regla: los que permita `voice.emoji` del brand.json, ni uno más)
- [ ] **Guion largo (—)** usado donde correspondería un paréntesis o un punto
- [ ] **Cadenas de frases cortas** de ritmo idéntico
- [ ] **Negritas con `**asteriscos**`** en contextos donde no procede

### Otros marcadores frecuentes (ampliación práctica)
- [ ] "En el mundo actual...", "En la era de...", "Hoy más que nunca..."
- [ ] "Es importante destacar que", "Cabe señalar que"
- [ ] "revolucionario", "imprescindible", "clave", "potente" sin justificación
- [ ] Listas de tres elementos con ritmo idéntico y adjetivo final
- [ ] Cierres tipo "En definitiva..." / "En resumen..." que no aportan nada nuevo
- [ ] Preguntas retóricas encadenadas al inicio de párrafo
- [ ] Simetría excesiva: todos los párrafos de la misma longitud

### Ejemplo del temario de lo que NO publicar

> *"Este Emocionante Aprendizaje Sobre Escritura Con IA Te Lleva Desde El Texto Genérico Hasta La Comunicación Auténtica y Memorable, Donde No Solo Evitas Errores Comunes, Sino Que También Desarrollas Una Voz Única."*

Seis TICS simultáneos: mayúsculas en cada palabra, "emocionante", "aprendizaje", "desde... hasta", "memorable", "no solo... sino que".

---

## Las tres reglas de criterio

Antes de publicar, responde:

- [ ] **¿Usé la IA con intención?**
  No uses contenido generado "porque queda bonito". Úsalo porque cuenta algo o es útil. Si la estética no apoya el mensaje y la estrategia, es **decoración vacía**.

- [ ] **¿Mi criterio está presente?**
  La IA propone, tú dispones. Si el resultado no tiene tu visión, tu tono y tu aprobación, no es tuyo. **No firmes lo que no has revisado.**

- [ ] **¿Fui editor y no mensajero?**
  No hagas de intermediario entre el prompt y la publicación. Corta, pule, reencuadra y mejora.

---

## Verificación de marca

- [ ] ¿Aparece alguna palabra de `voice.bannedWords`?
- [ ] ¿El tono coincide con `voice.tone` y su modulación por canal?
- [ ] ¿Respeta `voice.person` (tuteo/usted)?
- [ ] ¿El tema pertenece a alguno de los `content.pillars`?
- [ ] ¿Contiene datos, cifras o testimonios **no verificados**?
- [ ] Si la marca es pre-lanzamiento, ¿se ha inventado prueba social?

---

## Verificación de veracidad

- [ ] ¿Hay algún dato, fuente o cifra que no puedas verificar? → elimínalo o márcalo
- [ ] ¿Se prometen funcionalidades que el producto no tiene hoy?
- [ ] ¿Las estadísticas citadas tienen fuente real?

> La IA optimiza para **sonar convincente**, no para ser veraz. Una cifra inventada que suena plausible es el fallo más caro de todos, porque nadie la cuestiona.

---

## El test final

Léelo en voz alta y responde:

> **¿Podría este texto ser de cualquier otra marca de mi sector?**

Si la respuesta es sí, no ha pasado el checklist — da igual que no contenga ningún TIC.

> *"Vuestra única defensa es la autenticidad radical y la coherencia. Si parece hecho por una máquina para un algoritmo, será ignorado como ruido de fondo."*
