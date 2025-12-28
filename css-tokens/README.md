# CSS Design Tokens

## Philosophy

This token system embodies several key principles:

### 1. Perceptual Uniformity

Colors use the `oklch()` color space rather than `hsl()` or `rgb()`. This ensures:

- Consistent perceived brightness across hues
- More predictable color manipulation
- Better accessibility through perceptual lightness control

### 2. Semantic Naming

Tokens are named by their purpose or scale value, not their appearance:

- `--color-primary` not `--color-teal`
- `--size-16` (16px value) not `--spacing-small`
- `--text-xl` (size indicator) not `--heading-size`

### 3. System Thinking

The design system is interconnected:

- Border radius values reference the spacing scale
- Typography sizes follow a modular scale
- Z-index uses named layers, not arbitrary numbers

### 4. Dark Mode First-Class

Dark mode isn't an afterthought:

- Colors are redefined in `prefers-color-scheme: dark`
- Values are adjusted for optimal contrast in both modes
- The system maintains visual hierarchy in light and dark

### 5. Scale Consistency

Both spacing and typography use consistent scales:

- Spacing: 4px base unit (0.25rem)
- Typography: Modular scale with clear relationships

## Token Categories

### Typography

- **Font Families**: System fonts with web-safe fallbacks
- **Weights**: Named weights from regular to bold
- **Sizes**: Modular scale from xs (12px) to 4xl (36px)

### Spacing

- **Size Scale**: 4px increments from 4px to 96px
- Named by pixel value for clarity (`--size-16` = 1rem = 16px)

### Colors

- **Surfaces**: Background colors for different elevation levels
- **Text**: Primary, muted, and inverted text colors
- **Brand**: Logo-specific colors
- **Interactive**: Primary and accent colors with hover states
- **Semantic**: Success, error, warning, info states
- **Borders**: Subtle and strong border options

### Layout

- **Border Radius**: Five levels from small to full circle
- **Z-index**: Named layers for predictable stacking
- **Transitions**: Three timing options (fast, base, slow)

## Usage Examples

```css
/* Typography */
.heading {
  font-family: var(--font-family-base);
  font-size: var(--text-2xl);
  font-weight: var(--font-weight-bold);
}

/* Spacing */
.card {
  padding: var(--size-24);
  margin-block-end: var(--size-32);
}

/* Colors */
.button {
  background-color: var(--color-primary);
  color: var(--color-text-inverted);
}

.button:hover {
  background-color: var(--color-primary-hover);
}

/* Layout */
.modal {
  border-radius: var(--radius-lg);
  z-index: var(--layer-modal);
}
```

## Extending the System

These tokens provide a foundation. Projects can:

- Add component-specific tokens that reference these base tokens
- Create semantic aliases (e.g., `--button-bg: var(--color-primary)`)
- Extend the color palette while maintaining the `oklch()` approach

The key is maintaining the system's consistency and semantic approach.
