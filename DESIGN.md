---
name: NERDS Design System
colors:
  surface: '#101415'
  surface-dim: '#101415'
  surface-bright: '#363a3b'
  surface-container-lowest: '#0b0f10'
  surface-container-low: '#191c1e'
  surface-container: '#1d2022'
  surface-container-high: '#272a2c'
  surface-container-highest: '#323537'
  on-surface: '#e0e3e5'
  on-surface-variant: '#c2c6d1'
  inverse-surface: '#e0e3e5'
  inverse-on-surface: '#2d3133'
  outline: '#8c919b'
  outline-variant: '#424750'
  surface-tint: '#a5c8ff'
  primary: '#a5c8ff'
  on-primary: '#00315f'
  primary-container: '#00417b'
  on-primary-container: '#83afef'
  inverse-primary: '#305f9b'
  secondary: '#fff9ef'
  on-secondary: '#3a3000'
  secondary-container: '#ffdb3c'
  on-secondary-container: '#725f00'
  tertiary: '#a7c8ff'
  on-tertiary: '#003061'
  tertiary-container: '#00407d'
  on-tertiary-container: '#78aeff'
  error: '#ffb4ab'
  on-error: '#690005'
  error-container: '#93000a'
  on-error-container: '#ffdad6'
  primary-fixed: '#d4e3ff'
  primary-fixed-dim: '#a5c8ff'
  on-primary-fixed: '#001c3a'
  on-primary-fixed-variant: '#0e4782'
  secondary-fixed: '#ffe16d'
  secondary-fixed-dim: '#e9c400'
  on-secondary-fixed: '#221b00'
  on-secondary-fixed-variant: '#544600'
  tertiary-fixed: '#d5e3ff'
  tertiary-fixed-dim: '#a7c8ff'
  on-tertiary-fixed: '#001b3c'
  on-tertiary-fixed-variant: '#004689'
  background: '#101415'
  on-background: '#e0e3e5'
  surface-variant: '#323537'
typography:
  display-2xl:
    fontFamily: Inter
    fontSize: 72px
    fontWeight: '800'
    lineHeight: '1.1'
    letterSpacing: -0.04em
  headline-lg:
    fontFamily: Inter
    fontSize: 32px
    fontWeight: '700'
    lineHeight: '1.2'
    letterSpacing: -0.02em
  body-md:
    fontFamily: Inter
    fontSize: 16px
    fontWeight: '400'
    lineHeight: '1.6'
    letterSpacing: 0em
  label-mono:
    fontFamily: Space Grotesk
    fontSize: 12px
    fontWeight: '500'
    lineHeight: '1'
    letterSpacing: 0.05em
  code-accent:
    fontFamily: monospace
    fontSize: 14px
    fontWeight: '400'
    lineHeight: '1.4'
rounded:
  sm: 0.25rem
  DEFAULT: 0.5rem
  md: 0.75rem
  lg: 1rem
  xl: 1.5rem
  full: 9999px
spacing:
  container-max: 1280px
  gutter: 1.5rem
  margin-page: 2rem
  unit-xs: 0.25rem
  unit-sm: 0.5rem
  unit-md: 1rem
  unit-lg: 2rem
  unit-xl: 4rem
---

## Brand & Style
The design system is engineered to bridge the gap between institutional prestige and cutting-edge technological innovation. It targets a youthful, high-achieving demographic of researchers and developers who value technical precision and modern aesthetics.

The visual style is a hybrid of **Glassmorphism** and **Modern Corporate**, utilizing the depth of semi-transparent layers to create a sense of sophisticated hierarchy. It evokes an emotional response of "Intellectual Energy"—combining the stability of the university’s heritage with the fast-paced nature of modern software engineering. The aesthetic is clean and "Tailwind-inspired," emphasizing utility, structured whitespace, and high-density information display without clutter.

## Colors
The color strategy for this design system is built on a high-contrast dark mode foundation. The **Deep Institutional Blue** serves as the immersive background, providing a stable, "infinite" space for research content. The **Vibrant Gold** is used exclusively for high-priority actions, conversion points, and critical status indicators, ensuring they "pop" against the dark canvas.

A lighter **Tertiary Blue** is utilized for interactive hover states and decorative glass borders. Neutrals are strictly cool-toned, ranging from pure white for primary text to muted slate blues for secondary metadata, maintaining a crisp, "technical" atmosphere throughout.

## Typography
This design system utilizes a dual-type architecture. **Inter** is the workhorse font, used in heavy weights for headlines to project authority and clarity. Its neutral, geometric nature ensures readability across complex data sets.

For technical accents and labels, **Space Grotesk** (or a system Monospace) is employed to inject a "code-editor" aesthetic. This distinction helps the user quickly identify metadata, version numbers, and technical specs. Headlines should always use tight letter-spacing to maintain a modern, high-energy feel, while monospaced labels should use slightly increased tracking for a clean, scientific look.

## Layout & Spacing
The layout follows a **Fixed-Fluid Hybrid Grid**. It utilizes a 12-column structure centered within a max-width container, allowing for expansive "glass" panels that can span multiple columns. 

The spacing rhythm is based on an 8px (0.5rem) base unit, consistent with the Tailwind CSS ecosystem. High-energy layouts should leverage wide margins for primary content sections to allow the background grid patterns to breathe, while using tighter spacing within component groups (like card headers and data lists) to maintain a sense of technical density.

## Elevation & Depth
Depth in this design system is achieved through **Glassmorphism** rather than traditional shadows. Layers are defined by their backdrop-blur intensity (ranging from 8px to 20px) and a subtle 1px inner border (stroke) that simulates a light catch on a glass edge.

- **Base Layer:** Deep Blue background with a subtle, low-opacity CSS grid pattern (1px lines every 40px).
- **Surface Layer:** Semi-transparent blue (#FFFFFF10) with a heavy backdrop-blur.
- **Interactive Layer:** Vibrant Gold elements, which sit at the highest perceived elevation, often accompanied by a soft outer glow (bloom) rather than a black shadow, to simulate an emissive light source.

## Shapes
The shape language is defined by **Rounded-XL** geometry. Large containers and cards use a 1.5rem corner radius to soften the technical aesthetic and make the interface feel modern and approachable. 

Small interactive elements like buttons and input fields follow a consistent 0.5rem radius. This contrast between "large soft panels" and "precise inner elements" creates a balanced visual hierarchy. Avoid sharp 0px corners entirely to maintain the youthful, innovative tone of the design system.

## Components
### Buttons
Primary CTAs are solid **Gold (#FFD700)** with black text for maximum legibility. They use a subtle "glow" box-shadow on hover. Secondary buttons are "ghost" style with a 1px white-transparent border and backdrop-blur.

### Cards
Cards are the primary content vessel. They must feature a `backdrop-filter: blur(12px)` and a top-weighted linear gradient stroke to simulate light hitting the top edge. 

### Labels & Accents
Use the Monospace font for small "tags" (e.g., [RESEARCH], [V2.0], [UFC_LAB]). These should be styled as small chips with a background color that is only 10% opaque.

### Inputs
Input fields are dark-filled with a 1px border that glows **Gold** only when focused. Placeholder text should be a muted blue-gray.

### Background Grid
A persistent, subtle SVG grid pattern must be present on the base layer. This grid acts as a structural guide, reinforcing the "research and engineering" theme of the group.