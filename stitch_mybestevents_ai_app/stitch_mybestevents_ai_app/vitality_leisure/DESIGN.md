---
name: Vitality & Leisure
colors:
  surface: '#f9f9f9'
  surface-dim: '#dadada'
  surface-bright: '#f9f9f9'
  surface-container-lowest: '#ffffff'
  surface-container-low: '#f3f3f3'
  surface-container: '#eeeeee'
  surface-container-high: '#e8e8e8'
  surface-container-highest: '#e2e2e2'
  on-surface: '#1a1c1c'
  on-surface-variant: '#3d4a40'
  inverse-surface: '#2f3131'
  inverse-on-surface: '#f1f1f1'
  outline: '#6d7a6f'
  outline-variant: '#bccabd'
  surface-tint: '#006d40'
  primary: '#006d40'
  on-primary: '#ffffff'
  primary-container: '#2bb673'
  on-primary-container: '#004024'
  inverse-primary: '#5cde97'
  secondary: '#5f5e5e'
  on-secondary: '#ffffff'
  secondary-container: '#e2dfde'
  on-secondary-container: '#636262'
  tertiary: '#5d5f5f'
  on-tertiary: '#ffffff'
  tertiary-container: '#9fa0a0'
  on-tertiary-container: '#353738'
  error: '#ba1a1a'
  on-error: '#ffffff'
  error-container: '#ffdad6'
  on-error-container: '#93000a'
  primary-fixed: '#7afbb1'
  primary-fixed-dim: '#5cde97'
  on-primary-fixed: '#002110'
  on-primary-fixed-variant: '#00522f'
  secondary-fixed: '#e5e2e1'
  secondary-fixed-dim: '#c8c6c5'
  on-secondary-fixed: '#1b1b1c'
  on-secondary-fixed-variant: '#474746'
  tertiary-fixed: '#e2e2e2'
  tertiary-fixed-dim: '#c6c6c7'
  on-tertiary-fixed: '#1a1c1c'
  on-tertiary-fixed-variant: '#454747'
  background: '#f9f9f9'
  on-background: '#1a1c1c'
  surface-variant: '#e2e2e2'
typography:
  h1:
    fontFamily: Inter
    fontSize: 32px
    fontWeight: '600'
    lineHeight: '1.2'
    letterSpacing: -0.02em
  h2:
    fontFamily: Inter
    fontSize: 24px
    fontWeight: '600'
    lineHeight: '1.3'
    letterSpacing: -0.01em
  h3:
    fontFamily: Inter
    fontSize: 20px
    fontWeight: '600'
    lineHeight: '1.4'
    letterSpacing: '0'
  body-lg:
    fontFamily: Inter
    fontSize: 18px
    fontWeight: '400'
    lineHeight: '1.6'
    letterSpacing: '0'
  body-md:
    fontFamily: Inter
    fontSize: 16px
    fontWeight: '400'
    lineHeight: '1.5'
    letterSpacing: '0'
  label-md:
    fontFamily: Inter
    fontSize: 14px
    fontWeight: '600'
    lineHeight: '1.2'
    letterSpacing: 0.02em
  caption:
    fontFamily: Inter
    fontSize: 12px
    fontWeight: '400'
    lineHeight: '1.4'
    letterSpacing: '0'
rounded:
  sm: 0.25rem
  DEFAULT: 0.5rem
  md: 0.75rem
  lg: 1rem
  xl: 1.5rem
  full: 9999px
spacing:
  base: 8px
  xs: 4px
  sm: 12px
  md: 16px
  lg: 24px
  xl: 32px
  gutter: 16px
  margin-mobile: 20px
  margin-desktop: 40px
---

## Brand & Style
The design system is rooted in **Modern Minimalism**, prioritizing clarity, breathability, and a "high-end concierge" feel. It balances the clinical reliability of a health platform with the aspirational energy of a travel app. 

The interface leverages heavy whitespace to reduce cognitive load, allowing high-quality imagery to serve as the primary emotional driver. The style is strictly "Airy Professional"—avoiding unnecessary decorations in favor of precise alignment, generous margins, and a sense of calm reliability.

## Colors
This design system utilizes a high-contrast but soothing palette. 
- **Primary Green (#2BB673):** Used for growth, health, and primary calls to action. It should be used sparingly to maintain its energetic impact.
- **Soft Black (#1E1E1E):** Reserved for high-level typography and essential UI borders, providing a grounded, premium feel without the harshness of pure black.
- **Light Gray (#F5F5F5):** The foundational canvas color, creating a soft distinction between the background and white content containers.
- **Pure White (#FFFFFF):** Used for elevated cards and surfaces to create depth against the gray background.

## Typography
The system uses **Inter** exclusively to ensure a systematic, clean, and highly legible experience across all devices. 
- **Headlines:** Set in SemiBold (600) with slight negative letter spacing to create a compact, premium editorial look.
- **Body Text:** Set in Regular (400) with a generous line height to ensure maximum readability during long-form event descriptions.
- **Labels:** Uppercase or slightly tracked SemiBold weights are used for utility text like category tags or filtering chips.

## Layout & Spacing
This design system follows an **8px linear scale** to maintain rhythmic consistency. The layout philosophy uses a **fixed-width container** for desktop (12 columns) and a **fluid grid** for mobile.

- **Margins:** Mobile views use a 20px side margin to provide extra "breathing room" compared to standard 16px layouts.
- **Gaps:** Use 16px gutters for card grids and 24px-32px vertical spacing between distinct sections to reinforce the airy aesthetic.

## Elevation & Depth
Depth is conveyed through **Tonal Layering** and **Ambient Shadows**. 
- **The Base:** All page backgrounds are Light Gray (#F5F5F5).
- **The Surface:** Interactive elements and content containers are Pure White (#FFFFFF).
- **The Shadow:** Use a singular, ultra-soft shadow style for cards: `0px 4px 20px rgba(0, 0, 0, 0.05)`. This creates a subtle lift without appearing heavy or dated. 
- **Floating Elements:** Floating Action Buttons (FABs) use a slightly more aggressive shadow `0px 8px 24px rgba(43, 182, 115, 0.2)` to emphasize their primary function and primary color.

## Shapes
The shape language is friendly and modern, utilizing a "Rounded" (Level 2) approach. 
- **Standard Radius:** 16px for secondary components and small cards.
- **Large Radius:** 20px for primary feature cards and hero sections.
- **Interactive Elements:** Buttons and search inputs should maintain a consistent 12px-16px radius, while filter chips utilize a pill-shape (full radius) for high tactile contrast.

## Components
- **Cards:** Use a 16:9 aspect ratio for images. Text is placed on the white surface below the image, never as an overlay unless a gradient scrim is applied for legibility.
- **Buttons:** Primary buttons are Solid Green (#2BB673) with White text. Secondary buttons use a Soft Black (#1E1E1E) outline or a light gray ghost style.
- **Floating Action Buttons (FAB):** Circular, Primary Green, positioned in the bottom right with a clear icon (e.g., plus or map toggle).
- **Search Bar:** Large, full-width White container with a subtle 1px border (#E0E0E0) and a Soft Black magnifying glass icon.
- **Filtering Chips:** Pill-shaped with a Light Gray fill; when active, they transition to Soft Black with White text to signify a firm selection.
- **Navigation:** A clean bottom navigation bar on mobile with thin-stroke icons and subtle labels.