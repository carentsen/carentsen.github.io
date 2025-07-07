# Color Style Guide

## Overview
This style guide defines the color palette for the personal website, based on a pleasant light blue primary color with complementary and analogous colors from the color wheel.

## Primary Color Palette

### Main Brand Color
- **Sky Blue**: `#87CEEB` 
  - **Use for**: Primary buttons, links, brand elements, accent backgrounds
  - **Accessibility**: WCAG AA compliant when used with white text
  - **CSS Variable**: `var(--primary-blue)`

### Color Variations
- **Light Variant**: `#B8E0F5` - For subtle backgrounds and hover states
- **Dark Variant**: `#5FB3D4` - For hover effects and emphasized elements

## Complementary Colors (Color Wheel Opposite)

### Warm Coral
- **Primary**: `#FFAB87`
- **Light**: `#FFD4C4`
- **Dark**: `#FF8A61`
- **Use for**: Call-to-action buttons, warnings, accent elements that need to stand out

## Analogous Colors (Adjacent on Color Wheel)

### Mint Green
- **Primary**: `#87EBC8`
- **Light**: `#B8F5E0`
- **Dark**: `#5FD4A8`
- **Use for**: Success messages, nature-related content, calming sections

### Soft Lavender
- **Primary**: `#B787EB`
- **Light**: `#D4B8F5`
- **Dark**: `#A05FD4`
- **Use for**: Creative sections, premium features, artistic elements

## Neutral Colors

### Text Colors
- **Primary Text**: `#2C5282` (Dark blue) - Main content, headers
- **Secondary Text**: `#4A5568` (Medium gray) - Body text, descriptions
- **Light Text**: `#A0AEC0` (Light gray) - Captions, metadata

### Background Colors
- **Primary Background**: `#FFFFFF` (Pure white) - Main content areas
- **Secondary Background**: `#F7FAFC` (Off-white with blue tint) - Page background
- **Accent Background**: `#E2E8F0` (Light gray) - Cards, sections

## Usage Guidelines

### Do's ✅
- Use the primary blue (`#87CEEB`) as the main brand color
- Use complementary orange (`#FFAB87`) sparingly for important CTAs
- Stick to the defined color variables for consistency
- Test color combinations for accessibility (minimum 4.5:1 contrast ratio)
- Use gradients between analogous colors for visual interest

### Don'ts ❌
- Don't use colors outside this palette without careful consideration
- Don't use bright, saturated colors that clash with the soft palette
- Don't use insufficient color contrast for text readability
- Don't overuse the complementary orange color

## Color Psychology

- **Blue**: Trust, professionalism, calm, reliability
- **Coral/Orange**: Energy, creativity, warmth, friendliness
- **Mint Green**: Growth, harmony, freshness, balance
- **Lavender**: Creativity, luxury, imagination, sophistication

## Implementation

All colors are defined as CSS custom properties in `styles.css`:

```css
:root {
  --primary-blue: #87CEEB;
  --complementary-orange: #FFAB87;
  --analogous-mint: #87EBC8;
  --analogous-lavender: #B787EB;
  /* ... additional color definitions */
}
```

## Accessibility Notes

- All text color combinations meet WCAG AA standards
- Color is never the only way to convey information
- Focus states use sufficient contrast
- Colors work for users with color vision deficiencies

## Future Considerations

- Dark mode variants can be added using the same color relationships
- Seasonal or thematic variations can use the same base palette with adjusted saturation/brightness
- Brand evolution should maintain the core blue-orange relationship
