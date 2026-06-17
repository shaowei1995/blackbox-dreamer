# jiejoe Design Study Log

## 2026-06-18 - Session 1: Easing, Hover Micro-interactions & ScrollTrigger Timing

### Design Principles Studied (from jiejoe's Awwwards-awarded work)

1. **Easing Curve System**: jiejoe uses dramatically asymmetric cubic-beziers rather than symmetric ones. Signature curves include `cubic-bezier(.76, 0, .24, 1)` for reveals (fast-in, slow-out with a plateau) and `cubic-bezier(.16, 1, .3, 1)` for exits (explosive start, gentle landing). This creates a sense of weight and intentionality absent from standard `ease` or `power2`.

2. **Multi-speed Hover Layers**: Instead of uniform transition durations, jiejoe layers hover properties at different speeds — border-color changes fast (0.2s), box-shadow blooms slowly (0.6s), and transform settles in between (0.4s). This creates an organic, "alive" feeling where different visual properties respond at different tempos.

3. **GSAP Easing Variation**: In scroll-triggered animations, jiejoe uses `power3.out` and `power4.inOut` for dramatic entrances, reserving `power2.out` only for subtle secondary elements. Duration is also slightly longer (1.2-1.4s vs standard 0.8-1.0s) to create a more cinematic feel.

4. **Breathing Animations on Static Elements**: Key visual elements like skill cards and photo plates get subtle continuous animations (scale pulse, box-shadow glow cycle) that make the page feel alive even when the user isn't interacting.

5. **Stagger Refinement**: Text character reveals use exponential stagger (each subsequent character slightly faster) rather than linear, and entrance animations include subtle rotationY for a 3D perspective feel.

### Applied Optimizations

1. Added jiejoe-style custom easing properties (`--ease-reveal`, `--ease-out-expo`) to CSS variables
2. Enhanced `.hss_block` hover with multi-speed transition layers (border 0.2s, shadow 0.6s, transform 0.4s)
3. Added subtle breathing glow animation to `.hss_block` for ambient life
4. Enhanced `.hpp_plate` hover with layered transition speeds
5. Upgraded GSAP ScrollTrigger animations: `power2.out` → `power3.out` for primary entrances, longer durations (1.15→1.3s), added subtle rotationY to skill card entrances
6. Added `--ease-reveal` to hero clip-path reveal and menu overlay transitions
7. Enhanced section separator entrance with scale + opacity stagger
