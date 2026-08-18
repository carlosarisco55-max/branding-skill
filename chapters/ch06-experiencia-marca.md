# Ch06 — Experiencia de marca (cómo se vive la marca)

Cuarto eje. Los tres anteriores definen qué es la marca, cómo habla y cómo se ve. Este define **qué siente la persona al encontrarse con ella**, punto por punto.

Es el eje que más se salta la gente, y el que explica por qué marcas con buen logo y buen tono siguen sin convertir.

---

## Los tres componentes

| Componente | Qué define |
|---|---|
| **Touchpoints** | Puntos de contacto: web, RRSS, tienda física, atención al cliente, producto, email, facturación |
| **Experiencia de usuario** | Cómo interactúa el público con la marca en cada uno |
| **Sensaciones / emociones** | Lo que la marca quiere hacer sentir: confianza, inspiración, diversión, alivio |

---

## Mapa de touchpoints

Para cada punto de contacto, responde tres preguntas del curso:

1. **¿Qué siente la persona en este touchpoint?**
2. **¿Cuál es la acción (CTA) y qué fricción la bloquea?**
3. **¿Cómo se traduce en conversión** (lead / venta / reserva)?

Formato de trabajo:

| Touchpoint | Momento del journey | Emoción objetivo | CTA | Fricción a eliminar |
|---|---|---|---|---|
| Anuncio / post | Descubrimiento | Reconocimiento ("me pasa a mí") | Seguir leyendo | Sonar a publicidad |
| Landing | Consideración | Alivio ("esto lo resuelve") | Prueba gratuita | Formulario largo, precio oculto |
| Onboarding | Activación | Competencia ("lo controlo") | Completar setup | Demasiados pasos |
| Producto en uso | Uso | Confianza | Acción recurrente | Aprender una plataforma nueva |
| Soporte | Incidencia | Acompañamiento | Contactar | No encontrar a un humano |
| Facturación / renovación | Fidelización | Justicia | Renovar | Sorpresas en el cobro |

> **Regla**: cada touchpoint debe tener una emoción objetivo **distinta y explícita**. Si tres touchpoints aspiran a "confianza", no has diseñado la experiencia, has repetido un adjetivo.

---

## El IKIGAI del branding

Así como el ikigai personal conecta lo que amas, lo que sabes hacer, lo que el mundo necesita y por lo que te pueden pagar, el **Ikigai del Branding** conecta las cuatro dimensiones esenciales de una marca — que son exactamente los cuatro ejes del brand book:

```
        ESTRATEGIA                    IDENTIDAD VERBAL
     (lo que es y quiere ser)            (cómo habla)
                    \                  /
                     \                /
                      \   BRANDING   /
                       \ AUTÉNTICO  /
                       /  Y COHERENTE\
                      /               \
                     /                 \
        IDENTIDAD VISUAL          EXPERIENCIA
          (cómo se ve)      (cómo se vive y por qué pagan)
```

### 1) Estrategia — lo que es y quiere ser
**Inputs**: misión, visión, valores, propuesta de valor, buyer persona, DAFO/CAME.
**Preguntas guía**:
- ¿Qué problema resolvemos y para quién?
- ¿Cuál es nuestro diferencial demostrable?
- ¿Qué NO somos / qué NO prometemos?

### 2) Identidad verbal — cómo habla
**Inputs**: arquetipo principal/secundario + message house + objeciones.
**Preguntas guía**:
- ¿Qué tono sostenemos 3 meses?
- ¿Cuáles son nuestros mensajes madre?
- ¿Qué territorios editoriales vamos a ocupar?

### 3) Identidad visual — cómo se ve
**Inputs**: arquetipo + estilo visual + referencias benchmark.
**Preguntas guía**:
- ¿Qué estilo visual nos hace reconocibles?
- ¿Cómo se ve una pieza "de marca" **sin logo**?

### 4) Experiencia — cómo se vive y por qué pagan
**Inputs**: embudo, touchpoints, activación de campaña.
**Preguntas guía**:
- ¿Qué siente la persona en cada touchpoint?
- ¿Cuál es la acción (CTA) y qué fricción la bloquea?
- ¿Cómo se traduce en conversión (lead / venta / reserva)?

> **Cuando estas cuatro áreas están alineadas, surge el branding auténtico y coherente, capaz de generar confianza, diferenciación y conexión real con el público.**

### Cómo usarlo como diagnóstico
El IKIGAI no es solo un gráfico bonito para la presentación. Es un **detector de desalineación**:

| Faltan | Síntoma |
|---|---|
| Estrategia | Marca bonita que no sabe qué promete. Se nota en que el copy cambia cada mes |
| Identidad verbal | Diseño coherente, textos intercambiables con la competencia |
| Identidad visual | Buen mensaje que nadie recuerda porque no se reconoce |
| Experiencia | Todo suena y se ve bien, pero nadie convierte |

Si un proyecto llega en modo auditoría, este cuadro es el primer diagnóstico a aplicar.

---

## Cómo se documenta

```json
"experience": {
  "touchpoints": [
    { "name": "landing", "stage": "consideration", "emotion": "alivio",
      "cta": "prueba gratuita", "friction": "formulario largo" }
  ],
  "brandPromise": "...",
  "whatWeAreNot": ["...", "..."]
}
```

El campo `whatWeAreNot` es tan importante como la promesa: sale de la pregunta "¿qué NO somos / qué NO prometemos?" y es lo que después impide que la marca acepte cualquier encargo o cualquier cliente.

---

**Siguiente**: [ch07 — Pilares y canales](ch07-pilares-y-canales.md).
