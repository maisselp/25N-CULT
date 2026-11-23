# Mujeres, IA, STEAM y competencias STEAM · AI-STEAM Network

Presentación web interactiva con desplazamiento horizontal diseñada para la ponencia **«Mujeres, IA, STEAM y competencias STEAM. La red AI-STEAM Network»** (25 de noviembre de 2026 · Universitat de València), impartida por **María José Lozano Pérez**.

---

## Resumen de la ponencia

La ponencia traza un hilo histórico y conceptual desde la figura de **Ada Lovelace (Ada Byron)** y su noción de *«Ciencia Poética»* hasta los retos actuales de la **Inteligencia Artificial** y el enfoque **STEAM** (incorporando las Artes y las Humanidades al ámbito científico-tecnológico). Frente a una visión puramente mecánica del cálculo, la presentación defiende que *la IA es el pincel, pero la mirada, el criterio y el sentido cultural siguen siendo humanos*.

A partir de esa base, el recorrido conecta el pasado con la iniciativa europea **AI-SECRETT** y la **Comunidad de Práctica (CoP) AI-STEAM Network**, mostrando cómo convergen la Formación Profesional, la Universidad (con la participación de **8 universidades europeas** del consorcio), el talento femenino y los creadores en siete sectores productivos, con ejemplos reales como el **Proyecto LARA** (IA inclusiva desde la FP) y una invitación abierta a participar.

---

## Contenido de la ponencia (10 escenas)

La presentación se articula como un recorrido narrativo horizontal en 10 escenas conectadas por un hilo continuo inspirado en el telar Jacquard:

1. **Portada**: Título de la ponencia, fecha, sede y lámina geométrica de urdimbre y trama Jacquard.
2. **Ada Byron y la «Ciencia Poética»**: Revelación progresiva en directo de Ada Lovelace y sus referentes familiares (Annabella Milbanke y Lord Byron).
3. **La máquina de Babbage y la visión de Ada**: Comparativa paso a paso entre la Máquina Analítica de Charles Babbage y la visión computacional y simbólica de Ada.
4. **De STEM a STEAM**: Transición interactiva para incorporar la **«A»** de Artes y Humanidades al enfoque científico-tecnológico.
5. **La IA es el pincel. La mirada es humana.**: Lienzo interactivo (`<canvas>`) de trazo libre a mano alzada que simula un pincel fino de artista guiado por el criterio humano.
6. **Del pasado al presente: la red europea de talento**: Conexión entre Formación Profesional, Universidad (`8 universidades europeas`), creadores y sociedad europea, con la placa oficial de AI-SECRETT.
7. **Los 7 sectores productivos de AI-SECRETT**: Tarjetas desplegables que muestran la convergencia entre IA y competencias STEAM en siete sectores clave.
8. **La Comunidad de Práctica (CoP) AI-STEAM Network**: Estructura y funcionamiento de la comunidad mediante tarjetas interactivas, respaldada por las 8 universidades europeas.
9. **Proyecto LARA: IA inclusiva desde la FP**: Caso real de aplicación de inteligencia artificial inclusiva desarrollada desde la Formación Profesional (IES Severo Ochoa), con acceso directo al vídeo del proyecto.
10. **Cómo formar parte de AI-STEAM Network**: Cierre, invitación abierta conectada con las 8 universidades europeas, botones directos de «Abrir web», códigos QR y utilidades de contacto con copia rápida al portapapeles.

---

## Estilo visual y diseño

La pieza sigue un estilo editorial **`atelier`** combinado con la identidad oficial de **AI-SECRETT** y la metáfora visual del **telar Jacquard**:

- **Paleta cromática**: Fondo cálido en marfil y pergamino (`#FAF6ED`, `#F4EFE3`, `#EDE6D6`), tinta azul noche de alto contraste (`#1E1B4B`) y acentos violeta/índigo (`#5620F6`, `#4918AD`) junto con matices tierra y dorado textil (`#8C7355`, `#A68452`).
- **Tipografía**:
  - *Titulares y cuerpo*: `Instrument Sans`
  - *Énfasis editorial en cursiva*: `Instrument Serif`
  - *Etiquetas, contadores y metadatos*: `IBM Plex Mono`
- **Hilo conductor**: Un trazado SVG continuo (`continuous-thread-svg`) recorre horizontalmente las 10 escenas de forma sincronizada con el raíl superior de progreso.

---

## Cómo usar y presentar

El proyecto es **autocontenido** en un único archivo HTML, sin dependencias de compilación ni servidores obligatorios:

1. Clona o descarga este repositorio.
2. Abre el archivo [index.html](./index.html) directamente en cualquier navegador moderno (Chrome, Edge, Firefox o Safari).
   - *Nota*: Requiere conexión a internet en el momento de abrirla para cargar las tipografías de Google Fonts y los iconos de `lucide` desde CDN.
3. Pulsa `F11` (o modo pantalla completa del navegador) para proyectar en la ponencia.

### Controles durante la ponencia

- **Teclado**: `→` (siguiente escena) y `←` (escena anterior).
- **Barra superior**: Botones `Anterior` / `Siguiente` y nodos clicables en el raíl de progreso (`01` a `10`).
- **Interacciones en escena**:
  - Escenas 2 y 3: botones de revelación paso a paso para acompañar el ritmo del discurso.
  - Escena 4: conmutador `Incorporar la «A»` / `Volver a STEM`.
  - Escena 5: dibujo interactivo con ratón/puntero sobre el lienzo y botón de limpieza.
  - Escenas 7 y 8: clic sobre cada tarjeta para desplegar o contraer su contenido.
  - Escena 10: botones de copia rápida al portapapeles.

---

## Estructura del repositorio

```text
.
├── AGENTS.md                                                                 # Instrucciones y tokens protegidos para agentes IA
├── README.md                                                                 # Documentación del proyecto
└── index.html                                                                # Presentación HTML autocontenida
```
