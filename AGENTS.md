# AGENTS.md

Guía de instrucciones para agentes de IA que trabajen en este repositorio.

## Descripción del proyecto

Este repositorio contiene una presentación web interactiva en un único archivo HTML autocontenido pensada para su uso en una ponencia en directo:

- Archivo principal: `Mujeres,_IA,_STEAM_y_competencias_STEAM_·_AI-STEAM_Network (3).html`
- Título: *Mujeres, IA, STEAM y competencias STEAM · AI-STEAM Network*
- Formato: Presentación narrativa con **desplazamiento horizontal por escenas** (10 escenas en total mediante `.scenes-track` con `translateX`) y un hilo continuo de telar Jacquard (`.continuous-thread-svg`) sincronizado con el avance.
- Stack: HTML5 + CSS (variables en `:root`) + JavaScript Vanilla + Google Fonts (`Instrument Sans`, `Instrument Serif`, `IBM Plex Mono`) + iconos `lucide@1.43.0` vía CDN. Sin paso de compilación (*build*).

---

## Regla crítica: respeto absoluto a los tokens visuales

**NO modifiques, sustituyas, elimines ni redefinas ninguno de los tokens visuales definidos en `:root` (ni la paleta, ni las tipografías, ni las escalas de tamaño, ni los radios, ni los espaciados, ni las curvas/tiempos de animación) hasta que la usuaria lo indique explícitamente.**

### Tokens visuales protegidos (`:root`)

- **Esquema y fondos (*Warm ivory & parchment*)**:
  - `color-scheme: light`
  - `--background: #FAF6ED`
  - `--surface-container-low: #F4EFE3`
  - `--surface-container: #EDE6D6`
  - `--surface-container-high: #E4DAC5`
  - `--surface-elevated: #FFFDF8`
- **Tinta y neutros**:
  - `--on-surface: #1E1B4B`
  - `--on-surface-variant: #46426E`
  - `--on-surface-muted: #5C5885`
- **Líneas y bordes**:
  - `--outline: #1E1B4B`
  - `--outline-variant: #D5CCB8`
  - `--outline-subtle: #E5DEC9`
  - `--rule-ink: 1px solid var(--outline)`
  - `--rule-stone: 1px solid var(--outline-variant)`
  - `--rule-accent: 1.5px solid var(--primary)`
- **Acentos oficiales AI-SECRETT y metáfora textil**:
  - `--primary: #5620F6` / `--on-primary: #FAF6ED`
  - `--primary-container: #EDE8FE` / `--on-primary-container: #2D0F8E`
  - `--secondary: #4918AD` / `--on-secondary: #FAF6ED`
  - `--secondary-container: #EAE3FA`
  - `--tertiary: #8C7355`
  - `--thread-gold: #A68452`
  - `--error: #9A2B22` / `--on-error: #FAF6ED`
- **Series de datos y semántica**:
  - `--data-1: #5620F6`, `--data-2: #4918AD`, `--data-3: #1E1B4B`, `--data-4: #8C7355`, `--data-context: #CFC6B2`
  - `--positive: #1F6F54`, `--warning: #8F5B14`, `--focus: #5620F6`
- **Tipografía y escala**:
  - `--font-headline` / `--font-body`: `'Instrument Sans', -apple-system, BlinkMacSystemFont, sans-serif`
  - `--font-serif`: `'Instrument Serif', Georgia, serif` (usada en `em` para énfasis editorial)
  - `--font-label`: `'IBM Plex Mono', monospace` (`--label-tracking: 0.14em`)
  - `--display-size`, `--headline-size`, `--subhead-size`, `--body-size`, `--label-size`
- **Forma, espaciado y movimiento**:
  - `--rounded: 0.25rem`, `--rounded-lg: 0.5rem`, `--rounded-full: 999px`
  - `--space-xs` (`0.25rem`) a `--space-3xl` (`5.5rem`)
  - `--ease-out: cubic-bezier(0.16, 1, 0.3, 1)`, `--ease-in-out: cubic-bezier(0.65, 0, 0.35, 1)`
  - `--dur-micro: 140ms`, `--dur-short: 260ms`, `--dur-long: 520ms`

---

## Arquitectura de la presentación

- **Shell** (`.presentation-shell`): grid de 3 filas (`auto minmax(0, 1fr) auto`) con barra superior fija (`.deck-topbar`), visor horizontal (`.deck-viewport`) y pie de escena.
- **Navegación**:
  - Barra superior con contador (`#counter-current` / `10`), raíl de progreso Jacquard (10 botones `.rail-node`) y botones `Anterior` / `Siguiente`.
  - Teclado: `ArrowRight` (`nextScene()`) y `ArrowLeft` (`prevScene()`).
- **Escenas (`#scene-1` a `#scene-10`)**:
  1. `Portada`
  2. `Ada Byron y la Ciencia Poética` (revelación manual en 3 pasos: `advanceAdaReveal()`)
  3. `Babbage y la visión de Ada` (comparativa en 3 pasos: `advanceBabbageStep()`)
  4. `De STEM a STEAM` (transición interactiva: `toggleSteamTransition()`)
  5. `La IA es el pincel` (lienzo `<canvas id="human-canvas">` interactivo de co-creación geométrica)
  6. `Red europea de talento`
  7. `7 sectores productivos` (tarjetas desplegables: `toggleSectorCard()`)
  8. `Comunidad de Práctica` (tarjetas desplegables: `toggleCopCard()`)
  9. `Caso real: Proyecto LARA`
  10. `Cierre y contacto` (copia al portapapeles: `copyText()`)

## Buenas prácticas al editar

1. **No romper el scroll horizontal**: mantener `.deck-viewport { overflow: hidden; }`, `.scenes-track { display: flex; }` y `.scene { flex: 0 0 100%; }` junto con `updateSceneUI()`.
2. **No alterar el nombre del archivo principal** salvo petición explícita.
3. **Respetar la accesibilidad**: conservar atributos `aria-hidden`, `aria-expanded`, `aria-label` y `:focus-visible`.
4. **Cualquier nuevo componente o escena** debe reutilizar exclusivamente las variables CSS de `:root` ya existentes y mantener la estética editorial `atelier`.
5. **Verificación**: tras cualquier cambio en el HTML, comprobar en navegador que las 10 escenas navegan correctamente con flechas y botones, que el lienzo de la escena 5 se redimensiona al entrar (`currentScene === 4`) y que no hay desbordamientos verticales ni horizontales.
